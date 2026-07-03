# Sharva-Astra Rebranding Record

This repository is a TCS-internal fork of [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) (MIT licensed).
To keep future merges with upstream simple and conflict-free (`git fetch upstream && git merge upstream/main`), all rebranding changes are strictly cosmetic. 

This document tracks all files modified, string translations, and load-bearing code structures/identifiers that were deliberately left untouched.

---

## Retained Upstream Abstractions (Do Not Rename)

The following identifiers, variables, file paths, configurations, and commands remain identical to upstream to avoid structural breaks:

- **Python Classes & Core Logic**: e.g., `class HermesAgent`, module names `hermes_cli`, `hermes_constants`, `toolsets.py` etc.
- **Constant Names**: Constant names like `HERMES_AGENT_LOGO`, `DEFAULT_AGENT_IDENTITY`, and `HERMES_AGENT_HELP_GUIDANCE` retain their exact upstream variable names; only the string values they store have been rebranded.
- **Configuration Keys**: `config.yaml` layout, display keys (like `skin`), and environment variables (like `HERMES_SKIN`, `HERMES_HOME`, etc.) remain unchanged.
- **Directory Paths**: The default config/secrets home directory remains `~/.hermes/` and its subdirectories.
- **Credits & Billing Output**: The commands `/credits` and `/billing` interact with the **Nous Portal** backend. Their help descriptions are slightly updated, but their internal logic and output strings (e.g. `"Not logged into Nous Portal"`, `"Nous credits"`) remain exactly as upstream. Changing these labels to "Sharva-Astra credits" would create confusion since they represent actual Nous Portal accounts, not TCS-internal balances.

---

## File Modifications & Rationales

| File Path | Change Summary & Rationale |
| :--- | :--- |
| [hermes_cli/banner.py](file:///d:/sharva/Sharva-Astra/hermes_cli/banner.py) | Updated the default ASCII logo stored in `HERMES_AGENT_LOGO`, the version label text format, and changed the printed author string `"Nous Research"` to `"TCS"` inside the welcome banner. |
| [hermes_cli/skin_engine.py](file:///d:/sharva/Sharva-Astra/hermes_cli/skin_engine.py) | Rebranded the default branding options for built-in skins (`default`, `mono`, `slate`, `daylight`, `warm-lightmode`) from `"Hermes Agent"` to `"Sharva-Astra"`. Implemented env var check `SHARVA_DEFAULT_SKIN` falling back to `HERMES_SKIN`. |
| [hermes_cli/_parser.py](file:///d:/sharva/Sharva-Astra/hermes_cli/_parser.py) | Rebranded top-level CLI argument parser help strings and description text to `"Sharva-Astra"`. |
| [hermes_cli/commands.py](file:///d:/sharva/Sharva-Astra/hermes_cli/commands.py) | Rebranded `/snapshot`, `/goal`, `/update`, and `/version` command help descriptions in the central registry. /credits and /billing left alone. |
| [hermes_cli/doctor.py](file:///d:/sharva/Sharva-Astra/hermes_cli/doctor.py) | Updated doctor diagnosis headers, check warnings, and the basic template generated for new `SOUL.md` personas. |
| [hermes_cli/subcommands/*](file:///d:/sharva/Sharva-Astra/hermes_cli/subcommands) | Rebranded `acp.py`, `config.py`, `dashboard.py`, `debug.py`, `doctor.py`, `setup.py`, `status.py`, `uninstall.py`, and `update.py` subcommand argument descriptions and help strings. |
| [hermes_cli/status.py](file:///d:/sharva/Sharva-Astra/hermes_cli/status.py) | Rebranded the diagnostic CLI status printed header block and docstrings. |
| [hermes_cli/setup.py](file:///d:/sharva/Sharva-Astra/hermes_cli/setup.py) | Rebranded interactive setup wizard welcome banners and prompts. |
| [hermes_cli/uninstall.py](file:///d:/sharva/Sharva-Astra/hermes_cli/uninstall.py) | Rebranded user-visible strings, console notifications, and goodbye prompts in the uninstaller tool. |
| [hermes_cli/default_soul.py](file:///d:/sharva/Sharva-Astra/hermes_cli/default_soul.py) | Rebranded the default seeded persona template file. |
| [agent/prompt_builder.py](file:///d:/sharva/Sharva-Astra/agent/prompt_builder.py) | Updated default system persona (`DEFAULT_AGENT_IDENTITY`) and capabilities guidance (`HERMES_AGENT_HELP_GUIDANCE`) to reflect `"Sharva-Astra"` and TCS, while retaining upstream credit and pointing to the repository link. |
| [README.md](file:///d:/sharva/Sharva-Astra/README.md) | Updated project descriptions, logo alt texts, links, badges, and top-level summary. |

---

## String Translation Map

| Upstream Term / Reference | Rebranded Term / Reference |
| :--- | :--- |
| `"Hermes Agent"` | `"Sharva-Astra"` |
| `"Nous Research"` | `"TCS"` (for branding blocks / welcome headers) |
| `"https://hermes-agent.nousresearch.com/"` | `"https://github.com/Abhi112ss/Sharva-Astra"` |
| `"https://hermes-agent.nousresearch.com/docs/"` | `"https://github.com/Abhi112ss/Sharva-Astra"` |
| `"You are Hermes, a helpful AI assistant."` | `"You are Sharva-Astra, a helpful AI assistant."` |
