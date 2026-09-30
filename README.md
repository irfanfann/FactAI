# Fact.AI Frontend

A static, framework-free web interface for Fact.AI. Lets users submit a news article URL or a text claim, view an AI-generated verdict with supporting sources, manage their account and subscription, and browse their past checks.

## How it works

The site is plain HTML, CSS, and JavaScript with no build step. It talks to the Fact.AI backend entirely through `fetch()` calls: submitting a claim, logging in/registering, verifying email, resetting a password, checking out a subscription via Midtrans Snap, and loading paginated check history. The logged-in session (a JWT) and theme preference are kept in the browser's local storage.

## Tech stack

- Vanilla HTML, CSS, JavaScript (ES6+)
- Midtrans Snap.js for the payment popup

## Setup

### 1. Clone the repo

```bash
git clone https://github.com/irfanfann/FactAI.git
cd frontend
```

### 2. Point it at your backend

Open `config.js` and set:

```javascript
window.API_BASE_URL = 'https://your-backend-url';
window.MIDTRANS_CLIENT_KEY = 'your-midtrans-client-key';
```

### 3. Run it locally

No build step is needed — just open `index.html` in a browser, or serve the folder with any static server (e.g. the VS Code "Live Server" extension) so relative paths and `fetch()` calls work correctly.

### 4. Deploy

The site is a set of static files, so it can be hosted anywhere that serves static content (e.g. GitHub Pages). Just make sure `config.js` points at your live backend URL.

## Notes and limitations

- This is a prototype built for a competition; there is no build tooling, bundler, or framework by design.
- The four analysis cards on the results page reflect whatever the backend's AI analysis returns.
