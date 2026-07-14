# Lightspeed Hub UI

Console plugin for the OpenShift Lightspeed multicluster hub. TypeScript/React.

## Specs

All specifications live in `.ai/spec/`. Start with `.ai/spec/README.md` for project overview, reading order, and structure guide.

## Commands

No package.json yet — repo is greenfield. Expected targets once scaffolded:

```bash
npm install        # Install dependencies
npm run start      # Dev server
npm run lint       # ESLint + Prettier + Stylelint (with --fix)
npm run build      # Production build
npm run test:unit  # Unit tests
```

## Conventions

- OpenShift console dynamic plugin — follows the same patterns as lightspeed-console and lightspeed-agentic-console
- TypeScript + React, PatternFly components, CSS variables (no hex colors)
- Prefix all custom CSS classes with the plugin name
- Use react-i18next for all user-facing strings
- All spoke data accessed through hub operator APIs — never call spoke APIs directly

## Git and PR Workflow

### Commit Messages
- Start with the Jira ticket reference: `OLS-XXXX description`
- Keep the first line under 72 characters
- Use imperative mood

### Pull Requests
This repo uses a **fork-based workflow**:

1. **Push to your fork**, not to `origin` (openshift/lightspeed-hub-ui)
2. **Create the PR** against `origin/main` using your fork's branch:
   ```bash
   git push <your-fork-remote> <branch>
   gh pr create --repo openshift/lightspeed-hub-ui --head <your-github-user>:<branch> --base main
   ```
3. **PR title** must start with the Jira reference: `OLS-XXXX description`
4. **Squash commits** before pushing
