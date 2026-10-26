# Troubleshooting from observed symptoms

Do not apply a blanket reinstall. First capture the exact error, the executable that produced it, plugin/Server/engine versions and the failed acceptance checkpoint. Preserve the user's service configuration.

| Symptom | First checks | Targeted next step |
|---|---|---|
| `future feature annotations is not defined` or unexpectedly old Python | `Get-Command python -All`; compare system interpreter and Server venv interpreter versions | Invoke the Server's own supported venv Python explicitly. Do not install into the unrelated application Python found on `PATH`. |
| Server page unavailable | Confirm process is running, configured host/port, plugin URL and Windows loopback access | Start or repair the matching Server release; use the URL shown by the Server, then retry the plugin connection. |
| `uv` download timed out or install stopped halfway | Inspect the installer output, network reachability, package cache and installed environment | Retry the documented install with a reachable approved index or longer timeout, then verify the affected package and engine entry point. Cross-drive hardlink warnings alone do not prove failure. |
| `ImportError` involving `bitstring.BitStream` | Inspect installed `bitstring`, engine and BabelDOC versions, plus upstream compatibility notes | Repair the specific mismatch in the **Server venv**. The author's old case used `bitstring==4.3.1`; do not impose that pin on newer releases without confirming compatibility. |
| `ModuleNotFoundError: sklearn._config` | Confirm which interpreter starts the engine; inspect the `scikit-learn` installation and corresponding import | Repair or reinstall only the broken package group in the correct venv, then run the engine start check and sample translation. |
| `uv pip check` passes but translation fails | Read engine subprocess and Server logs, then test the smallest runnable engine command | `uv pip check` covers requirement conflicts and missing packages, not file integrity, translation service access or PDF output. |
| Translation request fails after engine starts | Examine service selection, quota, network, authentication and returned status without revealing the token | Correct service-specific configuration or choose a service authorized by the user; retry a short PDF. |
| PDF produced but not attached or formatting poor | Compare output folder, Zotero item association, attachment permissions and PDF contents | Repair attachment flow or tune translation/layout settings. Keep the original PDF and log the exact defect. |

After a repair, repeat the failed checkpoint and then the end-to-end PDF acceptance run. Stop after a repeated unexplained failure with the smallest useful error excerpt and a precise next diagnostic, rather than layering speculative package pins.

