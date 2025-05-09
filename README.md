# 🏏IPL T20 Dashboard

## Overview
A mobile-first, responsive web application that provides real-time IPL T20 updates—featuring live match info, upcoming matches, points table, and the full season schedule. Built with Next.js, TypeScript, Tailwind CSS, and custom Node.js API scraping.

### 🛠️ **Technical Implementation**

- Built using **Next.js** with SSR/ISR for real-time data updates
- Typed with **TypeScript** for type safety and scalability
- Styled with **Tailwind CSS** following a mobile-first approach
- Developed a **custom API route** (`/api/scrape`) to:
  - Scrape data from `https://www.iplt20.com/`
  - Return structured JSON for UI consumption
  - Handle dynamic or JavaScript-rendered content via Puppeteer (if needed)
- Used **dummy data** as a fallback in case of scraping issues
- Ensure **revalidation / periodic updates** (every X mins)
- Created **responsive UI components** for mobile, tablet, and desktop

### 🎨 **User Interface (UI)**

- Mobile-first layout for a seamless small-screen experience
- Dashboard-inspired layout for live & upcoming match focus
- ESPN Cricinfo-style inspiration for match and table layout
- Clean separation of pages:
  - `/` - Dashboard (Live/Upcoming Match)
  - `/points-table`
  - `/schedule`

### 🔌 API Routes (```/api/scrape```)

Handles scraping from ```https://www.iplt20.com/``` Fetches:

- 🔴 Live Match Details

- 🏁 Upcoming Matches

- 🧮 Points Table

- 📆 Full Match Schedule

### Note:

- Data is refreshed periodically using ISR (Incremental Static Regeneration).

- In case of scraping failure, a structured dummy dataset is used for fallback.

### 📱 UI Screens

- **Home**: Displays live or next match prominently.

- **Points Table**: Shows latest team rankings, wins/losses, NRR.

- **Schedule Page**: Lists all matches in a calendar-like format.

- **Responsive Design**: Optimized for mobile, tablet, and desktop.

### 🧹 Scraping Methodology

- Utilized Cheerio for parsing static HTML.

- In case of heavy dynamic content, fallback to Puppeteer (headless browser).

- Extracted data using DOM selectors from:

    - /matches

    - /points-table

    - /schedule

- Set up scheduled revalidation to update every 5–10 minutes (depending on page).

### ❗ Challenges

- Anti-scraping mechanisms on ```iplt20.com``` (e.g., JS rendering).

- Dynamic loading of content required Puppeteer in some views.

- Rate limits required throttling and error handling.

### 🌟 **Bonus Features (Optional )**

- Implement **caching** for scraper data (e.g., Redis or in-memory)
- Enable **real-time notifications** for key match events
- Add **charts/graphs** for team performance trends
- Include **historical match stats** or player insights

## 📁 Project Structure

```bash
.
├── components/        # Reusable UI components
├── pages/
│   ├── api/scrape.ts  # Serverless API for scraping
│   ├── index.tsx      # Main dashboard
│   ├── points-table.tsx
│   ├── schedule.tsx
├── public/            # Static assets
├── styles/            # Tailwind/custom CSS
├── types/             # TypeScript interfaces
├── utils/             # Helper functions (e.g., formatTime)
└── data/              # Dummy data fallback
```

## Installation 

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ipl-live-dashboard.git
   ```
2. Navigate to the project directory:
   ```bash
   cd ipl-live-dashboard
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the development server:
   ```bash
   npm run dev
   ```

## Contact
For any questions or feedback, please contact:
- Email: [ravisharma50063@gmail.com](mailto:ravisharma50063@gmail.com)
- GitHub: https://github.com/ravigithub19

