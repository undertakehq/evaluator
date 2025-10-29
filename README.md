# Stock Market Asset Evaluator

This Rails application powers effort to evaluate stock market assets. The initial scope targets Brazilian Real Estate Investment Funds (FIIs), delivering insights comparable to U.S. REIT analysis by aggregating and processing open financial data.

## Project Objectives
- Collect and normalize open datasets relevant to FIIs (e.g., fund reports, exchange filings).
- Compute actionable indicators that highlight portfolio quality, income stability, and market positioning.
- Surface comparisons and alerts that help investors monitor multiple FIIs with minimal manual effort.

## Current Status & Roadmap
- ✅ Rails 8 foundation with PostgreSQL and RSpec test stack.
- 🚧 Data ingestion pipelines for FIIs from public sources.
- 🚀 Next up: expose evaluation metrics via API endpoints and dashboard views.

## Getting Started
1. Ensure Ruby 3.3.4, Bundler, and PostgreSQL are available locally (or run Postgres via `docker-compose up db`). Rails 8.0.1 is pinned in the Gemfile.
2. Install dependencies and prepare the database:
   ```sh
   bin/setup
   ```
3. Start the application:
   ```sh
   bin/rails server
   ```
4. Visit `http://localhost:3000` to confirm the app boots.

## Key Commands
- `bin/rails db:prepare` – synchronize the database schema for development or test.
- `bundle exec rspec` – execute the test suite.
- `bin/rails console` – open an interactive console for debugging calculations.
- `bin/rails log:clear tmp:clear` – remove noise before capturing logs for investigation.

## Directory Layout
- `app/` – Rails MVC code, plus jobs, mailers, channels, and front-end assets.
- `lib/` – shared modules that support data ingestion and evaluation logic.
- `spec/` – RSpec test suite mirroring the application structure.
- `config/` – environment configuration, credentials, and routing.
- `db/` – migrations and seeds; persistent Postgres volume configuration in `docker-compose.yaml`.

## Contributing
Keep changes focused on expanding the evaluator’s coverage and accuracy. Document new data sources or metrics in the README (or dedicated `docs/` notes) so future contributors understand their intent. Run `bundle exec rspec` before opening a pull request and highlight migrations, configs, or external dependencies in the PR description.

### Versioning & Commit Messages
- Tag releases using [Semantic Versioning](https://semver.org/) (`MAJOR.MINOR.PATCH`), and increment versions according to the impact of your changes.
- Use [Conventional Commits](https://www.conventionalcommits.org/) for commit messages. Examples:
  - `feat: add fii cashflow parser`
  - `fix: correct dividend yield rounding`
  - `chore(release): 1.2.0`
- Reference issues in commit messages where relevant, e.g., `feat: integrate infomoney source (#42)`.
