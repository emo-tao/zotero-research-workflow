# Component map

Select only the components needed for the user's outcome. “Six plugins” counts the browser Connector and five Zotero extensions; Zotero itself is the host application.

| Outcome | Component | Role | Required for complete-PDF translation? |
|---|---|---|---|
| Capture a paper from the browser | [Zotero Connector](https://www.zotero.org/download/) | Save metadata and available attachments into Zotero | No |
| Improve Chinese references | [Jasminum](https://github.com/l0o0/jasminum) | Chinese bibliographic metadata and site-specific helpers | No |
| Translate a word, passage or metadata | [Translate for Zotero](https://github.com/windingwind/zotero-pdf-translate) | Quick, local-in-document translation | No |
| Translate the complete PDF | [zotero-pdf2zh](https://github.com/guaguastandup/zotero-pdf2zh) | Zotero command/UI, task submission and translated attachment handling | **Yes**, with its matching Server, engine and configured translation service |
| Write linked reading notes | [Better Notes](https://github.com/windingwind/zotero-better-notes) | Zotero note organization and export features | No |
| Export citations to LaTeX | [Better BibTeX](https://github.com/retorquere/zotero-better-bibtex) | Stable citation keys and bibliography export | No |

For the complete-PDF path, the Zotero extension is the controller. The local Server coordinates translation using an engine from the PDFMathTranslate/BabelDOC ecosystem and a configured translation service. Exact process layout, artifact names and supported engines depend on the installed upstream release; inspect that release's README and configuration instead of assuming a fixed ZIP layout.

Selected-text translation and complete-PDF translation solve different needs. If the user only wants to understand one paragraph, avoid running a whole document. If the user needs a citable translated copy or bilingual reading file, use the complete-PDF path and check the resulting artifact.

