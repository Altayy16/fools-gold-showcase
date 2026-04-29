# Fools Gold - Technical Architecture & Showcase

> **Note:** The full source code for *Fools Gold* is currently private as the game is preparing for official release on mobile app stores. This repository serves as a technical showcase outlining the system architecture, DevOps infrastructure, and engineering principles used to build the game.

### 🎮 Play the Preview
The game is currently available to play via the web link below. 
**Note:** The web version will remain accessible until the official launch on the Google Play Store.

[**👉 Click here to play Fools Gold Web Preview**](https://play.devalty.com/)

## 📌 Project Overview
*Fools Gold* is a real-time, turn-based multiplayer RPG. It requires complex server synchronization, strict state management, and a seamless cross-platform experience across Web, iOS, and Android.

## 🛠️ Technology Stack
* **Backend:** PHP, Laravel
* **Database:** MySQL (with complex relational schemas for player inventories and game states)
* **Real-time Communication:** WebSockets for instant turn-based synchronization
* **Cross-Platform / Mobile:** Web core wrapped natively using Capacitor (handling safe-areas, mobile UI, and store constraints)
* **DevOps & Infrastructure:** Self-hosted VPS, Docker, Docker Compose, Nginx

## 🏗️ Core Engineering Highlights

### 1. Real-Time State Management
Built a robust WebSocket infrastructure to handle real-time multiplayer lobbies and turn-based combat, ensuring all clients stay perfectly synchronized with the server's master state.

### 2. Cross-Platform "Write Once, Run Anywhere"
Adopted a monorepo-style approach where the core web project is seamlessly compiled to native iOS and Android platforms via Capacitor. Handled platform-specific UI challenges directly within the unified codebase.

### 3. Centralized Authentication
Engineered a centralized Auth system to manage user accounts and sessions across multiple game portals and web properties securely.

### 4. Disciplined Code Architecture
Maintained a strict test-driven environment. A core engineering rule during this project was ensuring that complex logic refactoring never required altering predefined test files, guaranteeing backward compatibility and system stability. 

### 5. Product & UX Ownership
Maintained strict control over the game's visual and UX integrity:
* Enforced a strict medieval fantasy aesthetic across all generated art assets, rejecting modern or anachronistic environmental elements.
* Overrode standard UI abbreviations (e.g., K/M/B) to display exact, full currency counts, ensuring precise balance visibility for a better player experience.

## 📂 Repository Structure
Explore the folders above to see how the system is put together:
* `/infrastructure` - Docker configurations and server setup.
* `/docs` - System architecture diagrams, WebSocket event structures, and database schemas.
* `/media` - Game screenshots and UI flow.
