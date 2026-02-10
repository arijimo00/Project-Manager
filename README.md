# Project Manager

A web-based project management dashboard for tracking projects, accounts, stakeholders, resources, and delivery timelines — all in a single HTML file powered by Firebase Realtime Database.

## Features

- Dashboard entry form with auto-generated serial numbers
- Account and stakeholder management
- Resource tracking with efficiency levels
- Multi-select checkboxes for stakeholders and resources
- Single and multi-phase delivery date support
- Interactive Gantt chart timeline view
- Cloud persistence via Firebase Realtime Database
- Local session persistence via localStorage

## Tech Stack

- **Frontend**: Vanilla HTML, CSS, JavaScript (single `index.html` file)
- **Backend**: Firebase Realtime Database (v9 compat SDK, loaded via CDN)
- **Deployment**: Static hosting (GitHub Pages, or any static file server)

---

## Getting Started: Creating a New Account

### Prerequisites

Before you can log in, you need a **Firebase Realtime Database**. If you already have one, skip to [Part 2](#part-2-logging-in-to-the-app).

---

### Part 1: Setting Up Firebase (One-Time Setup)

#### Step 1: Create a Google Account

If you don't already have one, go to [accounts.google.com](https://accounts.google.com) and create a free Google account.

#### Step 2: Go to Firebase Console

1. Open your browser and navigate to [console.firebase.google.com](https://console.firebase.google.com).
2. Sign in with your Google account.

#### Step 3: Create a New Firebase Project

1. Click **"Create a project"** (or **"Add project"**).
2. Enter a project name (e.g., `my-project-manager`).
3. You may disable Google Analytics if prompted (it is not required).
4. Click **"Create project"** and wait for it to finish.
5. Click **"Continue"** when ready.

#### Step 4: Set Up the Realtime Database

1. In the left sidebar, click **"Build"** then **"Realtime Database"**.
2. Click **"Create Database"**.
3. Choose a database location (pick the one closest to you).
4. Select **"Start in test mode"** for now (you can update security rules later).
5. Click **"Enable"**.
6. Your database is now created. **Copy the Database URL** shown at the top of the page. It looks like:
   ```
   https://my-project-manager-default-rtdb.firebaseio.com
   ```

#### Step 5: Get Your API Key

1. In the left sidebar, click the **gear icon** next to "Project Overview", then select **"Project settings"**.
2. Scroll down to the **"Your apps"** section.
3. If no app is listed, click the **web icon** (`</>`) to register a new web app:
   - Enter a nickname (e.g., `project-manager-web`).
   - Click **"Register app"**.
4. You will see a code block with your Firebase config. Find the line that says `apiKey:` and **copy the API key value** (the string in quotes).

You now have the two pieces of information needed to log in:
- **Firebase API Key** (from Step 5)
- **Firebase Database URL** (from Step 4)

---

### Part 2: Logging In to the App

#### Step 1: Open the App

Open the Project Manager app in your browser. You will see the login screen with the title **"Welcome to Project Manager"**.

#### Step 2: Enter Your Username

In the **Username** field, type the name you want to use (e.g., `john.doe`). This can be any name you choose -- it will be displayed in the app as your identity.

#### Step 3: Enter Your Firebase API Key

In the **Firebase API Key** field, paste the API key you copied from the Firebase Console (see Part 1, Step 5).

#### Step 4: Enter Your Firebase Database URL

In the **Firebase Database URL** field, paste your database URL. It should look like:
```
https://your-project-name.firebaseio.com
```

#### Step 5: Click Login

Click the **Login** button. The app will:
1. Save your credentials locally so you stay logged in.
2. Connect to your Firebase database.
3. Load any existing data (accounts, stakeholders, resources, projects).
4. Take you to the main dashboard.

You are now logged in and ready to start managing projects.

---

## Returning Users

When you open the app again, you will be **automatically logged in** using your saved credentials. No need to re-enter your details.

## Troubleshooting

| Problem | Solution |
|---|---|
| **"Please enter username, Firebase API key, and Database URL"** | Make sure all three fields are filled in. None can be left blank. |
| **"Invalid Database URL"** | Check that your URL is in the format `https://your-project.firebaseio.com`. It must be a valid URL starting with `https://`. |
| **Data not loading** | Verify that your Firebase Realtime Database is active and the API key is correct. Check the browser console (F12) for error messages. |
| **App loads but shows no data** | This is normal for a new account. Start by adding accounts, stakeholders, and resources in their respective sections. |
