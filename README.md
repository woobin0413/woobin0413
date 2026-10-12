![Hi, I’m Woobin. Web, iOS and interactive AI.](assets/header.svg)

I build web applications, native iOS tools and interactive AI experiences. I’m interested in AI that helps with everyday tasks: turning spoken job notes into a quote, identifying a purchase from a photo, or letting two characters talk to each other. These projects explore those ideas, with clear interfaces, reliable data and readable code underneath.

[🧾 Quota](https://github.com/woobin0413/quota) · [🏠 Housekeeping for iOS](https://github.com/woobin0413/housekeeping-ios) · [💬 Multi-agent Conversation](https://github.com/woobin0413/multi-agent-conversation)

## Three projects, three different problems

| Project | What it helps you do | What to look for in the code |
| --- | --- | --- |
| **[Quota](https://github.com/woobin0413/quota)** | Create contractor quotes and invoices today; voice-to-quote drafting is planned | Database transactions, subscription billing and concurrent request limits |
| **[Housekeeping for iOS](https://github.com/woobin0413/housekeeping-ios)** | Build a shared inventory from purchase photos, with AI suggestions designed for review before saving | SwiftUI state, shared access rules and recoverable editing |
| **[Multi-agent Conversation](https://github.com/woobin0413/multi-agent-conversation)** | Watch two AI agents talk, with one angry and the other kind—or any moods you choose | Event streaming, session ownership and cancellation |

## 🧾 Quota

**The goal: say what the job needs → review a draft → send a professional quote or invoice.**
Quota is designed for contractors who would rather explain a job out loud than type an invoice on their phone. Imagine saying, “Replace four outlets and allow six hours of labor,” then reviewing a clear, customer-friendly draft.

**How AI fits in:** the planned voice assistant would turn the recording into text, pick out the work and quantities, and help organize a draft using the contractor’s own price book. The contractor would confirm the details and prices before saving or sending it.

**Today:** catalog-based quotes, PDF invoices, email and payment records work. Voice capture and AI drafting are planned; the screenshot shows the current quoting app.

<a href="https://github.com/woobin0413/quota#see-it-in-action">
  <img src="assets/quota-dashboard.png" alt="Quota dashboard with fictional clients, paid and unpaid quotes, and payment summary" width="800" />
</a>

*Actual interface with synthetic demo data.*

**Stack:** TypeScript · Next.js · PostgreSQL · Supabase · Auth0 · Stripe.

**Engineering focus:** atomic quote creation, shared rate budgets and billing revisions that prevent delayed events from overwriting newer state.

[Workflow & screenshots](https://github.com/woobin0413/quota#see-it-in-action) · [Billing code](https://github.com/woobin0413/quota/blob/main/lib/billing-state.ts) · [Regression tests](https://github.com/woobin0413/quota/blob/main/lib/__tests__/billing-state.test.ts)

## 🏠 Housekeeping for iOS

**Take a photo → review suggested product details → save to your household inventory.**
Housekeeping is designed to make recording a purchase as easy as taking its photo. Instead of typing everything about a new kettle or lamp, you would ask AI to suggest its name, description, brand and model, then make any corrections and save the purchase to the shared database.

**How AI fits in:** it helps identify what is in the photo and fills in an editable draft. You stay in charge of what gets stored: suggestions become an inventory item only when you tap Save. The app also keeps photos private and helps track what needs restocking.

**Today:** photo capture, manual entry and shared storage are implemented. The recognition flow is tested with sample responses; live AI recognition remains disabled.

<p>
  <a href="https://github.com/woobin0413/housekeeping-ios#see-it-in-action"><img src="assets/housekeeping-inventory.png" alt="Offline Housekeeping inventory preview with search and sample household items" width="260" /></a>
  <a href="https://github.com/woobin0413/housekeeping-ios#see-it-in-action"><img src="assets/housekeeping-photo-review.png" alt="Offline sample-photo review with editable purchase details" width="260" /></a>
</p>

*Offline simulator previews with sample artwork. Live recognition is disabled; hosted and physical-device acceptance is in progress.*

**Stack:** Swift · SwiftUI · Supabase.

**Engineering focus:** account-scoped state, household access rules, photo metadata removal and recovery of unfinished edits.

[Workflow & screenshots](https://github.com/woobin0413/housekeeping-ios#see-it-in-action) · [Architecture](https://github.com/woobin0413/housekeeping-ios/blob/main/docs/architecture.md) · [Native tests](https://github.com/woobin0413/housekeeping-ios/tree/main/ios/HouseKeepingTests)

## 💬 Multi-agent Conversation

**Choose two moods → watch the AI agents talk → change the mood or steer the story.**
Luna and Oak are two AI agents having a conversation with each other. Make Luna angry and Oak kind, and watch how an irritated remark meets a friendly reply. Or try a mysterious character talking to a funny one—the combination changes the tone of the exchange.

**How agentic AI works here:** each character has its own role and mood instructions. The app takes turns asking each agent to respond to the conversation so far. You can pause, change either mood, or add a direction such as “A dragon appears,” and let them continue for up to 15 turns. Both characters use the same underlying language model, guided by different instructions.

<a href="https://github.com/woobin0413/multi-agent-conversation#see-it-in-action">
  <img src="assets/conversation.png" alt="Conversation app with character moods, sample dialogue and a queued story redirect" width="700" />
</a>

*Real interface with scripted sample dialogue. This is a local demo with in-memory sessions.*

**Stack:** TypeScript · React · NestJS · Groq · Server-Sent Events.

**Engineering focus:** asynchronous streaming, private session controls, abort signals and bounded provider calls.

[Workflow & screenshots](https://github.com/woobin0413/multi-agent-conversation#see-it-in-action) · [Story service](https://github.com/woobin0413/multi-agent-conversation/blob/main/backend/src/story/story.service.ts) · [Security tests](https://github.com/woobin0413/multi-agent-conversation/blob/main/backend/src/story/story.security.spec.ts)

## What I work with

| Web & services | Native | Data & tooling |
| --- | --- | --- |
| TypeScript · React · Next.js · NestJS | Swift · SwiftUI | PostgreSQL · Supabase · Python · GitHub Actions |

The project READMEs include setup steps, design decisions, tests and current limitations. Screenshots use synthetic or offline demo data.
