---
name: portfolio-manager
description: >-
  Manages, updates, and deploys Wanitus Kudchabootr's personal portfolio website and GitHub Pages.
  Use when the user asks to modify profile info, add career experience, adjust styles, or deploy changes to https://wanitus.github.io.
---

# Wanitus Kudchabootr - Portfolio & Project Runbook

This skill provides all project context, profile data, architecture standards, and deployment workflows for Wanitus Kudchabootr's personal web portfolio.

---

## 1. Owner Profile & Biography (Reference Data)

- **Name**: Wanitus Kudchabootr (วนิตัส กุดฉะบุตร)
- **Role**: Senior Data Engineer / Data Management Specialist
- **Current Company**: CANA ENTERPRISE CO.,LTD. (Onsite at True Corporation Public Co., Ltd.)
- **Email**: `wanitus@gmail.com`
- **LinkedIn**: [wanitus-kudchabootr-10950a135](https://www.linkedin.com/in/wanitus-kudchabootr-10950a135/)
- **GitHub**: [Wanitus](https://github.com/Wanitus)
- **Live URL**: [https://wanitus.github.io](https://wanitus.github.io)

### Career History (5 Companies)
1. **CANA ENTERPRISE CO.,LTD.** (Apr 2024 – Present): Senior Data Engineer / Data Management Specialist (True Corp Onsite) — Big Data, Kubernetes, Docker, Airflow, Python, Vertica, Hadoop, Hive, AWS S3.
2. **True Digital Group** (Dec 2019 – Mar 2024): Engineer Specialist — Python & REST API automated reporting (Vending Machine, KE, EDCP), DialogFlow (Robocore), GCP, AWS.
3. **V-Smart Co., Ltd.** (Jul 2016 – Nov 2019): Senior ETL Developer — Lead ETL development, BI Architecture, data mapping, ETL performance tuning.
4. **Extend IT Resource Co., Ltd.** (May 2012 – Jul 2016): ETL Developer — ETL workflows, DataStage, SSIS, ODI, SIT/UAT testing, PL/SQL.
5. **Bank of Ayudhya Public Co., Ltd. (Krungsri)** (Jul 2006 – Apr 2012): Computer Officer — Mainframe batch processing, workflow monitoring, banking operations.

### Education
- **Master's Degree (M.Sc. IT)**: King Mongkut's University of Technology Thonburi (KMUTT บางมด, 2013 – 2015)
- **Bachelor's Degree (B.Sc. Computer Tech)**: Rajamangala University of Technology Thanyaburi (RMUTT ธัญบุรี, 2002 – 2006)

---

## 2. Website Structure & Design System

- **Workspace Path**: `C:\Users\Wanitus Kudchabootr\my-project`
- **Pages**:
  - `index.html`: Landing page with profile hero, highlights, core skills, and links.
  - `experience.html`: Detailed employment timeline, key projects, education, and credentials.
- **Design Language**:
  - Dark Cyberpunk / Sci-Fi High-Tech Glassmorphism
  - Background: `#070913` with ambient radial glowing gradients and grid lines.
  - Accent Colors: Neon Cyan (`#00f5ff`), Neon Magenta (`#ff007f`), Neon Purple (`#8b5cf6`), Emerald (`#10b981`).
  - Typography: Google Fonts `Prompt` (Thai & English body) + `Space Grotesk` (Tech numbers & badges).

---

## 3. Deployment Runbook (GitHub Pages)

Whenever changes are made to `index.html` or `experience.html`, follow this exact workflow to publish:

```bash
cd "C:\Users\Wanitus Kudchabootr\my-project"
git add index.html experience.html
git commit -m "<Clear description of change>"
git push origin main
```

- GitHub Pages automatically deploys branch `main` to `https://wanitus.github.io`.
- Changes typically take **15–30 seconds** to go live.
- Verification command:
  ```powershell
  curl.exe -s -o NUL -w "%{http_code}" https://wanitus.github.io
  ```

---

## 4. Automation & Scraping Guidelines

- **LinkedIn Scraping**: LinkedIn WAF blocks Python `requests` with `HTTP 999: Request Denied` due to TLS/JA3 fingerprinting.
  - **Solution**: Always use Windows built-in `curl.exe` with a Chrome User-Agent via `subprocess.run(["curl.exe", ...])`.
- **Windows Console Output**: Always include this at the top of Python scripts to prevent `UnicodeEncodeError`:
  ```python
  import sys
  if hasattr(sys.stdout, "reconfigure"):
      sys.stdout.reconfigure(encoding="utf-8")
  ```
