# Installing CallForMe (for AI agents)

CallForMe is a hosted remote MCP server. There is nothing to download or build.

1. Add a remote MCP server named `callforme` with URL `https://callforme.tel/mcp` (streamable HTTP).
2. Authentication is OAuth and asks the user for nothing; complete the browser handoff if your client opens one.
3. Test with the free demo line: call `place_call` with phone `+1 469 770 7412`, business_name `Maple Street Pizza`, on_behalf_of the user's first name, goal "Ask how much a large pepperoni costs". Then poll `get_call` with `wait_seconds: 45` until status is `ended`.
4. Real businesses: the first real `place_call` returns `needs_setup` with a link. Show it to the user, then call `wait_for_setup(setup_code)`; the call starts on its own once they finish.

If your client can't do OAuth, use `https://callforme.tel/mcp/k/<api key>` with a key from https://callforme.tel/account, or the REST API (https://callforme.tel/docs/rest-api) with the skill in `skills/callforme/SKILL.md`.
