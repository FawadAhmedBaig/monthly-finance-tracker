# BizPulse - Monthly Financial Tracker (PWA)

BizPulse is a lightweight, mobile-first Progressive Web Application (PWA) designed for small businesses and individuals to track monthly **Sales**, **Expenses**, and **Net Profit**. It features a grouped triple-bar graph, automatic profit calculation, local offline data storage, and one-tap CSV export.

---

## 🚀 Key Features

- **Grouped Triple-Bar Graph**: Side-by-side monthly visualization comparing Gross Sales, Overhead Expenses, and Net Profit using Chart.js.
- **100% Offline Capable**: Built with a Service Worker (`sw.js`) that caches all application assets, allowing full access even without an active internet connection.
- **Installable (PWA)**: Add BizPulse directly to your phone's home screen (Android and iOS) to run in full-screen standalone mode without browser bars.
- **Auto-Calculated Profit**: Automatically calculates $\text{Profit} = \text{Sales} - \text{Expense}$ in real-time as you type, with manual override support.
- **Summary Cards & KPIs**: Real-time summary tiles showing Total Sales, Total Expenses, Net Profit / Operating Loss, and overall Profit Margin ($ \frac{\text{Profit}}{\text{Sales}} \times 100 $).
- **Multi-Currency Support**: Switch between USD (`$`), PKR (`Rs.`), EUR (`€`), and GBP (`£`) with instant global formatting.
- **Local Data Persistence**: Saves all records to the browser's `localStorage`—no database setup or backend server required.
- **CSV Export**: Download complete records in CSV format for spreadsheet analysis (Excel, Google Sheets).

---

## 📁 Project Directory Structure

```text
bizpulse-finance-tracker/
├── index.html        # Main application file (HTML, Tailwind CSS, Chart.js, and JS logic)
├── manifest.json     # PWA metadata configuration for installation
├── sw.js             # Service Worker for offline asset caching
├── icon.svg          # Vector icon for splash screen and mobile home screen
└── README.md         # Project documentation
```

---

## 🛠️ Getting Started Locally

### Option 1: Direct Browser Launch
1. Clone or download the repository to your computer.
2. Double-click `index.html` to open it in Google Chrome, Microsoft Edge, Safari, or Firefox.

### Option 2: Run with a Local Server (Recommended for PWA testing)
Service Workers require a secure context (`http://localhost` or `https://`):

```bash
# Using Python 3
python -m http.server 8000

# Or using Node.js (npx)
npx serve
```
Open `http://localhost:8000` in your web browser.

---

## 🌐 Free Deployment via GitHub Pages

Follow these steps to host BizPulse for free:

1. **Create a GitHub Repository**:
   - Go to [GitHub](https://github.com) and create a new **Public** repository (e.g., `bizpulse-tracker`).

2. **Push your project files**:
   ```bash
   git init
   git add .
   git commit -m "feat: initial commit for BizPulse PWA"
   git branch -M main
   git remote add origin https://github.com/<your-username>/bizpulse-tracker.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Navigate to your repository's **Settings** tab.
   - In the left sidebar, click **Pages** (under *Code and automation*).
   - Under **Build and deployment** > **Source**, choose **Deploy from a branch**.
   - Under **Branch**, select `main` and keep the directory as `/(root)`.
   - Click **Save**.

4. **Access your site**:
   - GitHub will generate a live URL:
     ```text
     https://<your-username>.github.io/bizpulse-tracker/
     ```

---

## 📱 How to Install and Use Offline on Mobile

### Android (Chrome / Samsung Internet)
1. Open the GitHub Pages link on your mobile browser.
2. Tap the **three-dots menu (⋮)** in the top right corner.
3. Tap **Install app** or **Add to Home screen**.
4. Launch the **BizPulse** icon directly from your home screen or app drawer.
5. *Offline test:* Turn on **Airplane mode**. The app will continue to open, compute, and save your monthly records.

### iOS (Safari)
1. Open the link in Safari.
2. Tap the **Share button** (square with an upward arrow at the bottom).
3. Scroll down and tap **Add to Home Screen**.
4. Confirm by tapping **Add**. Launch the app like a native iOS application.

---

## 🔄 Cache Invalidation & Updates

If you modify `index.html` and push new changes to GitHub, increment the cache key inside `sw.js` to ensure clients get the latest version:

```javascript
// Change v2 to v3, v4, etc.
const CACHE_NAME = 'bizpulse-v3';
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).