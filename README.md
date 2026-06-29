# Annamayya Police Smart Policing — Performance Dashboard

A modern, high-performance single-page web dashboard for tracking and analyzing technology adoption and application usage metrics across all 28 Police Stations in the Annamayya District. 

---

## 🚀 How to Host Live on GitHub Pages

Since the dashboard is built entirely with static files (HTML, CSS, JS, and JSON data files), you can publish it live to the web for free using **GitHub Pages**:

1. **Push your code to GitHub**:
   Ensure all your latest local commits are pushed to your remote repository:
   ```bash
   git push origin main
   ```

2. **Go to Repository Settings**:
   * Open your browser and navigate to your GitHub repository: [annamayyapolice/annamayyapolice.github.io Settings/Pages](https://github.com/annamayyapolice/annamayyapolice.github.io/settings/pages).
   * Or click the **Settings** tab at the top of your GitHub repository page and select **Pages** from the left-hand sidebar (under the "Code and automation" section).

3. **Configure Build and Deployment**:
   * Under **Build and deployment** -> **Source**, choose **"Deploy from a branch"**.
   * Under **Branch**, select **`main`** (or the default branch) and set the folder dropdown next to it to **`/(root)`**.
   * Click **Save**.

4. **Access the Live URL**:
   * GitHub will automatically start a deployment action. After about 1-2 minutes, refresh the settings page.
   * A banner will appear at the top showing your live URL, which will look like:
     👉 **[https://annamayyapolice.github.io/](https://annamayyapolice.github.io/)**

---

## 🛠️ Local Development & Running

To run the dashboard locally on your computer:

1. Open a terminal or PowerShell window in the project folder.
2. Start a local HTTP server:
   ```bash
   python -m http.server 8000
   ```
3. Open your browser and go to `http://localhost:8000/index.html`.

---

## 📈 Updating Dashboard with New Weekly Data

When you receive a new raw Excel sheet (e.g., `PS wise DATA 04062026-10062026.xlsx`):

1. Put the new raw Excel file in the root directory.
2. Update the filename reference inside [compile_week.py](file:///compile_week.py) if the date range changes.
3. Run the compiler script:
   ```bash
   python compile_week.py
   ```
   *This script compiles the raw sheets, saves the compiled workbook to `data/weeks/`, and automatically runs `process_excel.py` and `make_manifest.py` to regenerate the JSON database and update the dashboard manifest.*
4. Commit and push the updated files to GitHub to deploy them live:
   ```bash
   git add .
   git commit -m "update dashboard data for week 04.06.2026 to 10.06.2026"
   git push origin main
   ```