---
name: graduation-thesis-writer
description: Write, polish, audit, and diagram high-quality Markdown-only Chinese undergraduate graduation theses from project code, database schemas, APIs, screenshots, PDFs, and user notes. Use when the user asks to audit materials, learn from reference thesis templates, create a thesis outline, draft chapters, prepare draw.io diagrams, improve Chinese academic expression, remove AI-sounding Word-style text, generate figure/table captions, prepare references, testing sections, reviewer-style checks, or Word-convertible Markdown thesis text for software, AI, large-model, web, mobile, or data-system projects.
---

# Graduation Thesis Writer

## Purpose

Use this skill to produce a rigorous, code-faithful Chinese undergraduate graduation thesis as a single high-quality Markdown document that can later be converted to Word. Treat the implemented project as the source of truth, and use reference PDFs, Word templates, school examples, and excellent thesis samples to learn structure, academic tone, formatting patterns, chapter depth, and figure/table habits.

Do not generate `.docx` by default. Produce Markdown as the primary and final artifact unless the user explicitly asks for another format.

## Source Priority

Follow this order when deciding what may be stated as fact:

1. Source code, database models, migrations, SQL scripts, tests, and runtime behavior.
2. Configuration files, dependencies, API definitions, prompts, deployment scripts, and logs.
3. README files, design documents, comments, screenshots, and generated artifacts.
4. Explicit user-provided explanations.
5. Reference PDFs, Word templates, school examples, and excellent thesis samples for chapter structure, paragraph organization, style, and formatting habits only.

When evidence is missing, write "待补充信息" or "此处需用户补充..." instead of inventing features, metrics, experiments, references, or conclusions.

## Required Workflow

### 1. Audit Materials First

Before drafting the thesis body, inspect available code and materials. Identify:

- Project type and thesis topic.
- Frontend, backend, database, AI/model, deployment, and third-party service stack.
- Core modules, classes, functions, APIs, schemas, tables, prompts, and workflows.
- Screenshots, PDFs, reports, logs, and test data that can support thesis figures or results.
- Missing evidence and which chapters it affects.

If the materials are insufficient for a full thesis, output a "材料审计与缺口报告" and limit drafting to safe chapters.

For deeper workflow details, read `references/workflow.md`.

### 2. Learn From Reference Templates

Before producing the final outline, extract reusable writing and formatting patterns from the user's reference templates:

- Chapter sequence and naming conventions.
- Abstract length, keyword style, and bilingual abstract pattern.
- Depth of literature review and related-technology explanation.
- Figure/table numbering style, caption style, and placement habits.
- Requirement-analysis, database-design, implementation, and testing-section organization.
- School-specific formatting constraints, if a template is provided.

Never copy project facts, experimental results, references, business modules, or algorithm claims from a template unless the user's own project materials support them.

For detailed template-learning rules, read `references/template-learning.md`.

### 3. Build a Four-Level Outline

After the audit, output a detailed outline before writing chapters. The outline must:

- Include headings down to four levels where useful.
- Tie every major section to verified project implementation.
- Add a short "拟写内容" note after second- or third-level headings.
- Mark required figures, tables, formulas, screenshots, sequence diagrams, E-R diagrams, architecture diagrams, and flowcharts.
- Mark unsupported parts as "待补充".

Wait for user confirmation before drafting chapters unless the user explicitly asks to continue without confirmation.

### 4. Draft Chapter by Chapter

For each chapter:

- Start with the chapter writing goal.
- Write formal, objective academic Chinese.
- Convert code facts into academic prose instead of copying code.
- Insert figure/table placeholders where appropriate.
- Use a draw.io-first strategy for formal thesis figures. For architecture diagrams, UML use-case/activity/sequence/class/state diagrams, DFDs, E-R diagrams, module diagrams, business workflows, deployment diagrams, and algorithm workflows, the final Markdown should point to a `.drawio`, `.svg`, or `.png` artifact. For a Word-convertible final thesis, do not leave structural figures as raw Mermaid code blocks in the body.
- When draw.io MCP is available, use it to create polished diagrams. When no draw.io MCP tool is callable, create diagrams.net-compatible `.drawio` XML files in the project (for example `论文/drawio/图X-X_图名.drawio`) and reference them from the figure placeholder. Mermaid may be used only as a private drafting aid or for quick analysis, not as the final visible thesis diagram format unless the user explicitly requests Mermaid.
- If the user asks to improve figure quality or says Mermaid diagrams are ugly/too tall, convert every structural figure in the relevant chapters to draw.io sources, including existing simple sequence, state, class, component, E-R, deployment, and page-navigation diagrams. Keep screenshot figures as screenshot placeholders rather than draw.io files.
- Keep diagrams Word-page friendly: prefer horizontal swimlanes, staged matrices, two-row pipelines, compact component groups, and split subfigures over tall vertical chains. Avoid `mindmap` Mermaid for thesis deliverables because it is less stable across renderers.
- Every figure, exported diagram, screenshot placeholder, and image must have a visible caption using the thesis template style, plus an insertion placeholder that states the source file or required screenshot.
- Apply conservative Chinese academic polishing: fix口语化、语病、逻辑断层、翻译腔和明显 AI 味, but do not rewrite already clear paragraphs just to sound more "advanced". Prefer plain, accurate, modern academic Chinese over ornate or old-fashioned wording.
- Generate concise figure and table titles. Captions should directly identify the object and purpose, avoid empty phrases such as "展示了", "可以看出", or promotional wording, and keep numbering consistent with the chapter.
- Keep claims proportional to evidence.

For algorithm or AI-agent sections, include:

- Design motivation.
- Principle and workflow.
- Key formulas only when they reflect real logic.
- Mapping between implementation and thesis description.

For system implementation sections, include:

- Module responsibilities.
- Key classes, APIs, data structures, and interactions.
- Data flow and error handling.
- Screenshot placeholders.

### 5. Handle References Carefully

Never fabricate references. Use only real, verifiable sources from authoritative venues or official documentation. If citations have not been verified, create a "待核验参考文献位" list instead of a fake bibliography.

### 6. Final Consistency Check

Before final delivery, check:

- Terms, module names, and technology names are consistent.
- Functions and tables match the code.
- Diagrams match real architecture.
- Test results come from real evidence.
- No unsupported performance numbers, experiment conclusions, or invented modules remain.
- Reviewer-style risk pass: identify fatal or material issues first, including unsupported claims, weak evidence, inconsistent contribution statements, missing tests, unclear diagrams, or AI-sounding prose. Ignore purely cosmetic changes unless they affect Word conversion or academic readability.

Use `references/quality-checklist.md` before final thesis assembly.

For Markdown deliverable standards, read `references/markdown-output.md`. For diagram strategy, read `references/diagramming.md`. For Chinese polishing, AI-tone removal, captions, and reviewer-style language checks, read `references/writing-polish.md`.

## Default Thesis Shape

Adapt the structure to the project, but prefer:

1. 摘要
2. Abstract
3. 第1章 绪论
4. 第2章 相关技术与理论基础
5. 第3章 需求分析
6. 第4章 系统总体设计
7. 第5章 核心算法与关键技术实现
8. 第6章 系统实现
9. 第7章 系统测试与结果分析
10. 第8章 总结与展望
11. 参考文献
12. 附录

If the project has no self-trained model or experimental algorithm, do not force a deep-learning experiment chapter. Rename the chapter to "核心流程与关键技术实现" or another code-faithful title.

## Output Contract

The final artifact should be one Markdown file in the user's target project directory. It should be directly convertible to Word after:

- Replacing diagram placeholders with exported draw.io images first; use Mermaid-exported images only for simple fallback diagrams.
- Replacing screenshot placeholders with real screenshots.
- Applying the school's Word style template.

Do not make the final body depend on raw Mermaid code blocks for major diagrams. If a diagram is visually important, long, renderer-sensitive, or likely to occupy too much vertical space, provide a draw.io source file or exported image path and write the body as a formal figure placeholder with a caption.

Do not auto-export Word, PDF, or other formats unless the user explicitly requests it.
