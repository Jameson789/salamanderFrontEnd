## 🛠️ Development Plan

This plan outlines the structured steps for building the **Salamander Tracker** React frontend. It covers setup, feature implementation, and testing using Cypress.

---

### 1. 🏗️ Setup

- Initialize the React app (or Next.js if preferred)
- Install necessary dependencies:
  - `react-router-dom`
  - `@mui/material`
  - Other libraries as needed (`axios`, `cypress`, etc.)
- Organize project structure:
  - Create a `components/` folder
  - Remove default Vite boilerplate and styles

---

### 2. 🧭 Routing & Layout

- Set up React Router with the following routes:
  - `/videos` – Video list page
  - `/preview/:filename` – Video preview and settings page
- Build a basic layout (optional header or nav)

---

### 3. 📼 Video Chooser Page

- Display a list of mock videos from `mock/videos.js`
- Enable navigation to the preview page on click

---

### 4. 🔍 Video Preview Page

- Show:
  - Original thumbnail image
  - Binarized thumbnail with centroid
- Include interactive controls:
  - Threshold slider
  - Target color picker
- Add functionality:
  - “Process Video” button
  - Job status display
  - Download link to result CSV

---

### 5. 🖼️ Image Logic

- Convert the thumbnail image to binary using:
  - Selected color
  - Threshold value
- Detect the largest connected region
- Calculate and render the centroid on the binarized image
- Reimplement your Java logic in JavaScript

---

### 6. 🔄 Processing Jobs

- Implement job submission:
  - `POST /process/{filename}?targetColor=<hex>&threshold=<int>`
- Track job status via polling:
  - `GET /process/{jobId}/status`
- Display download link when job is complete

---

### 7. 🧪 Testing (Cypress)

- Use Cypress for end-to-end testing

#### `/videos` – Video Chooser Page

- Renders list of videos from mock data
- Navigates to preview page on selection

#### `/preview/:filename` – Video Preview Page

- Loads original and binarized thumbnails
- Updates binarized image on slider/color input
- Displays centroid marker
- Submits processing job correctly
- Tracks job status and displays CSV download

---

### 8. 🎨 Final Touches & Styling

- Apply consistent design with Material UI
- Add favicon, custom title, and UI polish
- Final code cleanup and deployment prep
