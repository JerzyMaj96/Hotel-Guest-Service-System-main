# Hotel Guest Service System

A hotel guest service platform that allows guests to report issues (technical or reception-related), attach photos, and track resolution status. Hotel staff can manage and update reported issues.

## Requirements

- [Docker](https://www.docker.com/products/docker-desktop) installed and running

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/JerzyMaj96/Hotel-Guest-Service-System-main.git
cd Hotel-Guest-Service-System-main
```

### 2. Create the environment file

```bash
cp .env.example .env
```

Fill in the values in `.env`:

```env
DB_USERNAME=        # PostgreSQL username
DB_PASSWORD=        # PostgreSQL password
JWT_SECRET=         # Base64-encoded secret key for JWT signing (HS256, min. 32 bytes)
                    # Generate with: openssl rand -base64 32
TWILIO_ACCOUNT_SID= # Twilio Account SID (for SMS notifications)
TWILIO_AUTH_TOKEN=  # Twilio Auth Token
TWILIO_PHONE_NUMBER= # Twilio phone number (e.g. +13168447607)
```

> If you don't have a Twilio account, SMS notifications won't work but the rest of the app will run fine.

### 3. Run the application

```bash
docker compose up
```

The following services will start:

| Service | URL |
|---------|-----|
| Frontend | http://localhost:3001 |
| Backend API | http://localhost:8081 |
| Mailpit (email UI) | http://localhost:8027 |
| PostgreSQL | localhost:5433 |

### 4. Stop the application

```bash
docker compose down
```

> To also remove stored data (database, uploaded photos): `docker compose down -v`
