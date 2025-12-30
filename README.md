# Reddit Pain Point Research Workflow

Personal n8n automation for analyzing public Reddit posts to identify common pain points in enterprise software discussions (e.g., real estate, ERP, startups). Complies with Reddit Responsible Builder Policy: non-commercial, public data only, no user interaction.[1]

## Workflow Overview
Manual trigger → Reddit search → AI analysis (Gemini) → Google Sheets logging. Fetches posts from targeted subreddits, extracts pain points via LLM, appends structured insights.[1]

## Key Nodes
- **Reddit Search**: Queries public posts (e.g., "ERP pain point", "real estate frustration").
- **AI Agent + Gemini**: Classifies sentiment, extracts quotes, scores severity.
- **Google Sheets**: Logs: subreddit, post title, pain point, evidence, date.
- **Rate Limiting**: Respects 100 QPM via n8n delays.[1]

## Setup Instructions
1. Import `Pain-Point-hunter.json` into n8n.
2. Configure Reddit OAuth2 credentials (post-API approval).
3. Add Google Gemini API key.
4. Set Google Sheets document/sheet ID.
5. Test with manual trigger.[1]

## Targeted Subreddits
- r/realestate
- r/ERP
- r/startups
- r/SaaS
- r/indianstartups [conversation_history]

## Compliance Notes
- **Personal Use Only**: No commercialization, AI training, or data sales.
- **Data Retention**: Delete sheets weekly per RBP.
- **No Interaction**: Read-only, public posts/comments.
- **Rate Limits**: 50 queries/day max.[2]

## Screenshots
![Workflow Diagram](

![Sample Output](screenshots/sheets-output
MIT - Personal research only. Not for production/commercial use.

```
## Usage Example Output
| Subreddit    | Pain Point          | Quote Excerpt                  | Score |
|--------------|---------------------|--------------------------------|-------|
| r/realestate | Manual invoicing   | "Hate doing invoices manually" | 8/10  |
| r/ERP        | Integration issues | "ERP won't sync with CRM"      | 9/10  |
```

**For Reddit API approval: Attach this README + JSON export.** Demonstrates transparent, compliant personal research tool.[1]

[1](https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/29545872/813e1ed5-7bff-469d-ae4a-a5ce76b79862/Pain-Point-hunter.json)
[2](https://support.reddithelp.com/hc/en-us/articles/42728983564564-Responsible-Builder-Policy)
