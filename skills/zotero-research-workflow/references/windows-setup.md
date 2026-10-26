# Windows setup and end-to-end verification

Use this only for setup, upgrade or acceptance testing. Start from the components already installed on the user's machine; do not overwrite a working library or existing Zotero profile.

## Before changing anything

Record the active Zotero version, Windows/PowerShell version, installed Zotero extensions, zotero-pdf2zh plugin and Server versions, Server URL/port, translation engine, and configured service **name** (never print its API key). Check the current [Zotero plugin installation guide](https://www.zotero.org/support/plugins) and the matching [zotero-pdf2zh release notes](https://github.com/guaguastandup/zotero-pdf2zh/releases). Install `.xpi` files from upstream releases compatible with the user's Zotero version.

If setting up whole-PDF translation, use the Server package or deployment procedure documented by the same plugin release. Pairing unrelated plugin and Server versions can produce misleading connection or task errors. Do not guess a `latest/download/...` asset name; verify the published assets first.

## Windows checks

In PowerShell, inspect interpreter resolution before installing Python packages:

```powershell
$PSVersionTable.PSVersion
Get-Command python -All
Get-Command uv -All
```

Use the Python executable from the Server's actual virtual environment for engine checks. If `uv` manages that environment, target that interpreter explicitly; `uv` may create an environment without a `pip` module:

```powershell
& <path-to-venv-python> --version
uv pip check --python <path-to-venv-python>
```

Replace placeholders with observed paths; do not paste angle brackets literally. In Windows PowerShell 5.1, issue commands on separate lines instead of using `&&`. `wget` may alias `Invoke-WebRequest`; save downloads with `Invoke-WebRequest -Uri <verified-release-asset-url> -OutFile <destination>`.

Start the Server using the procedure supplied by its release and verify its actual configured local address, commonly `http://127.0.0.1:8890` in this workflow. Keep the Server available while translating. A responsive page proves only the HTTP layer, so continue to an engine test.

## Acceptance run

Use one short, non-sensitive PDF the user is allowed to process. Confirm, in order:

1. The Zotero item has the correct source PDF and the plugin command appears.
2. The Server receives the task and the engine starts without import errors.
3. The configured translation service completes the request; distinguish service/rate-limit errors from local engine faults.
4. The translated PDF exists, opens, and is attached to the **same** source item. If bilingual output is requested, confirm that artifact too.
5. Spot-check title/abstract or a few paragraphs, at least one equation or figure caption if present, and reference text. Record layout and terminology defects for later tuning.

Report which checkpoints passed with file or UI evidence, plus any unresolved issue. A process starting or a package dependency check passing is not an end-to-end pass.

