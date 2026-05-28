# Campus Board

> A community bulletin board for Moringa School students — share announcements, join study groups, report lost items, and stay connected with your campus.

A React + Vite frontend that connects to a REST API backend. Students can post and browse announcements, study groups, events, and lost & found items.

## Features

* User authentication — signup and login with session persistence
* Create posts across 4 categories: Announcements, Study Groups, Events, Lost & Found
* Search and filter posts by category or keyword
* Stats dashboard with live post counts per category
* Recent activity sidebar showing latest posts
* Authors can delete their own posts
* Fully responsive design for mobile and desktop

## Tech Stack

* React 18
* Vite 5
* Wouter (client-side routing)
* TanStack Query (data fetching & caching)
* Tailwind CSS 4
* Radix UI (Toast, Tooltip)
* date-fns (date formatting)

## Project Structure

* `src/pages/` — one file per route (home, new-post, post-detail, login, signup)
* `src/components/` — reusable UI components (Layout, PostCard, CategoryBadge)
* `src/components/ui/` — base primitives (Input, Label, Toaster, Tooltip)
* `src/context/auth.jsx` — authentication context and state
* `src/lib/api.js` — all API calls wrapped as TanStack Query hooks
* `src/App.jsx` — route definitions and app-level providers
* `src/main.jsx` — React DOM entry point

## Prerequisites

* Node.js v18 or higher
* npm v9 or higher
* A running instance of the Campus Board backend

## Installation

1. Clone the repository:

```
git clone https://github.com/ahadietn/campus-board-frontend.git
```

2. Change into the project directory:

```
cd campus-board-frontend
```

3. Install dependencies:

```
npm install
```

4. Create an environment file:

```
touch .env
```

Add the following to `.env`:

```
VITE_API_URL=http://localhost:5000
```

> Replace `http://localhost:5000` with your backend URL if it runs on a different port.

## Running the App

With the backend API running, start the development server:

```
npm run dev
```

Open **http://localhost:3000** in your browser. If port 3000 is taken, Vite will use the next available port and display it in the terminal.

## Available Scripts

* `npm run dev` — start the development server with hot reload
* `npm run build` — build for production into the `dist/` folder
* `npm run serve` — preview the production build locally

## API Endpoints

The frontend communicates with the following backend endpoints:

* `POST /api/auth/signup` — register a new user
* `POST /api/auth/login` — log in
* `GET /api/auth/me` — get current session user
* `GET /api/posts` — list all posts (supports `?category=` and `?search=`)
* `POST /api/posts` — create a new post
* `GET /api/posts/:id` — get a single post
* `DELETE /api/posts/:id` — delete a post (owner only)
* `GET /api/posts/stats` — get post counts by category
* `GET /api/posts/recent` — get the 5 most recent posts

## Deployment

This project is deployed on **Vercel**.

```
npm install -g vercel
vercel login
vercel --prod
```

After deploying, add `VITE_API_URL` in **Vercel Project Settings → Environment Variables** pointing to your live backend URL.

## Authors

* Erick — [@erick3099](https://github.com/erick3099)
* Ahadi — [@ahadietn](https://github.com/ahadietn)

## Contributing
Contributions are welcome. Please open a pull request or issue with a clear description of the proposed change and any relevant context.
## License
This project was built for educational purposes at [Moringa School](https://moringaschool.com). Feel free to use it as a reference or learning resource.