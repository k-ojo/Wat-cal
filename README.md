**Wat-cal**
- **Description:** `Wat-cal` is a Node.js web application providing landlord and tenant interfaces, meter reading handling, and APIs for managing readings, tenants, and landlords. The repository contains backend controllers, a public frontend, and specialized views under `Lmode` and `public`.

- **License:** MIT — see the `LICENSE` file in the repository root.

**Prerequisites**
- **Node.js:** Install Node.js (v14+ recommended).
- **Package manager:** `npm` (bundled with Node) or `yarn`.
- **Database:** Configure a MongoDB or Postgres instance (the project includes both `mongoose` and `pg` deps). Provide connection strings using environment variables.

**Quick Start**
- Install dependencies:

```bash
npm install
```

- Create a `.env` file in the project root (example variables):

```
PORT=3000
MONGO_URI=mongodb://localhost:27017/watcal
DATABASE_URL=postgres://user:pass@localhost:5432/watcal
JWT_SECRET=your_jwt_secret
```

- Start the server (uses the project's `start` script):

```bash
npm start
# or
node server.js
```

- For development with live reload (optional):

```bash
# install nodemon globally or as dev dep
npm install -g nodemon
nodemon server.js
```

**Project Structure (high level)**
- **Root files:** `app.js`, `server.js`, `package.json` — application entry points and config.
- **`src/controllers/`:** REST controllers (e.g. `landlordController.js`, `tenantController.js`, `mbusController.js`).
- **`src/models/`:** Mongoose models like `Reading.js`, `Tenant.js`, `Room.js`, `Landlord.js`.
- **`public/` and `Lmode/`:** Frontend static pages, CSS and JS used by tenant and landlord UIs.
- **`utils/`:** utilities such as `db.js` and XML files used by the project.
- **`Server/` and `Server/mosquitto_endpoint/`:** MQTT or other server helpers.
- **`data/`:** CSV/PDF helpers and payment server scripts.

**Configuration & Environment**
- The project expects environment configuration for database connectivity and JWT secrets. Check `utils/db.js` and `src/middleware` for exact variable usage — adapt your `.env` accordingly.

**Common Tasks**
- **Run locally:** `npm start` then open `http://localhost:3000` (or the configured `PORT`).
- **Lint / tests:** There are no tests configured by default. Add test scripts to `package.json` if needed.
- **Add/Change env vars:** Edit `.env` and restart the server.

**Contributing**
- Fork the repo, create a feature branch, and open a pull request describing your change.
- Keep changes focused and include any migration or environment notes.

**Troubleshooting**
- If the server fails to connect to the DB, confirm the connection string and DB server are reachable and that the correct driver (Mongo or Postgres) is being used.
- If static pages are not loading, check `public/` and `Lmode/` locations and the static middleware in `server.js` or `app.js`.

**Next steps you might want me to do**
- Add a sample `.env.example` to the repo.
- Add badges / CI configuration.
- Generate more detailed docs for API endpoints in `src/controllers`.

---
_File created automatically by project assistant._
