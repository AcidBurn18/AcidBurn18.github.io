# Portfolio Modernization – Phase 1 Implementation Plan

> **For Hermes:** Implement this plan task-by-task, keeping the current design language recognizable and only improving structure, hierarchy, and credibility.

**Goal:** Transform the existing portfolio homepage from a resume-style site into a senior Platform Engineering / DevOps portfolio that clearly communicates engineering depth, real infrastructure experience, and consulting readiness.

**Architecture:**
Keep the site as a single-page static portfolio. Preserve the existing warm, editorial visual language, but restructure content into stronger sections and more deliberate information hierarchy. Prioritize truthful proof points sourced from the public GitHub profile, Medium RSS/articles, and the private homelab documentation. Do not invent projects, metrics, or case studies. The implementation should minimize dependencies, reuse existing styles where possible, and remain fast, responsive, and accessible.

**Tech Stack:** HTML, CSS, vanilla JS if needed, GitHub Pages/static hosting, existing portfolio assets, public GitHub profile, Medium RSS, private homelab architecture docs.

---

## Source-of-truth rules

- Use the public identity as Ansh Agrawal.
- Treat public repos as portfolio signals only; some may be incomplete or half-baked.
- For homelab claims, prefer the private homeserver docs/runbooks and architecture notes.
- Use Medium articles as the main writing/publication source.
- Do not add case studies, metrics, testimonials, consulting services, or architecture diagrams in Phase 1.
- Keep all claims factual and already supported by the available sources.

---

## Content inventory to use

### Strong identity / positioning
- Platform Engineering
- Cloud Infrastructure
- Kubernetes
- Azure Landing Zones
- Infrastructure as Code
- GitOps
- Self-Hosted Platforms
- Security
- Observability
- Networking

### Strong evidence sources
- GitHub public profile and pinned/popular repos
- Medium RSS/articles on homelab networking, Traefik, Tailscale, qBittorrent/Jellyfin, DNS, Terraform docs, CI/CD, Kubernetes certificates
- Private homelab docs:
  - backup platform architecture
  - DNS observability runbook
  - Traefik side-by-side migration notes
  - indian-music-cleaner architecture

### Likely featured project candidates
- Azure Landing Zone Starter / Azure Landing Zone work
- Home Server DevOps Lab / homeserver_public
- Infrastructure Automation / Terraform-related work
- GitOps / deployment automation work
- Frigate AI / observability / homelab operations if publicly supportable
- OPNsense / networking / DNS observability if enough public-safe detail exists

---

## Task 1: Audit current homepage content and map it to the new narrative

**Objective:** Build a content map that preserves only the parts worth keeping and identifies what must be rewritten.

**Files:**
- Read: `index.html`
- Read: existing public repo README/docs if needed
- Read: Medium RSS feed entries
- Read: private homelab architecture docs

**Deliverable:**
A concise content inventory containing:
- current sections
- sections to keep
- sections to rewrite
- sections to split or regroup
- list of credible project/article inputs

**Verification:**
- Confirm every intended homepage section has source material behind it.
- Confirm there are no invented projects or claims.

---

## Task 2: Rewrite hero section for stronger positioning

**Objective:** Replace generic DevOps wording with a sharper platform-engineering value proposition.

**Files:**
- Modify: `index.html` hero copy and hero metadata

**Content requirements:**
- Primary identity: Platform Engineer / DevOps Engineer
- Mention cloud infrastructure, Kubernetes, Azure Landing Zones, IaC, GitOps, self-hosted platforms
- Short value proposition focused on reliability and automation
- Keep language direct and non-hype

**Implementation notes:**
- Keep the existing visual style and tone.
- Improve the CTA pair so it drives to GitHub and Medium.
- Consider a second-line sentence that clarifies what problems are solved.

**Verification:**
- The hero should answer “who am I” and “what do I build” within seconds.
- Copy should be concise and factual.

---

## Task 3: Replace the generic summary with a professional narrative

**Objective:** Convert the bio into a platform-engineering summary that sounds like a senior technical operator.

**Files:**
- Modify: `index.html` summary/intro area

**Content requirements:**
- Platform Engineering
- Azure Landing Zones
- Infrastructure Automation
- Terraform Enterprise / Terraform ecosystem if supported by source material
- Kubernetes
- Security
- Observability
- Home lab engineering

**Implementation notes:**
- Write as a compact narrative, not a bullet list of buzzwords.
- Use outcome-oriented language: design, automate, secure, observe, operate.

**Verification:**
- Summary should feel like engineering documentation, not a personal bio paragraph.

---

## Task 4: Rebuild the experience section around problem → solution → impact

**Objective:** Present work history as engineering outcomes instead of responsibilities.

**Files:**
- Modify: `index.html` experience section
- Add: if necessary, a dedicated experience block separate from the summary

**Content requirements:**
Each experience item should contain:
- Problem
- Solution
- Impact

**Implementation notes:**
- Keep the claims truthful and sourced.
- Use compact substructure such as three labeled lines or a small grid inside each experience card.
- If there is no reliable quantified impact, describe operational improvement qualitatively.

**Verification:**
- A reviewer can understand what was improved and why it mattered.
- No responsibility-only wording remains.

---

## Task 5: Redesign the projects section into categorized featured work

**Objective:** Make projects the strongest proof section on the page.

**Files:**
- Modify: `index.html` projects section
- Add styling for category groupings and featured cards if needed

**Content requirements:**
Every project card must show:
- problem statement
- technologies
- architecture highlights
- engineering decisions
- GitHub link
- article link if available

**Implementation notes:**
- Group projects by category:
  - Cloud Infrastructure
  - Self-Hosted Infrastructure
  - Automation
  - Networking
  - Observability
  - AI & Computer Vision
- Make featured projects larger than secondary ones.
- Prefer 3–6 strong items over a long list.
- Use the most credible and supportable description for each repo/article.
- If a repo is incomplete, present it as a work-in-progress lab or starter rather than a finished product.

**Suggested featured cards:**
- Azure Landing Zone
- Home Lab / homeserver_public
- Infrastructure Automation / Terraform docs work
- GitOps / deployment automation
- Traefik / ingress / networking work
- Frigate AI or observability if source material supports it

**Verification:**
- Each project card should read like a miniature engineering brief.
- No fabricated achievements.
- Strong cards visually dominate the section.

---

## Task 6: Rebuild the skills section into grouped capability bands

**Objective:** Replace the wall of badges with clean skill families.

**Files:**
- Modify: `index.html` skills section
- Modify CSS for grouped rows/cards/pills

**Content requirements:**
Use groups such as:
- Cloud
- Infrastructure as Code
- Containers
- GitOps
- Networking
- Monitoring
- Programming
- Operating Systems

**Implementation notes:**
- Keep the number of visible items reasonable.
- Use grouped clusters instead of a single tag cloud.
- Ensure the layout remains legible on mobile.

**Verification:**
- Skills are readable in under five seconds.
- No overwhelming badge wall.

---

## Task 7: Convert the writing section into an editorial article showcase

**Objective:** Present Medium work like a curated technical publication list.

**Files:**
- Modify: `index.html` article/writing section
- Potentially add reusable article card styles

**Content requirements for each article:**
- Title
- Category
- Estimated reading time
- Short summary
- Direct link

**Implementation notes:**
- Highlight engineering articles over generic tutorials.
- Use categories such as networking, homelab, automation, DNS, ingress, DevOps, Kubernetes, Terraform.
- Estimated reading time can be approximate and should be clearly presented as such.
- Prioritize the strongest and most relevant Medium pieces.

**Recommended article themes to feature first:**
- Traefik / ingress / reverse proxy in homelab
- Tailscale on Proxmox
- qBittorrent to Jellyfin automation
- Unbound / Pi-hole / DNS
- GitHub Actions CI/CD for homelab
- Terraform docs / module documentation

**Verification:**
- The section looks curated, not like a raw feed.
- Every article has an immediately useful reason to click.

---

## Task 8: Improve certifications presentation

**Objective:** Make certifications look intentional and credible.

**Files:**
- Modify: `index.html` certifications section

**Content requirements:**
- Provider
- Year
- Credential
- Verification link

**Implementation notes:**
- Use a compact card or table-like list.
- Group technical certifications separately from language credentials if needed.
- If a credential has an official verification URL, display it clearly.

**Verification:**
- Certification entries are easy to scan and verify.

---

## Task 9: Strengthen the contact section with a better CTA

**Objective:** End the page with a confident consulting-oriented call to action.

**Files:**
- Modify: `index.html` contact section

**Content requirements:**
- Strong CTA line such as: “Let’s build reliable infrastructure together.”
- LinkedIn
- GitHub
- Email
- Medium

**Implementation notes:**
- Make the CTA feel like an invitation to collaborate on infrastructure work.
- Keep the section brief and decisive.

**Verification:**
- Contact section feels like the end of a technical portfolio, not a generic footer.

---

## Task 10: Refine information architecture and navigation

**Objective:** Make the page easier to scan and better aligned to the new story.

**Files:**
- Modify: `index.html` navigation and section anchor structure

**Implementation notes:**
- Navigation should reflect the new section order.
- Keep anchors short and meaningful.
- Consider grouping sections in the order:
  - Hero
  - Summary
  - Experience
  - Projects
  - Skills
  - Writing
  - Certifications
  - Contact

**Verification:**
- A user can jump to any major section quickly.
- The site reads top-to-bottom as an engineering story.

---

## Task 11: Tighten the visual system without changing the brand too much

**Objective:** Improve hierarchy, spacing, responsiveness, and readability while keeping the existing palette recognizable.

**Files:**
- Modify: `index.html` CSS

**Implementation notes:**
- Preserve the warm, editorial color system unless a contrast issue requires adjustment.
- Improve section spacing and card spacing.
- Strengthen type hierarchy with clearer headings and body text.
- Keep animations subtle and usability-first.
- Maintain accessibility basics: semantic HTML, contrast, focus states, keyboard navigability.

**Verification:**
- Mobile, tablet, and desktop layouts remain clean.
- Lighthouse/performance should stay high because the site remains static and dependency-free.

---

## Task 12: Validate the final output against Phase 1 goals

**Objective:** Make sure the homepage answers the user’s core questions in under 30 seconds.

**Files:**
- Read: `index.html`

**Validation checklist:**
- Who am I?
- What infrastructure have I actually built?
- What problems do I solve?
- Why should someone hire me instead of another DevOps engineer?

**Verification:**
- The page now feels like a senior Platform Engineer portfolio.
- The design remains recognizable.
- The page does not drift into blog, brochure, or fake case-study territory.

---

## Suggested implementation order

1. Content inventory and section mapping
2. Hero rewrite
3. Professional summary rewrite
4. Experience section restructure
5. Projects redesign
6. Skills grouping
7. Writing/articles makeover
8. Certifications cleanup
9. Contact CTA upgrade
10. Navigation and final visual pass
11. Accessibility and responsive polish
12. Final validation

---

## Out of scope for Phase 1

Do not add any of the following yet:
- Case studies
- Architecture diagrams
- Infrastructure metrics
- Consulting services page
- Testimonials
- Blog redesign
- New framework migration
- Heavy animations

---

## Acceptance criteria

Phase 1 is complete when:
- The homepage reads like a Platform Engineering portfolio, not a resume
- The strongest projects and articles are easy to find
- The site still looks like the same brand, just more mature
- All claims are backed by public repos, Medium posts, or private homelab docs
- The site remains lightweight, responsive, and accessible
