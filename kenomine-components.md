Kenomine.io Components v0.1

Purpose

This file documents reusable UI and content components for kenomine.io.

The goal is not to over-engineer the portfolio. The goal is to create consistent patterns for storytelling, readability, accessibility, and future maintenance.

⸻

Semantic Page Structure

Use semantic HTML wherever possible.

<header>
  <nav aria-label="Primary navigation"></nav>
</header>
<main>
  <section aria-labelledby="project-hero-title"></section>
  <section aria-labelledby="discovery-title"></section>
  <section aria-labelledby="strategy-title"></section>
  <section aria-labelledby="solution-title"></section>
  <section aria-labelledby="impact-title"></section>
</main>
<footer></footer>

Rules:

* One <main> per page.
* One visible <h1> per page.
* Use <section> for major case study sections.
* Use <article> for full case studies or project cards.
* Use <aside> for supporting notes, insights, or callouts.
* Use <figure> and <figcaption> for product screenshots, diagrams, and journey maps.

⸻

Heading System

Case Study Page

<h1>Project Name</h1>
<h2>Discovery</h2>
<h2>Strategy</h2>
<h2>Solution</h2>
<h2>Outcome</h2>
<h3>Activities</h3>
<h3>Outputs</h3>

Rules:

* Do not skip heading levels.
* Section anchors should match major headings.
* Keep headings short and scannable.

⸻

Core Layout Components

1. Site Header

Purpose:

Provide clear site navigation without competing with portfolio content.

Content:

* Logo / name
* Work
* About
* Contact
* Resume

Semantic markup:

<header class="site-header">
  <nav aria-label="Primary navigation">
    <a href="/">Koichi Enomoto</a>
    <ul>
      <li><a href="/work">Work</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/resume">Resume</a></li>
    </ul>
  </nav>
</header>

Accessibility:

* Current page uses aria-current="page".
* Mobile menu has visible focus state.
* Navigation is keyboard accessible.

⚠ Needs definition: mobile nav behavior.

⸻

2. Case Study Hero

Purpose:

Help recruiters understand the project within 30 seconds.

Content:

* Project title
* Short summary
* Role
* Company / client
* Platform
* Timeframe
* Key outcome or signal

Semantic markup:

<section class="case-hero" aria-labelledby="case-title">
  <p class="eyebrow">Case Study</p>
  <h1 id="case-title">Fidelity Youth App</h1>
  <p class="hero-summary">
    Helping teen investors build confidence before their first trade.
  </p>
</section>

Rules:

* Keep summary under 30 words.
* Show role and outcome early.
* Avoid long setup paragraphs.

⸻

3. Project Metadata Block

Purpose:

Give fast context before the story begins.

Fields:

* Role
* Team
* Timeline
* Platform
* Methods
* Deliverables

Semantic markup:

<dl class="project-meta">
  <div>
    <dt>Role</dt>
    <dd>Senior Product Designer</dd>
  </div>
  <div>
    <dt>Platform</dt>
    <dd>iOS, Android</dd>
  </div>
</dl>

Rule:

Use <dl> for label-value pairs.

⸻

4. Metrics Block

Purpose:

Make impact visible and scannable.

Semantic markup:

<section class="metrics" aria-labelledby="metrics-title">
  <h2 id="metrics-title">Impact</h2>
  <dl class="metric-grid">
    <div class="metric-card">
      <dt>Activation</dt>
      <dd>71%</dd>
    </div>
  </dl>
</section>

Rules:

* Use real metrics only.
* Add context beneath the number.
* Avoid vanity metrics without meaning.

⸻

5. Case Insight Card

Purpose:

Highlight a strategic takeaway.

Example:

<aside class="case-insight" aria-label="Case insight">
  <h3>Case Insight</h3>
  <p>
    Choice creates flexibility, but too much choice can increase hesitation.
  </p>
</aside>

Use for:

* key user insight
* strategic rationale
* trade-off
* decision principle

Rule:

One strong idea per card.

⸻

6. Process Section

Purpose:

Standardize case study storytelling.

Recommended sections:

<section id="discovery" aria-labelledby="discovery-title">
  <h2 id="discovery-title">Discovery</h2>
</section>
<section id="strategy" aria-labelledby="strategy-title">
  <h2 id="strategy-title">Strategy</h2>
</section>
<section id="solution" aria-labelledby="solution-title">
  <h2 id="solution-title">Solution</h2>
</section>
<section id="outcome" aria-labelledby="outcome-title">
  <h2 id="outcome-title">Outcome</h2>
</section>

Rules:

* Each section should include Activities and Outputs when useful.
* Avoid process theater.
* Show decisions, trade-offs, and rationale.

⸻

7. Activities / Outputs Block

Purpose:

Clarify what was done and what was produced.

Semantic markup:

<section class="activities-outputs" aria-labelledby="activities-title">
  <h3 id="activities-title">Activities and Outputs</h3>
  <div class="two-column">
    <div>
      <h4>Activities</h4>
      <ul>
        <li>Reviewed existing research</li>
        <li>Mapped current workflow</li>
      </ul>
    </div>
    <div>
      <h4>Outputs</h4>
      <ul>
        <li>Journey map</li>
        <li>Opportunity areas</li>
      </ul>
    </div>
  </div>
</section>

⸻

8. Image / Figure Block

Purpose:

Show screenshots, diagrams, or design artifacts with proper context.

Semantic markup:

<figure class="case-figure">
  <img src="/images/fidelity-browse.png" alt="Fidelity Youth App browse screen showing investment themes." />
  <figcaption>
    Browse experience helped teens explore investing through familiar themes.
  </figcaption>
</figure>

Rules:

* Every meaningful image needs alt text.
* Use captions to explain why the artifact matters.
* Avoid dumping screenshots without interpretation.

⸻

9. Before / After Component

Purpose:

Show design evolution clearly.

Semantic markup:

<section class="before-after" aria-labelledby="before-after-title">
  <h3 id="before-after-title">Before and After</h3>
  <figure>
    <img src="/images/before.png" alt="Previous balance transfer page with multiple tasks on one page." />
    <figcaption>Before: Users had difficulty reviewing inputs after completion.</figcaption>
  </figure>
  <figure>
    <img src="/images/after.png" alt="Updated balance transfer flow with clearer review steps." />
    <figcaption>After: The flow separated decision-making and review into clearer steps.</figcaption>
  </figure>
</section>

⸻

10. Comparison Table

Purpose:

Compare products, options, competitors, or design directions.

Semantic markup:

<table class="comparison-table">
  <caption>
    Comparison of design options for balance transfer enrollment.
  </caption>
  <thead>
    <tr>
      <th scope="col">Option</th>
      <th scope="col">Strength</th>
      <th scope="col">Trade-off</th>
      <th scope="col">Decision</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Intent-first flow</th>
      <td>Clarifies user goal early</td>
      <td>Adds one decision point</td>
      <td>Recommended</td>
    </tr>
  </tbody>
</table>

Rules:

* Use real table markup, not divs.
* Include a <caption>.
* Use scope for headers.

⸻

11. Timeline / Journey Component

Purpose:

Show progression over time.

Use for:

* migration journeys
* onboarding flows
* phased rollouts
* service journeys

Semantic markup:

<ol class="timeline">
  <li>
    <h3>Phase 1: Awareness</h3>
    <p>Merchant learns that Zettle and PayPal POS experiences are being unified.</p>
  </li>
  <li>
    <h3>Phase 2: Transition</h3>
    <p>Merchant receives guided support before operational changes happen.</p>
  </li>
</ol>

Rule:

Use ordered lists when sequence matters.

⸻

12. Quote / Research Snippet

Purpose:

Highlight research evidence or stakeholder input.

Semantic markup:

<figure class="quote-block">
  <blockquote>
    <p>I want to understand what happens after I submit the transfer.</p>
  </blockquote>
  <figcaption>Participant feedback, usability testing</figcaption>
</figure>

Rule:

Use quotes sparingly and pair them with interpretation.

⸻

13. Callout Component

Purpose:

Highlight important supporting context.

Types:

* Note
* Warning
* Decision
* Constraint
* Opportunity

Semantic markup:

<aside class="callout callout--constraint" aria-label="Project constraint">
  <h3>Constraint</h3>
  <p>
    Legal, privacy, and security requirements limited how migration messaging could be framed.
  </p>
</aside>

⸻

14. Tags / Pills

Purpose:

Show quick metadata.

Semantic markup:

<ul class="tag-list" aria-label="Project tags">
  <li>Fintech</li>
  <li>Native App</li>
  <li>Design Systems</li>
</ul>

Rule:

Use list markup, not loose spans.

⸻

15. CTA Block

Purpose:

Guide visitors to the next action.

Examples:

* View next case study
* Download resume
* Contact Koichi

Semantic markup:

<section class="cta-block" aria-labelledby="cta-title">
  <h2 id="cta-title">Interested in working together?</h2>
  <a class="button button--primary" href="mailto:hello@kenomine.io">
    Get in touch
  </a>
</section>

⸻

Standard UI Components

Buttons

Variants:

* Primary
* Secondary
* Text link

Rules:

* Minimum height: 44px
* Visible hover state
* Visible focus state
* Clear accessible label

⸻

Links

Rules:

* Links should be visually distinct from body text.
* Do not rely on color alone.
* External links should indicate destination when needed.

⸻

Cards

Use cards for:

* case study previews
* metrics
* insights
* related projects

Rules:

* Entire card may be clickable only if semantics are clean.
* Do not nest multiple links inside one clickable card.

⸻

Accordion

Use only when content is optional.

Semantic markup:

<details>
  <summary>View project details</summary>
  <p>Additional project context goes here.</p>
</details>

Rule:

Avoid hiding critical portfolio content inside accordions.

⸻

Modal

⚠ Avoid unless necessary.

Portfolio content should generally stay on-page.

⸻

Accessibility Standards

Required

* Semantic headings
* Alt text for meaningful images
* Captions for complex visuals
* Keyboard accessible navigation
* Visible focus states
* Minimum 44px interactive targets
* WCAG AA color contrast
* No text embedded in images unless repeated nearby

⸻

Content Rules

Case Study Writing

Preferred pattern:

1. What was the situation?
2. What made it hard?
3. What did I do?
4. Why did it matter?
5. What changed?

⸻

Captions

Every major artifact should answer:

* What am I looking at?
* Why does it matter?

⸻

Metrics

Metrics should include context.

Weak:

“71% activation”

Better:

“71% activation among teen investors, signaling strong early engagement with the investing experience.”

⸻

Needs Definition

⚠ Final class naming convention

⚠ Component variants

⚠ Mobile navigation

⚠ Image aspect ratios

⚠ Card interaction model

⚠ Button visual styles

⚠ Focus state styling

⚠ Motion behavior

⚠ CMS or markdown content structure

⚠ Screenshot caption standards

This one is especially useful because it tells ChatGPT and future-you not just how the site looks, but how the portfolio should be structured semantically.
