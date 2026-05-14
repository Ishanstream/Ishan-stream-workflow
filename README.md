# Ishan-stream-workflow

🎞️ ISHAN Stream: A Private Cinematic Media Portal
ISHAN Stream is a custom-built, responsive video streaming platform designed to host and share high-bitrate engagement and ceremony memories with relatives. This project highlights a problem-solving journey, overcoming storage constraints and API limitations through creative engineering.
🚀 The Engineering Journey: Challenges & Solutions
1. Optimizing Playback Performance
The Problem: Initial hosting on Google Drive led to frequent "Preview Unavailable" errors and significant buffering for high-bitrate 4K content.
The Solution: Migrated the media library to Dropbox, leveraging its superior raw file delivery for smoother streaming.
2. Strategic Resource Management (Cloud-to-Cloud Transfer)
The Problem: Managing a 2GB free storage limit and high data costs for manual uploads of large ceremony files.
The Solution: Implemented "Smart Fetching" using the Dropbox "Save URL" API. Videos were first staged on Google Drive and then transferred directly cloud-to-cloud to Dropbox, bypassing local bandwidth consumption and streamlining the deployment workflow.
3. Dynamic Link Generation & Reliability
The Problem: Static shared links often became unpredictable or reached access limits during peak usage by family members.
The Solution: Developed a JavaScript-based integration using the Dropbox API v2. The portal now generates dynamic shared links on-click and programmatically converts them to raw=1 format for direct browser playback.
4. Automated Authentication (The OAuth 2.0 Milestone)
The Problem: Dropbox Access Tokens expire every 4 hours, which originally required manual intervention to keep the portal live.
The Solution: Architected a persistent authentication system using OAuth 2.0 with Refresh Tokens. Utilizing a local Termux environment to retrieve a permanent refresh_token, the application now autonomously requests new access tokens in the background, ensuring 24/7 uptime without maintenance.
🛠️ Tech Stack
Frontend: HTML5, CSS3 (Glassmorphism & Custom UI)
Typography: Syne, Cormorant Garamond, DM Sans
Logic: Vanilla JavaScript (Async/Await, Fetch API)
Storage & API: Dropbox API v2 (Multi-account orchestration)
Deployment: GitHub / Vercel
✨ Key Features
Session Persistence: Fully automated token refreshing for uninterrupted access.
Distributed Storage: Logic to fetch media across multiple Dropbox accounts to maximize free-tier utility.
Luxury Aesthetic: Premium cinematic UI featuring gold accents and blurred glass effects.
Redundancy: Integrated Google Drive fallback for direct downloads if streaming limits are exceeded.
