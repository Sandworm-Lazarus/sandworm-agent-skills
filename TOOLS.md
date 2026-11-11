# Companion tools

[Home](README.md) · [Skill catalog](CATALOG.md) · [Sources and licenses](SOURCES.md)

These are executable tools and frameworks, counted separately from agent skills. Their README/source overviews were inspected; this repository has not installed or run them. Links point to the recorded revision.

**18 tools and frameworks in 7 groups.** See [start here](docs/start-here.md) for task-oriented selections.

| Group | Tools |
| --- | ---: |
| [Personal agents](#personal-agents) | 2 |
| [Agent frameworks](#agent-frameworks) | 5 |
| [Agent memory](#agent-memory) | 2 |
| [Browser automation](#browser-automation) | 3 |
| [Voice & audio](#voice-audio) | 4 |
| [MCP development](#mcp-development) | 1 |
| [AI application SDKs](#ai-application-sdks) | 1 |

<a id="personal-agents"></a>

## Personal agents

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent/tree/60f81635c28e825a233f7bb25ed93a2579d5b547) | Agent ส่วนตัวที่ใช้ tools, memory, skills และ messaging gateways | Python/runtime, model provider และ integrations ที่เลือก. เหมาะศึกษา Agent บน VPS ที่เรียกโมเดลผ่าน API; ตรวจสิทธิ์ terminal, persistence และ channel secrets |
| [Letta Code](https://github.com/letta-ai/letta-code/tree/ad308cd3cb8486afa0bb8ad624c690b828339ea7) | สร้าง stateful agent harness ที่มี memory, skills, channels และ scheduling | Node/CLI และ provider/host configuration ตาม mode. ใช้ source ปัจจุบันแทน retired V1 server ใน letta-ai/letta; ตรวจเงื่อนไข remote/cloud features |

<a id="agent-frameworks"></a>

## Agent frameworks

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [LangGraph](https://github.com/langchain-ai/langgraph/tree/5ea88ecbcdb9fde713c3abd58850a5b7beaa24ec) | สร้าง stateful workflow ที่มี durable execution และจุดให้คนตรวจ | Python หรือ JS/TS counterpart, state store และ model provider. เป็น orchestration layer; ต้องกำหนด retry, checkpoint และ tool policy เองตามระบบ |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai/tree/f5c460d46ad9d03200371751d3d89f3ea58433de) | สร้าง typed Agents, tool calls และ structured outputs ใน Python | Python, Pydantic และ model/provider ที่รองรับ. Typed schema ไม่รับรองความถูกต้องเชิงเนื้อหา; แยก SDK จาก hosted Logfire/Gateway |
| [Agno](https://github.com/agno-agi/agno/tree/0b88f303e1ebd58a92677652fdeaddd7e7618362) | สร้าง Agent teams/workflows และให้บริการผ่าน API/MCP ด้วย AgentOS | Python, storage/runtime และ model credentials ตามการ deploy. แยก framework, AgentOS และ platform/UI features ก่อนเลือก stack |
| [CrewAI](https://github.com/crewAIInc/crewAI/tree/4254a835b1e5433d123e201928612bc692edbc3e) | จัด role-based agent collaboration และ event-driven Flows | Python และ model/tool integrations. แยก open framework จาก AMP/control-plane features; วัดประโยชน์ของหลาย Agent ด้วยงานจริง |
| [Mastra](https://github.com/mastra-ai/mastra/tree/59a60e42d5985980d1a36cf0bcddeead09283703) | สร้าง Agents, graph workflows, memory และ MCP integrations บน TypeScript | Node/TypeScript, provider credentials และ storage ตาม feature. Apache core แยก ee directories; ทดลอง suspend/resume และ retry ด้วย task สังเคราะห์ |

<a id="agent-memory"></a>

## Agent memory

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [Mem0](https://github.com/mem0ai/mem0/tree/f1791daa86d469249c9b002f62644d58a1eb96a0) | เพิ่ม memory layer ที่แยก user/session/agent context | SDK, LLM/embedding backend และ memory store. README แยก managed benchmark จาก OSS SDK; อย่าโอนคะแนน managed มาอ้างเป็นผลของ self-host |
| [Graphiti](https://github.com/getzep/graphiti/tree/ebef986a0b2360211b65751c111cacb4a7d790eb) | เก็บ entities, relationships และ facts ที่มีช่วงเวลาความถูกต้อง | Graph backend และ LLM/embedding setup ตาม integration. เหมาะข้อมูลที่เปลี่ยนตามเวลา; ออกแบบ provenance, deletion และ tenant isolation |

<a id="browser-automation"></a>

## Browser automation

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [Browser Use](https://github.com/browser-use/browser-use/tree/7fdd63c03fd342aab4fe44507c77c3221ffd43c6) | ให้ Agent โต้ตอบ browser จริงและอ่านผลผ่าน browser harness | Python/browser runtime และ LLM provider หรือ hosted service. Local library กับ Cloud เป็นคนละ deployment; session/cookies และ tool permissions ต้องตรงงาน |
| [Stagehand](https://github.com/browserbase/stagehand/tree/c8e096cb83b6c06ad73e49583fb79a87e78bdd3c) | ใช้ observe, act และ schema-based extraction ใน browser automation | JS/TS หรือ Python SDK, browser และ model provider. มี local browser และ hosted options; ตรวจ data path ของ page content และ screenshots |
| [Skyvern](https://github.com/Skyvern-AI/skyvern/tree/26d2722b0fc9c7f3246389bdf7385ef18862b242) | ทำ browser workflows ด้วย vision/LLM และ workflow builder | Browser runtime, app services และ model access. AGPL-3.0 ใน source; local/Cloud ไม่ควรถูกสมมติว่ามี feature parity |

<a id="voice-audio"></a>

## Voice & audio

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [LiveKit Agents](https://github.com/livekit/agents/tree/065deca6364096ce0cb79fd41dc1d3e53c64850e) | สร้าง real-time voice/video Agents ที่เชื่อม STT, LLM และ TTS | Agents runtime, LiveKit transport และ speech/model providers. Framework ไม่ใช่เสียงไทยสำเร็จรูป; เลือก provider แล้ววัด turn latency และ interruptions |
| [Pipecat](https://github.com/pipecat-ai/pipecat/tree/caff2b489bfbee73be0f75e9de7601490205873d) | ประกอบ streaming voice/multimodal pipelines และ conversation flows | Python, transport และ STT/LLM/TTS components. ต่อ APIs ได้โดยไม่ host ทุกโมเดลเอง; วัด end-to-end latency แยกจากแต่ละ service |
| [faster-whisper](https://github.com/SYSTRAN/faster-whisper/tree/3ec025c4b7526e3fa121e527724ac43afa275a95) | ถอดเสียงด้วย Whisper ผ่าน CTranslate2 บน CPU/GPU | Python, model files และ CTranslate2-compatible runtime. Benchmark ใน README ผูก hardware/config; ต้องวัดคำผิดและ latency กับเสียงไทยจริง |
| [CosyVoice](https://github.com/QwenAudio/CosyVoice/tree/074ca6dc9e80a2f424f1f74b48bdd7d3fea531cc) | สร้างเสียง TTS และศึกษาการ streaming/control ของ speech models | Python, checkpoint และ inference hardware/runtime ตามรุ่น. ย้ายจาก FunAudioLLM ไป QwenAudio; รายชื่อภาษาใน README ที่อ่านไม่ได้ยืนยันภาษาไทย |

<a id="mcp-development"></a>

## MCP development

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [MCP Inspector](https://github.com/modelcontextprotocol/inspector/tree/4d3464cb3a6dde609d7b5ac24c440b947eb40f23) | ตรวจและเรียก MCP servers ผ่าน web, CLI หรือ terminal interface | Node runtime ตาม engine ของ revision, MCP server/config และ connection credentials. เครื่องมืออาจเก็บ OAuth/env secrets; ตรวจ keychain หรือ encrypted storage เมื่อใช้ headless/VPS |

<a id="ai-application-sdks"></a>

## AI application SDKs

| Tool | ใช้ทำอะไร | ต้องมี / ข้อจำกัด |
| --- | --- | --- |
| [Vercel AI SDK](https://github.com/vercel/ai/tree/70e45d5878494be4b66e325187f865951025059e) | ต่อ text/streaming, structured outputs, tools และ UI สำหรับแอป TypeScript | Node 22+ ตาม README ที่อ่าน, provider adapter หรือ gateway และ UI integration ตามงาน. String model ID อาจเลือก Vercel AI Gateway; adapter โดยตรงเป็นอีกเส้นทาง ต้องบันทึก provider/billing route |
