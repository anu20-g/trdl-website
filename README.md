# TEWARY RESEARCH AND DEVELOPMENT LAB (TRDL)
## Official Sovereign Laboratory Web Suite

This directory contains the production web distribution for the official **Tewary Research and Development Lab (TRDL)** laboratory portal.

### Directory Structure
```
TRDL_OFFICIAL_WEBSITE/
├── index.html                   # Primary Sovereign Laboratory Terminal
├── directorates.html            # Directorates 01–13 (Physics, NOIR AI, Defense, Biotech)
├── fellowships.html             # Active Fellowship Cohort (Rajat Prajapati & Aayush Agarwal)
├── verification.html            # Statutory Registry, Zero-Mock Mandate, MSME/NIC Ledger
├── styles.css                   # High-contrast scientific terminal stylesheet
├── assets/
│   └── trdl_mark.svg            # Laboratory vector insignia
├── firebase.json                # Firebase Hosting configuration
├── .firebaserc                  # Firebase project alias
├── netlify.toml                 # Netlify edge deployment configuration
└── .github/
    └── workflows/
        └── deploy.yml           # GitHub Pages automated CI/CD deployment
```

---

### Deployment Runbooks

#### 1. Firebase Hosting Deployment
```powershell
# In terminal, navigate to TRDL_OFFICIAL_WEBSITE:
cd "c:\Users\Anurag Tewary\Documents\TRDL\TRDL_OFFICIAL_WEBSITE"

# 1. Install Firebase CLI globally (if not already installed):
npm.cmd install -g firebase-tools

# 2. Login to Firebase:
firebase login

# 3. Associate with your Firebase project:
firebase use --add

# 4. Deploy to Firebase CDN:
firebase deploy --only hosting
```

#### 2. GitHub Pages Deployment
- Push the repository to GitHub on branch `main`.
- In your GitHub Repository:
  1. Navigate to **Settings** &rarr; **Pages**.
  2. Under **Build and deployment** &rarr; **Source**, select **GitHub Actions**.
  3. The workflow in `.github/workflows/deploy.yml` will automatically build and publish `./TRDL_OFFICIAL_WEBSITE`.

#### 3. Netlify Deployment
- **Git Continuous Deployment:** Link your GitHub repo to Netlify. Set **Publish directory** to `TRDL_OFFICIAL_WEBSITE`. Netlify will read `netlify.toml` and deploy automatically on every push.
- **Manual CLI Deployment:**
  ```powershell
  npm.cmd install -g netlify-cli
  netlify login
  netlify deploy --dir=. --prod
  ```
