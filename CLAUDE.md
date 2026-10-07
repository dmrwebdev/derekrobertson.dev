# derekrobertson.dev

Personal homepage for Derek Robertson, a senior developer whose main stack is Ruby on Rails.
The app is itself a portfolio piece: every choice should hold up in a code review.

## Stack

- Rails 8.1, Ruby 4.0, Hotwire (Turbo + Stimulus), importmap, Propshaft
- Static site: no database (no Active Record or Active Job).
- Generated barebones: no Solid gems, Kamal, Docker, GitHub CI, linters, system tests,
  Jbuilder, Action Mailer/Mailbox/Text/Cable or Active Storage. Add each only when needed.
- Components: ViewComponent
- CSS: plain modern CSS (nesting, custom properties, `@layer`, container queries).
  No Sass, no Tailwind, no utility-class frameworks.
- Interactivity: Stimulus controllers. No JS frameworks.

## Development

- Ruby 4.0.7 via mise on the WSL host; mise reads the version from `.ruby-version`.
- `bin/setup` to bootstrap, `bin/dev` to run (http://localhost:3000), `bin/rails test`.

## Production constraints

- Target: an existing 1 GB DigitalOcean droplet. Do not plan around upsizing it.
- Keep it lean: one Puma process (`WEB_CONCURRENCY=1`, few threads), YJIT + jemalloc, HTTP caching (`fresh_when` / `Cache-Control`).
- Build Docker images off-box; never build on the droplet.
- No paid services beyond the droplet.

## Design direction

- Dark background, teal/cyan accent, a techy display face paired with a mono face.
- Lead with typography, whitespace and substance; at most one tasteful interactive piece.

## Session notes

Session state, open questions and machine-specific notes live in `tmp/claude/`
(git-ignored via `/tmp/*`). Read the current state at the start of a session:

@tmp/claude/current.md
