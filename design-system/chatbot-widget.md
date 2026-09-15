# AI Concierge Widget (Chat & Voice) System

## 1. Purpose

Every client website built using this system must include a way for
visitors to ask questions and book appointments through an on-brand
conversational assistant — via text chat or voice — without leaving
the page.

This document is the canonical reference for the AI concierge widget.
It is referenced by:

- `.agents/rules/01-premium-design.md`
- `.agents/rules/02-ui-system.md`
- `.agents/rules/03-animation.md`
- `.agents/rules/05-performance-seo.md`
- `design-system/components.md`
- `docs/client-design-brief-template.md`
- `.agents/skills/new-client/SKILL.md`
- `.agents/skills/premium-ui/SKILL.md`
- `.agents/skills/visual-qa/SKILL.md`
- `.agents/skills/final-qa/SKILL.md`

Do not duplicate this content elsewhere. Link to this file instead.

---

## 2. Required Capabilities

The widget is an active **conversion path**, not a gimmick or novelty
feature. Treat it with the same engineering and design rigor as the
site's primary call-to-action (see `.agents/rules/01-premium-design.md`
Section 12, Conversion Design).

### Chat Mode (Text Conversation)
- Accessible from a persistent, unobtrusive launcher (typically a
  fixed bottom corner).
- Clean, editorial text message stream with distinct user and
  assistant speech bubbles.
- Quick-reply suggested prompts relevant to the client (e.g. "Pricing
  & services", "Doctor credentials", "Emergency slots", "How to find
  the clinic").
- Typeahead or text input with responsive submit button.

### Voice Mode (Spoken Interaction)
- Tap-to-talk or push-to-talk voice interface.
- Visible, animated states: **idle**, **listening**, **thinking**,
  and **speaking**.
- **Live transcript is mandatory**: spoken interaction must display a
  synchronized real-time text transcript for accessibility and
  comprehension. Never implement a voice-only experience without visual
  fallback.
- Microphone permission requests must be strictly user-initiated
  (triggered only when the visitor explicitly taps the microphone icon).
  Never prompt for microphone access on initial page load.
- If microphone access is denied or unsupported by the browser, degrade
  gracefully with a polite, clear notice and seamlessly keep the text
  chat input available.

### Appointment Booking & Lead Capture
- The assistant's primary commercial responsibility is answering visitor
  questions accurately and guiding them toward scheduling an appointment,
  reserving a service, or requesting a callback.
- Structured intake: collecting visitor name, phone number / WhatsApp,
  preferred service, and requested time slot.
- Clear confirmation state summarizing the request.

---

## 3. Animated Bot Presence

The concierge must feel alive, polished, and characterful rather than
like a generic floating blue circle.

### Avatar States
The assistant presence must reflect four clear conversational states:
1. **Idle**: Calm, subtle breathing or resting state.
2. **Listening**: Visual audio pulse, waveform, or attentive focus.
3. **Thinking**: Processing indicator or gentle contemplation motion.
4. **Speaking**: Animated mouth/waveform movement synchronized with
   audio output or text typing.

### Technology: Lightweight Vector First
- **Preferred**: Lightweight vector animation — native SVG animation,
  CSS keyframes, Lottie (via dotlottie/lottie-web), or Rive.
- Vector animations are resolution-independent, razor-sharp on high-DPI
  displays, and typically weigh only 5–30 KB.
- **Avoid raw GIFs and heavy videos**: GIFs are non-scalable, have large
  file sizes (often 500 KB–2 MB), cannot adapt to dark/light modes,
  and severely degrade performance on budget mobile devices. A raw GIF
  is acceptable only as an emergency fallback, must be optimized under
  100 KB, and must be lazy-loaded.

### Brand-Specific Avatar Derivation
The avatar's visual style, character, and motion personality must be
derived from the client's brand identity:
- A luxury dental clinic might use a refined geometric crest, a calm
  abstract gem, or an elegant clinical monogram with soft champagne
  glow.
- A neighborhood motorcycle garage might use an illustrated wrench-wielding
  mascot or a technical mechanical gear gauge with snappy industrial
  timing.
- A high-end salon might use an organic, flowing line-art silhouette.

Do not use an identical avatar across different clients.

### Reduced Motion
Respect `prefers-reduced-motion` unconditionally. When active, replace
continuous looping and pulse animations with a refined, static,
high-clarity vector icon representing each state.

---

## 4. Integration Architecture (Pluggable & Multi-Tenant)

The widget must be architected as a self-contained component behind a
clean adapter/provider interface (`ConciergeProvider`), ensuring the
underlying backend can be connected, upgraded, or swapped without
rewriting the frontend.

```
[ Visitor UI: Chat & Voice Modal ]
               │
               ▼
   [ ConciergeAdapter Interface ]
        ├── sendMessage(text)
        ├── startVoiceSession()
        ├── stopVoiceSession()
        └── submitBooking(data)
               │
         ──────┴──────
         │           │
         ▼           ▼
   [ Placeholder ] [ Connected Backend ]
   (Mock / Stub /   (AI Receptionist SaaS:
    Direct Links)    Multi-Tenant RAG + Audio)
```

### Placeholder / Demo Mode (Default)
Until a live backend is provisioned for a client, the widget must
operate fully in demo/placeholder mode:
- The UI is visually complete, styled, and responsive.
- Pre-scripted responses answer the top 5–10 frequent questions about
  the client (hours, location, services, pricing guidance, emergency
  advice) drawn directly from verified client data.
- Booking requests capture visitor details and offer immediate fallback
  actions:
  - Direct WhatsApp link pre-filled with the visitor's request.
  - Direct phone `tel:` call link.
  - Local client contact submission.
- Never show a broken loading spinner or dead error state.

### Connected Mode (AI Receptionist SaaS)
When wired to a live backend (such as an external multi-tenant AI
receptionist service with RAG and appointment booking APIs):
- Communicates with the backend using secure HTTPS/WSS endpoints.
- Passes a client tenant identifier (`tenantId`).
- Streams responses incrementally for low latency.
- Submits appointment bookings directly to the client's scheduling
  engine.

### Secrets and Security
- Follow `.agents/rules/06-code-quality.md` and Section 17 of
  `CLAUDE.md`/`GEMINI.md`:
  - Never hardcode API keys, service tokens, or private endpoints in
    source code or Git commits.
  - Use environment variables (e.g. `VITE_CONCIERGE_API_URL`,
    `VITE_CONCIERGE_TENANT_ID`).
  - Public frontend tokens must only possess restricted, rate-limited
    access to the visitor conversation endpoint.

---

## 5. Placement, Layout & UX

### Positioning & Mobile Ergonomics
- **Fixed Launcher**: Placed in the bottom-right or bottom-left corner
  with adequate margin (`bottom: 1.5rem; right: 1.5rem;`).
- **Mobile Clearance**: On viewports `< 768px`, verify that the launcher
  does **not** cover primary floating action buttons (e.g. "Book Now",
  "Call Clinic", WhatsApp floating buttons) or critical footer links.
  Provide appropriate z-index layering (`z-40` for launcher, `z-50` for
  open drawer/modal).
- **Mobile Expansion**: On mobile viewports, the opened conversation
  modal should expand to a full-screen sheet or bottom drawer with a
  prominent close/dismiss control, preventing awkward scrolling inside a
  tiny popup.

### Accessibility (WCAG 2.1 AA)
- The launcher and all controls within the modal must be fully keyboard
  accessible (`Tab`, `Enter`, `Space`, `Escape` to close).
- Focus must be trapped inside the modal when open and restored to the
  launcher when closed.
- Incoming chat messages must be announced to screen readers via an
  `aria-live="polite"` region.
- All buttons must carry explicit `aria-label` attributes (e.g.,
  `aria-label="Open AI Assistant"`, `aria-label="Activate microphone"`).

### Performance & Lazy Loading
- The widget must **never delay initial page paint or Largest
  Contentful Paint (LCP)**.
- Load the widget script, heavy vector assets, and any audio processing
  libraries asynchronously using dynamic imports (`import()`) or
  deferred mounting after the hero section renders.
- The initial bundle overhead of the launcher must remain strictly under
  15 KB gzipped.

---

## 6. Anti-Patterns to Avoid

- **Generic blue chat bubble**: Do not use a generic off-the-shelf icon
  that looks like an unstyled third-party plugin.
- **Autoplay voice / audio**: Never play voice greeting audio without
  explicit user action.
- **Auto-opening popups**: Do not pop open the chat window unprompted or
  cover the screen after 5 seconds. Let the visitor initiate.
- **Immediate microphone permission prompt**: Never request microphone
  access on page load.
- **Voice without live transcript**: Never deliver a voice response
  without displaying the text simultaneously.
- **Fake factual claims**: Do not program the bot to claim it is a
  "24/7 human doctor" or invent prices, certifications, or guarantees.
- **Blocking Core Web Vitals**: Do not load bloated 2 MB chat scripts
  that tank performance on ₹8k–15k mobile phones.

---

## 7. Final Chatbot Widget Review

Before declaring a client project complete, verify:

- [ ] Is the concierge widget present and on-brand?
- [ ] Does the avatar personality and visual style match the client's
      creative direction rather than a generic template?
- [ ] Are both Chat and Voice modes functional (or cleanly and
      gracefully placeholder-stubbed)?
- [ ] Does Voice mode request microphone permissions only on explicit user
      action?
- [ ] Is a live text transcript displayed during voice interaction?
- [ ] Does the appointment booking flow collect name, contact, and
      service, falling back to WhatsApp/phone if unconnected?
- [ ] Is the widget keyboard operable and compliant with `aria-live`
      announcements?
- [ ] Does the widget respect `prefers-reduced-motion`?
- [ ] Does the launcher avoid blocking the primary CTA or floating action
      buttons on mobile viewports?
- [ ] Does the widget load asynchronously without degrading Core Web
      Vitals on low-end mobile devices?
- [ ] Are all backend credentials stored strictly in environment
      variables?
