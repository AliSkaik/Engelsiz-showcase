# Engelsiz | Accessibility Web Platform (Showcase)

**Engelsiz** is a production web platform designed to improve accessibility for disabled individuals.
This repository is a **public showcase** of the project's purpose, features, technology stack, and my part in it.
> ⚠️ The **source code is proprietary** and not included in this repository.

---

## 🌟 Project Purpose
Empower people with disabilities, older adults, and other mobility-challenged individuals by providing digital tools that make navigating urban environments easier. The project aims to reduce accessibility barriers and offer reliable information about the accessibility of public spaces, buildings, and services.

---

## 🚀 Features
- Interactive maps powered by OpenLayers, highlighting accessible routes and locations.
- Users can view accessibility ratings, photos, and reviews for markets, restaurants, buildings, and other points of interest.
- Designed for users with a wide range of abilities, including mobility, visual, or cognitive impairments, as well as older adults and pregnant individuals. (in progress)
- Continuous UI/UX improvements informed by user reviews and accessibility reports.

---

## 👤 My Role
Built at AnkaGeo by a small team between August 2025 and March 2026, then handed over to the organisation that runs it today. I was one of its two main developers: 212 of the project's 461 commits are mine, across the full stack.

- **Frontend foundation.** Set up the React application the rest of the team built on.
- **Features.** The place-adding flow, photo management, an accessibility editor, an admin panel refactor and keyboard accessibility.
- **Map performance.** See below.

---

## ⚡ Map Performance
A map of places across a whole country gets slow if the browser downloads and draws every place at once. Two changes kept it fast:

- **Load only what is on screen.** When the user stops panning or zooming, the map sends its current extent, and the backend adds a `BBOX` filter to its GeoServer WFS request, so only the places in view travel over the network.
- **Cluster nearby places.** Places closer than a set distance on screen are grouped into one marker, using OpenLayers' clustering. Each cluster's colour blends the accessibility ratings of the places inside it, and marker styles are cached and reused instead of being rebuilt on every render.

---

## 🛠 Tech Stack
- **Frontend:** React 19, TypeScript, Vite, Redux Toolkit, OpenLayers, Capacitor (mobile wrapper)
- **Backend:** Node.js, Express 5, TypeScript, Sequelize
- **Data and maps:** PostgreSQL, GeoServer (WFS)

---

## 🌍 Live Project
**Visit:** https://engelsizulasim.org

---

## 📄 Notes
This repository is for **showcase and documentation purposes only**. The production application and source code remain private.
