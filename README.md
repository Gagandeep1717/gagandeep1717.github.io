# Gagandeep C M — Portfolio Workspace

A chat-style portfolio. Choose a section from the sidebar, or ask a question in the chat box.

## Run it locally

Any static file server works. With Node installed:

```bash
npx serve -l 8123 .
```

Then open http://localhost:8123.

## Edit the content

All text lives in `assets/js/portfolio.js` in the `files` object at the top, written as Markdown. The sidebar entries are in `index.html`.

- Resume: replace `assets/files/Gagandeep_CM_Resume.pdf`.

## Live site

Published with GitHub Pages at https://gagandeep1717.github.io/ from the `main` branch of `Gagandeep1717/gagandeep1717.github.io`. Push to `main` to update it.

## Chat AI (optional)

Out of the box the chat answers from the built-in section text, and uses Gemini Nano in Chrome where available. To add a cloud model:

1. Create a Supabase project, run `supabase link --project-ref <project-ref>` and `supabase db push --linked`.
2. Add `OPENROUTER_API_KEY` and a random `PORTFOLIO_RATE_LIMIT_SALT` as Edge Function secrets. Never commit them.
3. Check the allowed origin in `supabase/functions/portfolio-chat/index.ts` (set to `https://gagandeep1717.github.io`).
4. Deploy with `supabase functions deploy portfolio-chat --project-ref <project-ref>`.
5. Set the `portfolio-chat-endpoint` meta tag in `index.html` to `https://<project-ref>.supabase.co/functions/v1/portfolio-chat`.

## Credits

Layout, styles, and interaction design are adapted from [chirag4798.github.io](https://github.com/chirag4798/chirag4798.github.io) by Chirag Shetty, licensed under [CC BY 3.0](http://creativecommons.org/licenses/by/3.0/). Content is my own.
