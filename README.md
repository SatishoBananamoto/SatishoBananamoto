# Satish Patil

Since January 2026 I've been learning how AI agents behave by building prototypes with them. Before that I worked in enterprise technical sales, and I'm now moving into AI go-to-market. Most of this work comes back to one question: when should people, agents and products trust each other?

These are learning prototypes, not products.

## Public projects

**[caliber](https://github.com/SatishoBananamoto/caliber)**: Python library, CLI and MCP server.
Can an agent earn trust by showing that its confidence matches its results? The agent records predictions with a confidence level before checking them, and caliber builds a Trust Card from that record. What I learned is that calibration is easy to game with safe predictions. caliber flags those patterns but deliberately gives no single integrity score, because that number would become the new target. The [red-team tests](https://github.com/SatishoBananamoto/caliber/blob/main/tests/test_integrity_adversarial.py) record gaming strategies, including the ones that still get through.

**[persona-engine](https://github.com/SatishoBananamoto/persona-engine)**: Python library and REST API.
Can an AI persona's behaviour be tested like code? It turns Big Five traits and values into a structured plan (tone, confidence, disclosure) before any text is written. I wanted personas that answer surveys and interviews like real people, so teams could test a product before paying for market research. I stopped because models quickly improved at adapting on their own and technical debt grew. The core flaw was turning Big Five traits into intermediate values with unproven formulas, then feeding the model rigid prompt strings. Simply asking a model to role-play worked better. If I revisit this, I'd give the model the goal, what the trait values mean, and how they were derived.

## Private projects

**KV Secrets**: local credential broker for AI agents, in Python, with a CLI and an MCP server.
The agent asks for an action, and the broker checks the owner's rules, makes the call itself and returns a redacted result. By default the agent never sees the key. The lesson: owning a secret and using it are separate things.

**TryPass**: try-before-sign-up web app and OIDC provider, in TypeScript.
Each app gets a pairwise ID and a trial-eligibility flag instead of an email address. TryPass remembers which trials an account has used, which makes repeat free trials harder to farm. A one-time human check covers the basics, and stronger uniqueness checks can plug in. An independent AI review reframed it for me: the value is for companies offering costly AI trials, and the main risk is adoption.

I'm happy to walk through either private repo. Message me on [LinkedIn](https://www.linkedin.com/in/satish-patil-44231877).

## How I work with AI agents

Agents write the code. I set the problem, make the design calls and verify what they ship.

- **Unanchored reviews:** different agents plan, build, test and review, and the reviewer sees the problem, not the builder's conclusions.
- **Tests first:** "done" is defined before building starts, and builders can't loosen it.
- **Evidence over summaries:** I check claims against raw test output, logs and diffs.
- **Rules that learn:** instructions live in repo files, and a repeated mistake becomes a hook or rule that I test for effect.
- **Human sign-off:** publishing, merging to main, money and deleting anything need my yes.

Tools: mainly Claude Code and Codex; also Devin, Factory Droid and Cursor.
