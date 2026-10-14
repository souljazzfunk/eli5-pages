# eli5-pages

ELI5 explainer pages for two videos. Each page is one file with a three-button switcher: JA / EN / Both (Both shows Japanese with English underneath), plus a Light/Dark toggle. On load the language comes from `?lang=ja|en|both`, then from the saved choice in localStorage key `eli5-lang` (shared by both pages; written when you click a button), then from the browser language (`ja*` → JA, otherwise EN).

- [Grok Bot 201](): `grok-bot-201/` (`index.html`, `outline.md`)
- [Grok Bot for Marketing](): `grok-bot-marketing/` (`index.html`, `outline.md`)

The old per-language URLs (`grok-bot-201/eli5-ja.html`, `eli5-en.html`, `grok-bot-marketing/grok-bot-marketing.ja.html`, `grok-bot-marketing.en.html`) redirect to `./index.html?lang=ja|en`.
