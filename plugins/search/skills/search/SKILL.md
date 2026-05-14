---
name: search
description: Search the web using Ceramic and return a summary with cited sources.
---

Use this skill whenever you need current or external context to answer accurately — including when the user asks you to search, when your knowledge may be outdated, or when the task requires facts you cannot reliably recall. Follow these steps:

1. **Rewrite the query** for Ceramic's lexical (keyword-based) search engine before calling the tool. Ceramic matches exact keywords — it does not interpret natural language or synonyms automatically. Generate a keyword query of **2–10 words**.
   - Extract specific entities, topics, locations, and dates from the user's request
   - Replace conversational phrasing with concrete keywords
   - Include relevant synonyms explicitly when terminology is ambiguous
   - Keep word order meaningful (`house cat` and `cat house` return different results)
   - Examples of good keyword queries:
     - "2026 Super Bowl halftime performer"
     - "California tenant security deposit return law"
     - "OAuth 2.0"
     - "Serena Williams Grand Slam titles"
     - "California rent increase causes housing shortage 2025"

2. **Call `ceramic_search`** with the rewritten keyword query. Use the default `maxDescriptionLength` of 3000 unless the user needs more detail (max 8000). The tool returns up to 10 results ranked by relevance.

3. **Retrieve top sources** from the `results` array. Each result includes `rank`, `title`, `url`, and `description`.

4. **Summarize with citations** — write a concise answer drawing from the result descriptions, then list sources as numbered references:

   **Sources**
   1. [Title](url)
   2. [Title](url)

Only cite sources whose descriptions contributed to the answer. If the search returns no useful results, refine the query with more specific keywords and try again before giving up.
