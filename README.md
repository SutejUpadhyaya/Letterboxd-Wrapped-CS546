# Letterboxd Wrapped – Movie Analytics Dashboard

A full-stack web application that processes and analyzes Letterboxd viewing history to generate personalized film statistics, insights, and recommendations. Built with Node.js, Express, MongoDB, and Handlebars.

Note: This repository is a fork of a collaborative group project and reflects work I contributed to alongside my teammates.

---

## Features

### Core Functionality
- Upload Letterboxd `.zip` export to load viewing history
- Re-upload data to update statistics over time
- Admin account for managing movie records (add / edit / delete)
- Integration with Letterboxd poster assets

### Personalized Statistics
- Top genres, directors, and actors
- Average user rating
- Difference from global rating averages
- Total hours spent watching movies
- Time-range filtering:
  - all-time
  - past year
  - past month
- Recommendation generation based on viewing patterns
- Tracks watch history across multiple uploads (time-capsule feature)

### User & Social Features
- Public profile pages with comparable user statistics
- Follow other users
- Comment on movie pages
- Manually add or update ratings via database search

---

## Usage

### Seeding Database

Creates the initial database and admin account.

```bash
npm run seed
```

Default admin credentials:

```
Username: admin
Password: admin
```

---

### Starting the Application

```bash
npm start
```

Runs `app.js` and launches the full application.

---

## Application Flow

### Account Creation

Accessible at `/createaccount`.

Users may register with:

- username
- password and confirmation
- age
- optional profile description
- optional Letterboxd zip upload

Validation includes:

- username uniqueness (case-insensitive)
- password equality and hashing
- age validation (13–100)
- client-side and server-side checks

---

### Data Import

Letterboxd exports may be downloaded from:

https://letterboxd.com/settings/data/

Two upload modes are supported:

- full export — detailed analytics
- reduced dataset — faster upload with limited data

Users may also manually search and add films.

---

### Movie Search

Available at `/movies/lookup`.

- search for films by name
- results include release year and director
- selecting `/movies/:id` opens a detailed film page
- films can be added to user statistics

---

### Account Lookup

Available at `/accountlookup`.

- search for users
- view profile statistics
- follow accounts

---

### My Account

Allows users to:

- view personal statistics
- update profile information
- upload or refresh Letterboxd data

---

