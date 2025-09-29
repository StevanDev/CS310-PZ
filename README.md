## Bioskop MERN + MySQL (XAMPP 3306)

- **Backend**: Express + Sequelize MySQL, JWT, Joi, RBAC, paginacija/sort
- **Frontend**: Minimalni React (Vite) sa login zasticenim rutama
- **Baza**: XAMPP MySQL na **3306**, **root** bez lozinke

## Setup

### Baza
1. Pokrenite XAMPP MySQL (port je 3306)
2. U phpMyAdmin kreiraj `bioskop_db`
3. Importujte `server/sql/schema.sql` pa `server/sql/seed.sql`

Admin se automatski kreira pri startu backend-a: `admin@admin.com / admin123`

### Backend
```bash
cd server
npm i
cp .env.example .env
npm run dev
```

### Frontend
```bash
cd client
npm i
npm run dev
```

## API rute (primer)
- `POST /api/auth/register` `{ email, password }`
- `POST /api/auth/login` → `{ token }`
- `GET /api/movies?page=1&limit=10&sort=createdAt&order=desc`
- `POST /api/movies` admin – CRUD nad filmovima
- `GET /api/screenings?movie_id=1`
- `POST /api/reservations` (user) `{ screening_id, seats: [{row_no, seat_no}] }` – vraca 409 ako je sediste zauzeto