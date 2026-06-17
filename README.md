# Kolo Frontend

This is the official Next.js frontend repository for the Kolo application. The application is built using the Next.js App Router, strict TypeScript, and TailwindCSS, establishing a robust, production-ready foundation for future Stellar wallet, payment, and Soroban integrations.

## Tech Stack
- **Framework**: Next.js (App Router)
- **Language**: TypeScript (Strict Mode)
- **Styling**: TailwindCSS
- **Code Quality**: ESLint, Prettier

## Local Setup

To get started with development locally:

1. **Install Dependencies**
   Make sure you have Node.js installed, then run:
   ```bash
   npm install
   ```

2. **Run the Development Server**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) with your browser to see the result. The application will auto-update as you edit the files.

## Project Structure & Architecture

The application implements a clean, atomic folder architecture separating concerns into specific domain areas:

- `src/app/(auth)/`: Unauthenticated login and registration routes.
- `src/app/(dashboard)/`: Protected user dashboard, group management, payments, and profile routing.
- `src/app/api/`: Serverless API handlers, including Stellar wallet integrations and WhatsApp webhooks.
- `src/components/`: Reusable UI elements, heavily utilizing `index.ts` barrel files. Segmented into `common/`, `dashboard/`, `groups/`, `payments/`, and `layout/`.
- `src/hooks/`: Custom React hooks for global domain logic (`useAuth`, `useWallet`, etc.).
- `src/services/`: Isolated API fetch logic, segregating internal endpoints, external Stellar SDK usage, and webhook utilities.
- `src/context/`: React Context providers for global state management.
- `src/types/`: Centralized TypeScript interfaces for strict typing across the app.
- `src/utils/`: Common utilities including formatting helpers and cross-platform validators.
- `src/middleware.ts`: Next.js middleware handling dynamic route protection for the `/(dashboard)` routes.

## Development Workflow

- **Branching**: Always branch off `main` to create features (`feature/my-feature`).
- **Committing**: Ensure the code builds properly and all type checks pass before committing. 
- **Validation**:
  - Run `npm run build` to verify Next.js static rendering and TypeScript compilation.
  - Run `npm run lint` to catch stylistic and syntax errors.
