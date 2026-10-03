# CallForMe

**Let your agent call businesses for you.** CallForMe is a remote MCP server that gives Claude, ChatGPT, Codex, Cursor, Gemini CLI or any MCP client a phone. Your agent says who to call and what to get done; a voice assistant places the call, gets through the phone menu, waits on hold, asks your agent mid-call when the business needs something, and returns structured answers plus a transcript.

- Website: https://callforme.tel
- MCP server: `https://callforme.tel/mcp` (OAuth that asks for nothing)
- Agent Skill: [`skills/callforme/SKILL.md`](skills/callforme/SKILL.md) (also at https://callforme.tel/skill.md)
- REST API: https://callforme.tel/docs/rest-api
- Official MCP Registry: `tel.callforme/callforme`

![Parallel quotes](assets/parallel-quotes.png)

## What you can ask

- "Call the 3 closest auto shops and get brake quotes for my 2019 RAV4." (finds them and calls in parallel)
- "Book a table for 4 at 7:30 on Friday."
- "Cancel my gym membership and get the confirmation number."
- "Sit on hold with the airline and patch me in when a person answers."
- "Call 10 pharmacies near me and ask who has my prescription in stock."

Every call opens with "Hi, this is an AI assistant calling for [your name], on a recorded line." It switches to Spanish on its own and calls back in other languages when the business speaks one.

## Install

| Agent | How |
|---|---|
| Claude (claude.ai, desktop, mobile) | Settings → Connectors → Add custom connector → `https://callforme.tel/mcp` |
| Claude Code | `claude mcp add --transport http callforme https://callforme.tel/mcp` |
| ChatGPT | Settings → Security and login → Developer mode on, then chatgpt.com/plugins → + → Create custom MCP server → Create MCP App → `https://callforme.tel/mcp`, OAuth |
| Codex | `codex mcp add callforme --url https://callforme.tel/mcp` |
| Gemini CLI | `gemini mcp add --transport http callforme https://callforme.tel/mcp` |
| Cursor, Windsurf, VS Code, Cline, Goose, others | Add a remote MCP server with URL `https://callforme.tel/mcp` |
| Agents with a shell but no MCP | Use the skill in `skills/callforme/` with the REST API |

More: https://callforme.tel/agents

## Try it free

Five fictional businesses (a pizza place, three auto shops and a gym) can be called for free with no setup: https://callforme.tel/demo

## Pricing

$1 per answered call, including the first 5 minutes, then $0.25 a minute. No charge if nobody answers. Prepaid: the first real call shows a one-time link to add $10 through Stripe; auto-reload is on by default and adjustable. Details: https://callforme.tel/docs/pricing

## Safety

- Calls only go to businesses in the US and Canada. Emergency and premium-rate numbers are blocked.
- No calls between 10pm and 7am at the business, unless you say it's open (24-hour places).
- Card numbers, security codes, one-time codes and passwords are never read to a business.
- Businesses can opt out at https://callforme.tel/for-businesses or by asking on a call.

## Support

hello@greatwork.company. CallForMe is made by Great Work LLC.

## License

The skill and the files in this repository are MIT licensed. The CallForMe service itself is hosted and is not open source.
