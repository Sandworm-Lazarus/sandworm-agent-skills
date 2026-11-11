# Start here: Agent Skills

[Home](../README.md) · [Tools](../TOOLS.md) · [Sources](../SOURCES.md)

Select a task, inspect the complete pinned package, then try a bounded synthetic fixture. These are reading paths and prototype ideas, not tested integrations.

## Design the agent

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [LangGraph](https://github.com/langchain-ai/langgraph/tree/5ea88ecbcdb9fde713c3abd58850a5b7beaa24ec) | สร้าง stateful workflow ที่มี durable execution และจุดให้คนตรวจ | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai/tree/f5c460d46ad9d03200371751d3d89f3ea58433de) | สร้าง typed Agents, tool calls และ structured outputs ใน Python | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Agno](https://github.com/agno-agi/agno/tree/0b88f303e1ebd58a92677652fdeaddd7e7618362) | สร้าง Agent teams/workflows และให้บริการผ่าน API/MCP ด้วย AgentOS | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [CrewAI](https://github.com/crewAIInc/crewAI/tree/4254a835b1e5433d123e201928612bc692edbc3e) | จัด role-based agent collaboration และ event-driven Flows | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Mastra](https://github.com/mastra-ai/mastra/tree/59a60e42d5985980d1a36cf0bcddeead09283703) | สร้าง Agents, graph workflows, memory และ MCP integrations บน TypeScript | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Preserve useful context

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [Mem0](https://github.com/mem0ai/mem0/tree/f1791daa86d469249c9b002f62644d58a1eb96a0) | เพิ่ม memory layer ที่แยก user/session/agent context | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Graphiti](https://github.com/getzep/graphiti/tree/ebef986a0b2360211b65751c111cacb4a7d790eb) | เก็บ entities, relationships และ facts ที่มีช่วงเวลาความถูกต้อง | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Choose a personal harness

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent/tree/60f81635c28e825a233f7bb25ed93a2579d5b547) | Agent ส่วนตัวที่ใช้ tools, memory, skills และ messaging gateways | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Letta Code](https://github.com/letta-ai/letta-code/tree/ad308cd3cb8486afa0bb8ad624c690b828339ea7) | สร้าง stateful agent harness ที่มี memory, skills, channels และ scheduling | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Connect browser or voice

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [Browser Use](https://github.com/browser-use/browser-use/tree/7fdd63c03fd342aab4fe44507c77c3221ffd43c6) | ให้ Agent โต้ตอบ browser จริงและอ่านผลผ่าน browser harness | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Stagehand](https://github.com/browserbase/stagehand/tree/c8e096cb83b6c06ad73e49583fb79a87e78bdd3c) | ใช้ observe, act และ schema-based extraction ใน browser automation | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Skyvern](https://github.com/Skyvern-AI/skyvern/tree/26d2722b0fc9c7f3246389bdf7385ef18862b242) | ทำ browser workflows ด้วย vision/LLM และ workflow builder | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [LiveKit Agents](https://github.com/livekit/agents/tree/065deca6364096ce0cb79fd41dc1d3e53c64850e) | สร้าง real-time voice/video Agents ที่เชื่อม STT, LLM และ TTS | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Pipecat](https://github.com/pipecat-ai/pipecat/tree/caff2b489bfbee73be0f75e9de7601490205873d) | ประกอบ streaming voice/multimodal pipelines และ conversation flows | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [faster-whisper](https://github.com/SYSTRAN/faster-whisper/tree/3ec025c4b7526e3fa121e527724ac43afa275a95) | ถอดเสียงด้วย Whisper ผ่าน CTranslate2 บน CPU/GPU | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Inspect MCP and TypeScript apps

| Project | ใช้ทำอะไร | Evidence to collect |
| --- | --- | --- |
| [MCP Inspector](https://github.com/modelcontextprotocol/inspector/tree/4d3464cb3a6dde609d7b5ac24c440b947eb40f23) | ตรวจและเรียก MCP servers ผ่าน web, CLI หรือ terminal interface | Version, configuration, one task result, failure behavior and data/permission boundaries |
| [Vercel AI SDK](https://github.com/vercel/ai/tree/70e45d5878494be4b66e325187f865951025059e) | ต่อ text/streaming, structured outputs, tools และ UI สำหรับแอป TypeScript | Version, configuration, one task result, failure behavior and data/permission boundaries |

## Skill starting points

| Entry | Task | Review |
| --- | --- | --- |
| [context-compression](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering/blob/9ff0c99108b36d3b886defd825d8ac1f47dba374/skills/context-compression/SKILL.md) | ออกแบบสรุปบริบทที่รักษา decision, files และงานค้าง | entry-reviewed |
| [memory-systems](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering/blob/9ff0c99108b36d3b886defd825d8ac1f47dba374/skills/memory-systems/SKILL.md) | ออกแบบความจำข้าม session, entity/time validity และ retrieval | entry-reviewed |
| [tool-design](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering/blob/9ff0c99108b36d3b886defd825d8ac1f47dba374/skills/tool-design/SKILL.md) | ออกแบบชื่อ schema, result และ error ของ tool ให้ Agent ใช้ถูก | entry-reviewed |
