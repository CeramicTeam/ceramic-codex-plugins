---
name: ceramic-search
description: Web search for AI agents using Ceramic. Use for accurate current information — news, prices, recent events, documentation, general fact checking. Trigger this skill for keywords like "latest", "recent", "look up", "search for", "find online", "what's happening".
---

# Ceramic Search

Lexical (keyword-based) search engine built for AI agents.

# Usage

1. **Rewrite the natural language query**

   Ceramic matches exact keywords — it does not interpret natural language or synonyms automatically. Convert the user's natural language query into a keyword query of **2–8 words**.

   Rules:
   - Extract specific entities, topics, locations, and dates
   - Replace conversational phrasing with concrete keywords
   - Do not include uninformative words such as articles (the, a, an). Avoid prepositions (on, about, in, for, of, at, by, with) unless they are within established phrases or names (United States of America, Into the Wild).
   - Include relevant synonyms explicitly when terminology is ambiguous
   - Keep word order meaningful (`house cat` and `cat house` return different results)
   - Good keyword query examples:
     - "2026 Super Bowl halftime performer"
     - "climate change effects global warming impact"
     - "beginner investing strategies stocks bonds basics"

2. **Call `ceramic_search` with the rewritten keyword query**

   `ceramic_search` is provided by the MCP server registered in this plugin. Call it using the MCP tool invocation mechanism — do not attempt to call it as a local function.

   Use the default `maxDescriptionLength` of 3000 characters unless the user needs more detail (max 8000).

   **Minimal call (default description length):**
   ```json
   {
     "query": "2026 Super Bowl halftime performer"
   }
   ```

   **Call with extended descriptions (for detailed research):**
   ```json
   {
     "query": "2026 Super Bowl halftime performer",
     "maxDescriptionLength": 8000
   }
   ```

3. **Retrieve the top sources from the response**

   The response is structured json with a `results` array containing up to 10 search results. Each result includes the fields `description`, `rank`, `title`, and `url`.

   ```json
   {
     "results": [
       {
         "description": "search result description",
         "rank": 1,
         "title": "search result title",
         "url": "search result url"
       },
       ...
     ]
   }
   ```

4. **Summarize with citations**

   Write a concise answer drawing from the search result descriptions, and then list sources as numbered references:

   **Sources**
   1. [Title](url)
   2. [Title](url)

   Only cite sources whose descriptions contributed to the answer. If the search returns no useful results, refine the query with more specific keywords and try again before giving up.