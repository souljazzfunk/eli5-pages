# eli5-pages

ELI5 explainer pages for two videos. Each page has a JA/EN toggle in one file. On load the language comes from `?lang=ja|en`, then from the saved choice in localStorage (`eli5-lang`), then from the browser language.

- [Grok Bot 201](): `grok-bot-201/` (`index.html`, `outline.md`)
- [Grok Bot for Marketing](): `grok-bot-marketing/` (`index.html`, `outline.md`)

The old per-language URLs (`grok-bot-201/eli5-ja.html`, `eli5-en.html`, `grok-bot-marketing/grok-bot-marketing.ja.html`, `grok-bot-marketing.en.html`) redirect to `./index.html?lang=ja|en`.
