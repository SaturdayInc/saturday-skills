# Saturday Skills

Agent Skills that pair with the **Saturday** MCP connector (`https://api.saturday.fit/mcp`),
the evidence-based endurance sports-nutrition platform. Each skill frames a domain
so Claude uses the connector's tools correctly, safely, and concisely.

## Skills

| Skill | Description |
|-------|-------------|
| [`saturday-fueling`](./saturday-fueling/SKILL.md) | Evidence-based endurance-fueling guidance for the Saturday connector — race & workout fuel plans, carb/sodium/fluid targets, product fit and comparisons, and coach roster questions. Frames high-carb/high-sodium endurance fueling as the normal, safe performance domain it is (so the assistant doesn't misapply eating-disorder caution), documents Saturday's "sole prescriber" tool contract, and the Speed Nectar base philosophy. |

## Claude Code plugin

This repo is also a **Claude Code plugin marketplace**. The `saturday` plugin bundles
the `saturday-fueling` skill *and* the Saturday connector, so one install wires up both:

```shell
/plugin marketplace add SaturdayInc/saturday-skills
/plugin install saturday@saturday-skills
```

On first use of a Saturday tool, Claude Code runs the connector's OAuth flow
(dynamic client registration — no client ID/secret to configure). A Saturday account
with an active subscription is required; see the
[connection requirements](https://docs.saturday.fit/guides/mcp-integration).

| Component | Provides |
|-----------|----------|
| Skill `saturday-fueling` | Frames the fueling domain so Claude drives the connector correctly and safely |
| MCP server `saturday` | The remote connector at `https://api.saturday.fit/mcp` (fuel plans, product fit, bottling, coach tools) |

## About Saturday

Saturday computes personalized fuel prescriptions — grams of carbohydrate,
milligrams of sodium, and milliliters of fluid per activity — for endurance
athletes and the coaches who support them. Learn more at
[saturday.fit](https://saturday.fit) · API docs at
[docs.saturday.fit](https://docs.saturday.fit).
