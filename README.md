# eli5-pages

Simple picture explainers ("explain like I'm 5") for two webinars:

- Grok Bot 201: `grok-bot-201/` (`index.html`, `outline.md`)
- Grok Bot for Marketing: `grok-bot-marketing/` (`index.html`, `outline.md`)

The root `index.html` links to both pages.

Every page, including the root, has a three-button switcher: JA / EN / Both (Both shows Japanese with English underneath), plus a Light/Dark toggle. On load the language comes from `?lang=ja|en|both`, then from the saved choice in localStorage key `eli5-lang` (shared by all pages; written only when you click a button), then from the browser language (`ja*` → JA, otherwise EN).
