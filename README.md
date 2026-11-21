# AiPASS Gemini Enterprise custom recipe

[Enterprise recipe JSON](aipass-enterprise.recipe.json) · Version 1.0.17

## Setup

Import the JSON from Transgentic Settings. Use **Sync AiPASS Gemini Enterprise** with the Chrome profile signed in to the intended tenant. Enterprise uses a separate browser partition from regular AiPASS. Open the Enterprise drawer and confirm the signed-in composer loads before sending MCP requests. Reimport the workspace JSON after changes to update the installed recipe.

## Supported workflows

| Mode | Behavior |
| --- | --- |
| General and Coding | Uses the Enterprise chat composer. Live MCP checks verified a text reply, an uploaded text-file marker, and interpretation of a synthetic PNG. Explicit Argon selection remains unverified after an earlier pre-submit failure. |
| Image | Activates the native **Create images** tool using the current provider selection. Accepts one PNG, JPEG, or WebP reference. |
| Video | Activates the native **Create videos** tool using the current provider selection. Accepts one PNG, JPEG, or WebP keyframe. |
| Music | Unsupported in the verified tenant chat. |

The recipe uses open shadow DOM to locate the Enterprise composer and response. If media setup fails before submission, check that the selected tenant is still signed in and that the native creation tool is available in the drawer.

## Verification

MCP saved valid JPEGs from native image generation, including a run with a reference. The 1.0.17 Video keyframe test saved a playable eight-second 1280 × 720 MP4 with the expected blue first frame. The MCP catalog exposed the current provider selection, and the file did not identify the generating model. See the [verification log](aipass-verification.md) for details.
