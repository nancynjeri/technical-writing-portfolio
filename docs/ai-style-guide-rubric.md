# Style Guide & Evaluation Rubric for AI-Assisted Documentation

This guide defines the formatting conventions, structural restrictions, and stylistic constraints used to generate and evaluate technical documentation drafts using Large Language Models (LLMs).

## 1. Tone and Voice Parameters
When engineering prompts or auditing AI-generated drafts, enforce the following linguistic constraints:

*   **Active Voice:** Position the user as the actor performing the execution.
    *   *Incorrect:* "The database configuration file should be modified by the developer."
    *   *Correct:* "Modify the database configuration file."
*   **Eliminate Fluff:** Avoid introductory pleasantries or speculative sentences (e.g., "In this section, we will easily try to look at..."). Dive straight into the technical assertion.

## 2. Markdown Snippet Engineering Rules
AI models frequently introduce formatting errors inside complex markdown trees. All code blocks must adhere to strict syntax parsing markers.

### Code Block Restrictions
Every code block must include an explicit language tag for proper syntax highlighting. 

```json
// Example of strict JSON formatting configuration enforced during automated linting
{
  "parser": "markdown-linter",
  "rules": {
    "no-missing-language-tags": true,
    "require-fenced-code-blocks": true
  }
}
```

## 3. Editorial Assessment Rubric
Use this 3-tier scoring system to evaluate human-written and machine-generated documentation contributions during content QA pipelines:

1.  **Grade A (Production-Ready):** Completely accurate technical assertions, zero formatting violations, contains clear code inputs alongside expected outputs, and maintains a strict task-based structure.
2.  **Grade B (Needs Revision):** Technically accurate but lacks visual anchors, contains multi-sentence structural blocks that should be split into punchy bullet points, or misses explicit error-handling paths.
3.  **Grade C (Rejected):** Contains technical hallucinations, uses passive phrasing, lacks step-by-step setup criteria, or exposes sensitive parameters.
