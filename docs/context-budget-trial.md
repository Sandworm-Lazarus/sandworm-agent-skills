# Context budget trial: preserve the evidence before claiming savings

Original Sandworm-Lazarus procedure, 2026-11-16, MIT. This is a trial design and blank record, not an RTK/MCP Compressor implementation or a measured performance result. Canonical source: `originals/agent-skills/` in the hub; the generator publishes this guide only to Agent Skills.

## Choose the mechanism

| Tool | Useful task | What can shrink | What must remain observable |
| --- | --- | --- | --- |
| RTK OSS | Coding agents reading long git/test/lint output | Command output before entering conversation | Exit status, failure/assertion/location, raw-output recovery |
| MCP Compressor | An agent connected to a large tool catalog | Upfront descriptions/schemas; optional response shrinking | Resolved backend tool identity, argument schema, errors, authorization, raw response recall |

A smaller main context is useful, but an extra schema lookup, retry, model call, or re-read may raise total cost. Do not turn output-byte reduction into a percentage reduction in provider billing. RTK's bytes/4 estimate is not a Thai tokenizer.

## Start with our existing offline utility

From the generated Agent Skills repository root:

```bash
python3 scripts/tool_policy.py --policy examples/policy.json --request examples/request-allow.json --now 2030-01-01T00:00:00Z
python3 -m json.tool examples/context-trial.template.json
python3 -m unittest discover -s tests -v
```

These run original Sandworm code/JSON validation only. They do not install either upstream, launch a server, call a model, or test a real MCP authorization boundary. The policy evaluator is a decision harness, not an enforcing executor.

## Record before a future operator-run trial

1. Copy the blank template into a private report directory. Fill exact upstream commit, edition, client/runtime version, backend contract hash and tokenizer/provider identity. Keep raw command output and tool responses private; log aliases/hashes in a shareable summary.
2. Use a disposable small repository, synthetic documents, a read-only fixture backend and the same task in both variants. No production account, arbitrary backend command or private data is needed.
3. Hold prompt, model, effort, file revision, task acceptance criteria and output limits constant. Define a maximum call count, retry count and wall deadline before starting. Separate cold-cache and warm-cache attempts.
4. Compare a baseline with **one** mechanism. First RTK OSS alone or schema-on-demand alone; do not combine several filters and route models in the first comparison.
5. Include model input/output tokens, cached input, lookup calls, retries, wall time and all additional summarizer/provider calls. Preserve raw provider usage units rather than adding cached tokens twice. Leave unavailable values null and record why.
6. Use the same tokenizer for context-size comparisons. Record byte counts separately. A negative saving is a valid result; never omit failed or slower tasks.

No upstream trial has been run for this guide.

## Six concrete acceptance cases

| Case | Synthetic input | Pass condition |
| --- | --- | --- |
| Passing test output | Many passing tests | Correct pass count and unchanged exit status |
| Failed test output | One failing assertion with file/line | Agent identifies that assertion; raw detail can be recovered |
| Thai diagnostics | Thai text plus explicit email/JSON fixture fields | Text meaning is retained; configured privacy fields do not leave the boundary |
| MCP discovery | Many read-only tool definitions | Selected tool's full input schema is available before invocation |
| MCP misuse | Unknown tool, malformed arguments and a denied operation | Errors/denials remain distinguishable; wrapper dispatch does not authorize a backend call |
| Long response | Large synthetic response | Truncation is explicit and authorized full recall returns the corresponding response |

For MCP wrappers, enforce policy on the resolved backend operation, not merely the generic `invoke_tool` wrapper name. Test that cache/recall cannot cross principal or workspace boundaries. A smaller schema surface is not an authorization mechanism. The upstream snapshot requires legacy initialize support on backends and does not support dynamic catalog subscriptions.

## Stop rules and decision

Stop and retain the failure if an assertion, tool name, error flag, deny decision, source citation, or privacy sentinel disappears. Reject a configuration that improves bytes while failing the task. For passing variants, report end-to-end cost and time alongside context size; do not choose a winner from a single favorable output.

The template has no fabricated token usage or default savings. It requires a completion reason and an evidence location before a future human reviewer can interpret an attempt. It is a recording aid, not an executable schema validator.

## Upstream credit, scope and requirements

- [RTK README, pinned](https://github.com/rtk-ai/rtk/blob/8bb6096b773546547d7704f9a8683ea9719a5017/README.md): review covered README, root LICENSE, Cargo.toml, engine/LICENSE and proxy/LICENSE. Choose `rtk-oss` for Apache-2.0 filters/hooks; full default builds include a BUSL-1.1 engine. Engine/proxy grants exclude offering the licensed work or derivatives as paid or hosted products/services; their recorded Change Date is 2030-09-09. Preserve notices and review the actual component license before redistribution. Source manifest declares Rust 1.91; prebuilt binaries require an appropriate OS/architecture and compatible agent setup.
- [MCP Compressor README, pinned](https://github.com/atlassian-labs/mcp-compressor/blob/53e746d1e24c71328526c5c813559fc0557dd282/README.md): Apache-2.0 root license; reviewed Python/TypeScript manifests as requirement evidence. Python package declares >=3.11,<4; TypeScript uses a native Rust binding and its source build uses Bun tooling. SDK/runtime/backend prerequisites depend on the chosen package; inspect installation docs instead of assuming a pure-JS drop-in.

Both repositories were unarchived when inspected on 2026-11-16. Catalog records remain `readme-overview` and `runtime_tested: false`. No upstream code or bundles are copied into this guide.
