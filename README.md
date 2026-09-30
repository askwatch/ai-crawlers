# AI crawlers list

Every AI crawler worth a line in robots.txt: the token to write, who runs it, what it is for, whether it says it obeys robots.txt, its documented user-agent string, where the operator publishes its IP ranges, and how to verify it by reverse DNS.

26 bots from 13 operators. Every string and address was read off the operator's own documentation on 2026-09-29; where an operator publishes nothing, the field is `null` rather than something copied from server logs.

The same catalogue, with a page per bot and a check of your own robots.txt against all of them: **[askwatch.ai/ai-crawlers](https://askwatch.ai/ai-crawlers?ref=github)**.

## Files

| File | What |
| --- | --- |
| [`ai-crawlers.json`](ai-crawlers.json) | The full catalogue: bots, legacy tokens, and names people write that no crawler sends |
| [`ai-crawlers.csv`](ai-crawlers.csv) | The bots as a table |
| [`robots/block-ai-training.txt`](robots/block-ai-training.txt) | Stay in search and AI answers, keep pages out of model training |
| [`robots/block-all-ai.txt`](robots/block-all-ai.txt) | Block training, AI search and user fetches; Google Search and AI Overviews stay |

## The four groups

- **Search engines** crawl for a search index. Googlebot also feeds AI Overviews and AI Mode, so blocking it removes you from both.
- **AI search and answers** crawl so an AI answer can cite the page. Blocking them keeps you out of those answers.
- **AI training** collects text a model is trained on. Blocking it keeps you out of the next model, not out of today's answers.
- **Fetches on a user's request** read a page because a person asked an assistant to. Several operators say robots.txt may not apply to these.

### Search engines

| Token | Operator | What it is for | Obeys robots.txt | IP ranges | Source |
| --- | --- | --- | --- | --- | --- |
| [Googlebot](https://askwatch.ai/ai-crawlers/googlebot?ref=github) | Google | Google Search, including AI Overviews and AI Mode | yes | [list](https://developers.google.com/static/search/apis/ipranges/googlebot.json) | [docs](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) |
| [Bingbot](https://askwatch.ai/ai-crawlers/bingbot?ref=github) | Microsoft | Bing search, which also feeds Copilot | yes | [list](https://www.bing.com/toolbox/bingbot.json) | [docs](https://www.bing.com/webmasters/help/which-crawlers-does-bing-use-8c184ec0) |
| [Applebot](https://askwatch.ai/ai-crawlers/applebot?ref=github) | Apple | Spotlight, Siri and Safari suggestions | yes | [list](https://search.developer.apple.com/applebot.json) | [docs](https://support.apple.com/en-us/119829) |
| [DuckDuckBot](https://askwatch.ai/ai-crawlers/duckduckbot?ref=github) | DuckDuckGo | DuckDuckGo search | yes | [list](https://duckduckgo.com/duckduckbot.json) | [docs](https://duckduckgo.com/duckduckgo-help-pages/results/duckduckbot) |
| [YandexBot](https://askwatch.ai/ai-crawlers/yandexbot?ref=github) | Yandex | Yandex search | yes | not published | [docs](https://yandex.com/support/webmaster/en/robot-workings/check-yandex-robots) |

### AI search and answers

| Token | Operator | What it is for | Obeys robots.txt | IP ranges | Source |
| --- | --- | --- | --- | --- | --- |
| [OAI-SearchBot](https://askwatch.ai/ai-crawlers/oai-searchbot?ref=github) | OpenAI | Pages shown and cited in ChatGPT search | yes | [list](https://openai.com/searchbot.json) | [docs](https://developers.openai.com/api/docs/bots) |
| [Claude-SearchBot](https://askwatch.ai/ai-crawlers/claude-searchbot?ref=github) | Anthropic | Search results for Claude's answers | yes | [list](https://claude.com/crawling/bots.json) | [docs](https://support.claude.com/en/articles/8896518) |
| [PerplexityBot](https://askwatch.ai/ai-crawlers/perplexitybot?ref=github) | Perplexity | Perplexity's index for cited answers, not training | yes | [list](https://www.perplexity.com/perplexitybot.json) | [docs](https://docs.perplexity.ai/guides/bots) |
| [DuckAssistBot](https://askwatch.ai/ai-crawlers/duckassistbot?ref=github) | DuckDuckGo | Sources for DuckAssist answers, not training | yes | [list](https://duckduckgo.com/duckassistbot.json) | [docs](https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot) |
| [Amzn-SearchBot](https://askwatch.ai/ai-crawlers/amzn-searchbot?ref=github) | Amazon | Search experiences in Amazon products, such as Alexa | yes | not published | [docs](https://developer.amazon.com/amazonbot) |
| [MistralAI-Index](https://askwatch.ai/ai-crawlers/mistralai-index?ref=github) | Mistral | Mistral search, which answers questions in Vibe | yes | [list](https://mistral.ai/mistralai-index-ips.json) | [docs](https://docs.mistral.ai/robots) |

### AI training

| Token | Operator | What it is for | Obeys robots.txt | IP ranges | Source |
| --- | --- | --- | --- | --- | --- |
| [GPTBot](https://askwatch.ai/ai-crawlers/gptbot?ref=github) | OpenAI | Training OpenAI's models | yes | [list](https://openai.com/gptbot.json) | [docs](https://developers.openai.com/api/docs/bots) |
| [ClaudeBot](https://askwatch.ai/ai-crawlers/claudebot?ref=github) | Anthropic | Training Anthropic's models | yes | [list](https://claude.com/crawling/bots.json) | [docs](https://support.claude.com/en/articles/8896518) |
| [Google-Extended](https://askwatch.ai/ai-crawlers/google-extended?ref=github) | Google | Gemini and Vertex AI training; no effect on Search or AI Overviews | token | not published | [docs](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers) |
| [Applebot-Extended](https://askwatch.ai/ai-crawlers/applebot-extended?ref=github) | Apple | Apple Intelligence training; Applebot reads the rule | token | not published | [docs](https://support.apple.com/en-us/119829) |
| [CCBot](https://askwatch.ai/ai-crawlers/ccbot?ref=github) | Common Crawl | The open web archive many models train on | yes | [list](https://index.commoncrawl.org/ccbot.json) | [docs](https://commoncrawl.org/ccbot) |
| [meta-externalagent](https://askwatch.ai/ai-crawlers/meta-externalagent?ref=github) | Meta | Training Meta's AI models | yes | not published | [docs](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers) |
| [Bytespider](https://askwatch.ai/ai-crawlers/bytespider?ref=github) | ByteDance | Training ByteDance's models | unknown | not published | none |
| [Amazonbot](https://askwatch.ai/ai-crawlers/amazonbot?ref=github) | Amazon | Amazon's services, including model training | yes | [list](https://developer.amazon.com/amazonbot/ip-addresses/) | [docs](https://developer.amazon.com/amazonbot) |
| [MistralAI-Training](https://askwatch.ai/ai-crawlers/mistralai-training?ref=github) | Mistral | Training Mistral's models | yes | not published | [docs](https://docs.mistral.ai/robots) |

### Fetches on a user's request

| Token | Operator | What it is for | Obeys robots.txt | IP ranges | Source |
| --- | --- | --- | --- | --- | --- |
| [ChatGPT-User](https://askwatch.ai/ai-crawlers/chatgpt-user?ref=github) | OpenAI | Pages a ChatGPT user asks it to open | partly | [list](https://openai.com/chatgpt-user.json) | [docs](https://developers.openai.com/api/docs/bots) |
| [Claude-User](https://askwatch.ai/ai-crawlers/claude-user?ref=github) | Anthropic | Pages a Claude user asks it to open | yes | [list](https://claude.com/crawling/bots.json) | [docs](https://support.claude.com/en/articles/8896518) |
| [Perplexity-User](https://askwatch.ai/ai-crawlers/perplexity-user?ref=github) | Perplexity | Pages a Perplexity user asks it to open | partly | [list](https://www.perplexity.com/perplexity-user.json) | [docs](https://docs.perplexity.ai/guides/bots) |
| [meta-externalfetcher](https://askwatch.ai/ai-crawlers/meta-externalfetcher?ref=github) | Meta | Links a user asks a Meta AI product to fetch | partly | not published | [docs](https://developers.facebook.com/docs/sharing/webmasters/web-crawlers) |
| [Amzn-User](https://askwatch.ai/ai-crawlers/amzn-user?ref=github) | Amazon | Requests a user starts in Amazon's products | partly | not published | [docs](https://developer.amazon.com/amazonbot) |
| [MistralAI-User](https://askwatch.ai/ai-crawlers/mistralai-user?ref=github) | Mistral | Pages a Vibe user's question leads it to | yes | [list](https://mistral.ai/mistralai-user-ips.json) | [docs](https://docs.mistral.ai/robots) |

## Tokens that block nothing

Rules under these names match no crawler.

| Written as | Use instead |
| --- | --- |
| `anthropic-ai` | `ClaudeBot` (Anthropic's old token; its crawler is ClaudeBot) |
| `claude-web` | `ClaudeBot` (Anthropic's old token; its crawler is ClaudeBot) |
| `facebookbot` | `meta-externalagent` (Meta's old training crawler) |
| `chatgpt` | `GPTBot`, `OAI-SearchBot`, `ChatGPT-User` |
| `openai` | `GPTBot`, `OAI-SearchBot`, `ChatGPT-User` |
| `gpt-bot` | `GPTBot` |
| `claude` | `ClaudeBot`, `Claude-SearchBot`, `Claude-User` |
| `anthropic` | `ClaudeBot`, `Claude-SearchBot`, `Claude-User` |
| `perplexity` | `PerplexityBot`, `Perplexity-User` |
| `gemini` | `Google-Extended` |
| `bard` | `Google-Extended` |
| `google-gemini` | `Google-Extended` |
| `copilot` | `Bingbot` |
| `meta` | `meta-externalagent` |
| `meta-ai` | `meta-externalagent` |
| `bytedance` | `Bytespider` |
| `tiktok` | `Bytespider` |
| `common-crawl` | `CCBot` |
| `commoncrawl` | `CCBot` |
| `mistral` | `MistralAI-User`, `MistralAI-Index`, `MistralAI-Training` |

## Tools

- [robots.txt Tester](https://askwatch.ai/free-tools/robots-txt-tester?ref=github): what each of these bots may read on your site
- [robots.txt Generator](https://askwatch.ai/free-tools/robots-txt-generator?ref=github): build a file from these groups
- [llms.txt Checker](https://askwatch.ai/free-tools/llms-txt-checker?ref=github) and [Generator](https://askwatch.ai/free-tools/llms-txt-generator?ref=github)

## Corrections

Operators rename bots and move their documentation. If something here is out of date, [open an issue](https://github.com/askwatch/ai-crawlers/issues) with a link to the operator's page.

## License

The data is [CC BY 4.0](LICENSE): use it anywhere, with a link to [askwatch.ai/ai-crawlers](https://askwatch.ai/ai-crawlers).

Maintained by [AskWatch](https://askwatch.ai/?ref=github), an AI visibility tracker.
