# First App

A responsive web dating application foundation using **React**, **Vite**, **Tailwind CSS**, and **Supabase**. The intended stack can be run on free tiers for development and early hosting: Supabase Free, plus Vercel Hobby or Firebase Hosting. Free plans have usage limits and hosting terms; review current provider plans before launch.

This repository currently contains structure and configuration placeholders only. It does not include application logic or UI pages.

## Project structure

```text
src/
  core/
    config/       Supabase client and app constant placeholders
    context/      Shared auth context placeholder
    hooks/        Shared custom hooks
    utils/        Shared helpers and formatters
  features/
    auth/         Authentication components, services, and hooks
    profile/      Profile components, services, and hooks
    discovery/    Discovery components, services, and hooks
    matches/      Matches components, services, and hooks
    chat/          Chat components, services, and hooks
  shared/
    components/   Reusable components such as Navbar, Modal, and Button
    layouts/      Shared layouts such as MainLayout and AuthLayout
  App.jsx         Application root placeholder
  main.jsx        React entry point placeholder
  index.css       Tailwind CSS directives
public/
  images/
  icons/
```

Each feature owns its components, data services, and hooks. App-wide configuration and shared helpers belong under `src/core/`; reusable components and layouts belong under `src/shared/`. Keep changes within the relevant feature where possible so two developers can work in parallel with fewer overlapping edits. `.gitkeep` files preserve empty directories.

## Local setup

1. Install a current Node.js LTS release and npm.
2. Clone the repository and enter its directory.
3. Install dependencies:

   ```sh
   npm install
   ```

4. Copy `.env.example` to `.env` and provide your Supabase project URL and anon key. `.env` is ignored by Git.
5. Start the Vite development server:

   ```sh
   npm run dev
   ```

The server provides the Vite starter shell. React mounting and application UI are intentionally not implemented yet. Use `npm run build` to create a production build after the app entry point is added.

## Git collaboration

1. Before starting work, update your local base branch:

   ```sh
   git switch main
   git pull --ff-only origin main
   ```

2. Create a focused branch for your change:

   ```sh
   git switch -c feature/profile
   ```

3. Work within the relevant feature folder and avoid editing another feature's files unless required.
4. Review and commit your changes with a clear message:

   ```sh
   git status
   git add <files>
   git commit -m "Add profile foundation"
   ```

5. Push your branch and open a GitHub pull request:

   ```sh
   git push -u origin feature/profile
   ```

6. Before the next task, return to `main` and pull the latest changes. Resolve conflicts on your feature branch and coordinate edits when a shared file must change.

## Dependencies

`package.json` is the source of truth for web dependencies and scripts. `requirements.txt` is retained only as a note; this project does not currently use Python utilities.
