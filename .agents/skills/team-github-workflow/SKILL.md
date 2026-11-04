---
name: team-github-workflow
description: >-
  Git and GitHub team collaboration rules for Solius Studio: branching strategies,
  conflict prevention, commit conventions, and Pull Request checklists for 2-person projects.
  Use whenever branching, committing, creating Pull Requests, resolving git conflicts, or managing repository state.
---

# 2-Person Team GitHub Collaboration Protocol

## 1. Branch Strategy
- **`main`**: Production branch. It is always stable and deployable.
  - **Rule**: Direct pushes to `main` are strictly discouraged.
- **Feature Branches**:
  - `feature/<short-name>`: New components, sections, or logic (e.g. `feature/hero-redesign`, `feature/lead-form`).
  - `demo/<name>`: Individual demo showcase projects (e.g. `demo/lexvanguard-intake`, `demo/aura-menu`).
  - `fix/<short-name>`: Bug fixes (e.g. `fix/mobile-navbar-overflow`).

---

## 2. Commit Message Standards (Conventional Commits)
Keep commits clear and descriptive so your partner understands what changed at a glance:
- `feat: add WhatsApp direct booking modal to Hero`
- `fix: correct z-index overlap on mobile navbar`
- `style: refine ruby red accent colors on Bento grid`
- `docs: update setup instructions in README`
- `chore: update dependencies in package.json`

---

## 3. Daily Workflow for Partners
Before starting any new work:
1. **Pull latest changes from `main`**:
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Create your feature branch**:
   ```bash
   git checkout -b feature/mi-nueva-tarea
   ```
3. **Commit your incremental changes**:
   ```bash
   git add .
   git commit -m "feat: implementar seccion de precios"
   ```
4. **Push branch to GitHub**:
   ```bash
   git push -u origin feature/mi-nueva-tarea
   ```
5. **Open a Pull Request (PR)** on GitHub and notify your partner for review and merge.

---

## 4. Conflict Prevention Guidelines
- **Modularity**: Work on separate files whenever possible. (e.g. Partner A works in `src/components/ShowcasePreview.astro`, Partner B works in `src/components/AIAutomationSection.astro`).
- If both partners need to touch `src/pages/index.astro`, coordinate briefly to avoid merge conflicts.
- Always run `npm run build` locally before pushing to verify there are no compilation errors.
