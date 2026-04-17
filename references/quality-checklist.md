# Thesis Quality Checklist

## Truthfulness

- Every function described exists in code, screenshots, docs, or user notes.
- No module from a reference PDF is imported into the thesis unless implemented.
- No performance metric appears without a real test source.
- No experiment conclusion appears without data or logs.
- No reference is fabricated.

## Structure

- The title matches the actual project.
- The abstract names the real stack and implemented functions.
- The outline reflects useful reference-template patterns without copying unsupported template facts.
- The final deliverable is Markdown-only unless the user explicitly requested another format.
- The Markdown heading hierarchy can be converted to Word without manual restructuring.
- The related-technology chapter covers only technologies used by the project.
- Requirement analysis maps to implemented user flows.
- Database design matches models or SQL exactly.
- Interface design uses real routes, methods, and data contracts.
- Testing chapters distinguish completed tests from pending tests.

## Diagrams

- Architecture diagram matches actual frontend, backend, AI/tool, and database boundaries.
- E-R diagram includes only real tables/entities.
- Sequence diagrams follow real request order.
- Flowcharts do not invent branches absent from code.
- Final structural diagrams are draw.io-first: use draw.io MCP when available, or provide diagrams.net-compatible `.drawio` source files when MCP is unavailable.
- Raw Mermaid is not left in the final thesis body for UML, architecture, E-R, DFD, sequence, activity, module, deployment, or algorithm figures unless the user explicitly asks for Mermaid.
- Each diagram has source or a durable generated artifact path plus a thesis-style caption/placeholder.
- Diagram labels are short enough for A4 Word pages and avoid long sentence nodes, oversized vertical chains, heavy shadows, cartoon icons, or low-contrast colors.
- Figure numbering is continuous or marked for final layout.
- Every diagram, screenshot placeholder, exported image, and table has a caption.

## Language

- Terms are consistent across chapters.
- Sentences are formal, objective, and concise.
- Design decisions include rationale.
- Implementation sections explain data flow and control flow.
- Limitations are honest and technically specific.
- Chinese prose is Word-friendly: full-width Chinese punctuation, short paragraphs, no Markdown-only visual tricks that break after Word conversion.
- Remove obvious AI-sounding filler such as exaggerated praise, repetitive "本文首先...然后...最后...", empty "显著提升" claims, and generic large-model slogans without evidence.
- Preserve technical meaning while polishing; do not rewrite grounded implementation details into prettier but unsupported statements.
- Avoid old-fashioned or ornate wording unless the reference template clearly uses it.
- Figure and table titles are concise noun phrases, not long explanatory sentences.

## Final Assembly

- All "待补充" markers are either resolved or intentionally kept.
- Screenshot placeholders are clear enough for the user to capture the right image.
- References are checked against real sources.
- Appendix content does not expose secrets, API keys, or private credentials.
- No automatic `.docx` export is performed unless explicitly requested.
- Run a reviewer-style pass before delivery: separate must-fix truthfulness/logic/format issues from optional wording polish, and do not overclaim when evidence is absent.
