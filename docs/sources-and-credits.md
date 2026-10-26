# Sources and credits

This repository contains original workflow instructions prepared by `emo-tao` from a personal Windows Zotero setup and troubleshooting record. It does not copy upstream source code, plugin binaries, icons or translated PDFs. Names identify independent third-party projects; please follow each project's own documentation and license for software redistribution or modification.

| Component | Upstream project / publisher | Used here for |
|---|---|---|
| Zotero and Zotero Connector | [Zotero](https://www.zotero.org/download/) and [official plugins guide](https://www.zotero.org/support/plugins) | Library host, browser capture, plugin installation guidance |
| Jasminum（茉莉花） | [l0o0/jasminum](https://github.com/l0o0/jasminum) | Chinese bibliographic workflow |
| Better BibTeX | [retorquere/zotero-better-bibtex](https://github.com/retorquere/zotero-better-bibtex) | Citation keys and bibliography export |
| Better Notes | [windingwind/zotero-better-notes](https://github.com/windingwind/zotero-better-notes) | Linked note workflow |
| Translate for Zotero | [windingwind/zotero-pdf-translate](https://github.com/windingwind/zotero-pdf-translate) | Selected-text translation |
| zotero-pdf2zh | [guaguastandup/zotero-pdf2zh](https://github.com/guaguastandup/zotero-pdf2zh) | Whole-PDF Zotero plugin and Server workflow |
| PDF translation engine ecosystem | [PDFMathTranslate/PDFMathTranslate-next](https://github.com/PDFMathTranslate/PDFMathTranslate-next) and [BabelDOC](https://github.com/funstory-ai/BabelDOC) | Engine/background for translated PDF generation; confirm the engine actually selected by the installed Server |
| uv | [Astral uv documentation](https://docs.astral.sh/uv/) and [`uv pip check`](https://docs.astral.sh/uv/pip/inspection/) | Python environment diagnostics when applicable |

The setup cases about an old `python` on `PATH`, an interrupted `uv` installation, `bitstring`, and a damaged `scikit-learn` installation came from that personal record. They are examples of diagnostic reasoning, not claims that all versions of these upstream packages have the same defect.

Before publishing instructions based on a new upstream release, check its release notes and update any changed plugin names, Server layout, engine commands, or compatibility claims here.

