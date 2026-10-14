# Grok Bot 201 — outline (video grok-bot-201, 55:27)

Speakers: Scott (AI deployment team, host) and Joseph (field engineering, demo).

## 1. 00:00 Intro and the bot UI
- Scott introduces 201 as the follow-up to the 101 session; Joseph runs the demo.
- The UI works like iMessage: a list of bots on the left, and a star marks the primary bot (Roy), which has context on all the other bots.
- Live demo: "Tell the X bot to post that we're live with 201." Roy relays this to the X bot, which is signed into Joseph's X account and posts by controlling its own computer (he asks it to post a new one, not keep the earlier test post).
- Each bot has its own memory and its own computer, and you can open that computer and watch it work.

## 2. 00:03 Agenda and the 3 things you'll learn
- Agenda: welcome → the sticker shop demo → how it was built → turning it into an autonomous shop → Q&A.
- 1. Bots run on their own: routines plus multiple skills, and the bot picks the right skill.
- 2. Bots work as teammates and can be shared with other people.
- 3. Each bot has its own persona, memory, skills, workflows and routines.

## 3. 00:04 Recap of 101: Martin's 3 bots made stickers
- Dex is the designer: it takes Figma assets and makes creative variations with the Grok API.
- Maya handles the community: it made a QR code and ran a live demo.
- Penny handles sourcing: it found the print vendor.
- Online vote: "look at you" came first. Scott's favorite was the blue one; Joseph's was the "stack of three".
- Next step: a sticker shop where people can order stickers and create more with Dex.

## 4. 00:06 Team bots: sharing Dex
- Dex shows "by Martin" because Martin shared it with the team, which makes it a team bot.
- Add it with + → Team bots → search for Dex. No setup is needed.
- Demo: Joseph asks Dex for a "happy blue" sticker (Scott's favorite color).
- Group chat with the bot Dex and the human Martin: "@Martin, what do you think?" Martin replies "yes and yes."
- Answering a chat question: Martin manages Dex's memory, skills and routines, and his updates reach everyone who uses Dex.

## 5. 00:09 The live sticker shop
- The live site link was posted in the chat; Joseph says he vibe-coded it with Grok Bot.
- You drag stickers into a shopping bag in the middle. Each sticker has its own persona, such as "Thinking", "Nap buddies" and "Dizzy".
- Viewers were asked to play with it because their clicks are used later in the demo.

## 6. 00:12 The build team: Dex, Lou, Sam (+ a hidden 4th)
- Dex is the designer (a team bot from Martin), Lou the full-stack developer, and Sam the UI/UX designer.
- A hidden 4th bot is what makes the shop fully autonomous; it is revealed later.

## 7. 00:14 Demo: creating a UI/UX bot and fanning out to 3 models
- + → Create new bot → "You are a UI/UX designer". He gives it the Duolingo store as a clean reference (no clutter).
- Goal: a Grok Bot sticker shop, using 6 assets from Martin.
- The bot connects to Cursor and launches 3 cloud agents on Grok 4.7 (low), Opus 5.5 and Gemini 3.7 (low), then sends back screenshots and recordings.
- Why 3 models: each has different pre- and post-training, so the same prompt gives different results, and you pick the best.
- Clarification from Scott: the cloud agents are Cursor cloud agents, and the model choice is made there.
- The bot wrote a brief.md (similar to plan mode) with the Figma assets linked; all 3 agents got the same prompt and ran in parallel, visible in the Cursor UI.

## 8. 00:18 Why separate specialist bots?
- Q: why not one bot for everything?
- Like a startup team: if one person doing everything worked well, job titles wouldn't exist.
- Roles are blurring with AI, but each bot gets its own computer, context ("context is king") and memory.
- Scott agrees: for now, specialized bots give the best results.

## 9. 00:22 Voice brainstorm with the full-stack bot (Lou)
- Joseph uses voice chat: "a light sticker shop, deployed on Vercel".
- The bot suggests Next.js static export with zero server cost, plus Stripe Checkout.
- Joseph declines payments (he only wants a mockup). The bot says to keep images in /public and hardcode the product list as an array or JSON: no database, no backend.
- He asks it to spin up a cloud agent to scaffold the repo and send screenshots.
- A 2-minute brainstorm, like riffing with a PM (Joseph spent 3.5 years at Amazon as a software developer).
- Merging the 3 UI options onto the scaffold gives you the site.
- Scott: Cursor is specific to this example; bots connect to many other systems too.

## 10. 00:27 Inside Lou's computer
- You can open Lou's computer: a terminal that has already run localhost.
- "Spin up the latest localhost so I can see it": it types commands itself and can record its work into the chat.

## 11. 00:29 Comparing the fan-out results
- Grok 4.7 finished first, with a mobile view and a screen recording it made by itself.
- Opus 5.5 also looked good, but the results were similar because they shared the repo (contamination).
- An earlier round: Gemini (flash) looked vibe-coded and needed many iterations. Opus's cute hero page and drag animation inspired the drag-and-drop bag, the shimmer and the hearts.
- Mixing ideas from several models produced a result no single model reached.
- Price joke: maybe 25¢ per sticker, or free.

## 12. 00:33 The AI maturity curve
- Ask (chatbots, 2020–21) → co-work (scheduled tasks) → delegate to bots → many bots shared as team bots.
- The site took about 2 hours in total, which puts it at about 80–90% on the curve. Scott adds that proactivity also moves you up.

## 13. 00:35 The 4th bot: Ed (metrics) and the PMF loop
- Ed reads Vercel analytics and updates a "popularity canvas", a live dashboard (sneak peek).
- At 8:30 that morning, before the site was public, only 8 of 24 stickers had been clicked; "Party" led with 5 views.
- Roy is the orchestrator, connected to X and the site. Ed handles metrics, Dex design (Figma) and Lou code (GitHub).
- Routine every 24h: Ed ranks stickers → the bottom 3 are removed → Dex makes 3 new ones → Lou deploys to Vercel. The shop never goes stale.
- Human in the loop: it took about 30 minutes with Ed alone, plus end-to-end debugging. You can add daily brief checkpoints.

## 14. 00:41 Live results and running the loop
- Ranking: 1. Piggyback, 2. Party, 3. Cloud nap.
- Ed signs into Vercel in its own browser (or uses an API token; secrets are stored outside the bot's computer, so they don't leak).
- Bottom 3: Sprout, Heart Eyes, Grumpy. On a tie, it picks randomly so exactly 3 are removed (an edge case he hit the night before).
- "Run the PMF skill" goes to Roy, which messages Ed and Lou. It's non-blocking, so you can keep chatting, and he asked it to draw a workflow diagram.
- Runs every 24h on Grok 4.7 low. The result is a self-evolving website.
- Joseph gained 15 followers on X during the session (+300%).

## 15. 00:47 Voice, recap, team bots, email, Q&A
- Dictation versus live voice chat (bottom right of the chat box) uses the Grok voice API with low latency.
- Recap: persona, memory, skills, routines; Cursor cloud agents; Roy's workflow skill; team bots.
- Team bots: Dex shared with about 150 field engineers, and the stickers go from 24 to 27. Six to eight months ago everyone shared skills (markdown); now bots get shared and only the best survive.
- New feature: a bot can claim its own email to sign up for services and book meetings or restaurants (for example, Foreign Cinema in SF).
- Q&A on fan-out vs. tokens: first build the prompt and workflow on the model you know best (Grok), then fan out. Vague prompts waste tokens.
- Lou had already chosen Vercel + Next.js to stay on the free plan, because bots learn your preferences. Tell your chief-of-staff bot how you like to work.
- The recording will be shared in a few days.
