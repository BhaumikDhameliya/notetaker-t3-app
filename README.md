# Notetaker

A Notetaker App using TRPC bootstrapped with Theo's T3 application template that also integrates nextJS, Prisma, NextAuth and Tailwind. And used supabase and daisyui on top of that.

## Run Locally

### database setup

Go to https://app.supabase.com/projects

Create new project

Wait for project setup. Once, project setup is done

- go to Project settings
- select Database option from sidebar
- select URI under the Connection string section
- copy database URI
- paste to .env file (make sure to replace password with your database password)

```
  DATABASE_URL=<your-supabase-postgreSQL-database-uri>
```

Install dependencies

```bash
  pnpm install
```

Push prisma schema to supabase

```bash
  pnpm prisma db push
```

to verify go to supabase -> your-project -> database
now you can see the nextAuth required tables(like User, Session, Account, etc.)

### Setup GitHub Authentication

Go to GitHub settings -> Developer settings -> OAuthApps

- Register a new application (Homepage URL - http://localhost:3000, Authorization callback URL - http://localhost:3000/api/auth/callback/github)

- save Client ID
- generate a new client secret, copy secret key
- paste into .env file

```
GITHUB_CLIENT_ID=<your-github-client-id>
GITHUB_CLIENT_SECRET=<your-github-client-secret>
```

## Tech Stack

**Client:** NextJS

**API protocol:** TRPC

**Backend As a Service:** supabase

**Database:** PostgreSQL

**ORM:** Prisma

**Validation:** Zod

**Styling:** Tailwind + DaisyUI

## Screenshots

![App Screenshot](/public/app-preview.png)
