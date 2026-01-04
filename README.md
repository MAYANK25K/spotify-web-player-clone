# Spotify Web Player Clone 🎧

![Project Status](https://img.shields.io/badge/status-active-success.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

A responsive, JavaScript-driven music player that replicates the core functionality and UI of Spotify. This project challenges the standard static website by implementing a **custom audio engine**, **dynamic file handling**, and **professional-grade CSS animations**.

---

## 📸 Demo & Screenshots

**[Link to Video Demo / Live Site]**

![App Screenshot](assets/screenshot-desktop.png)
*(Note: Create an 'assets' folder and add your screenshots there)*

---

## ✨ Key Features

* **Dynamic Content Parsing:** Unlike standard static sites, this app uses `async/await` and the `Fetch API` to scan local directories, automatically generating albums and song lists. This mimics a CMS (Content Management System) behavior.
* **Custom Audio Engine:** Built entirely on the HTML5 `Audio()` API with custom logic for:
    * Real-time seek bars (updates every second).
    * Volume parsing and muting logic.
    * Track persistence (Next/Previous logic).
* **✨ High-Fidelity Animations:** Focused heavily on "Micro-Interactions" to improve UX:
    * **Floating Play Button:** Implemented complex CSS transitions (`transition: all 1s ease-out`) on playlist cards. The play button smoothly slides up and fades in on hover, exactly like the real Spotify app.
    * **Responsive Sidebar:** The mobile menu (`left` panel) utilizes smooth sliding transitions (`transition: all .3s`) instead of jarring jumps when toggling the hamburger menu.
    * **Interactive Seekbar:** The seek circle glides instantly with user interaction, providing responsive feedback.
* **Event-Driven UI:** The interface relies heavily on Event Listeners (`timeupdate`, `loadeddata`, `click`) to ensure the UI stays perfectly synced with the audio state.

---

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3 (Utility-first methodology similar to Tailwind).
* **Logic:** JavaScript (ES6+).
* **Concepts:** DOM Manipulation, Asynchronous Programming, CSS Variables (`:root`), CSS Transitions & Hover States.

---

## ⚠️ How to Run This Project (Important)

Because this project uses the `fetch()` API to read local file directories for the songs, **browser security policies (CORS) will block the script if you open `index.html` directly via double-click.**

You **must** use a local server to run this:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/spotify-web-player-clone.git](https://github.com/YOUR_USERNAME/spotify-web-player-clone.git)
    ```
2.  **Open in VS Code:**
    ```bash
    code spotify-web-player-clone
    ```
3.  **Launch Server:**
    * Install the **"Live Server"** extension in VS Code.
    * Right-click `index.html` and select **"Open with Live Server"**.

---

## 💡 Lessons Learned

* **The Physics of UI:** I learned that `transition: all .9s` creates a luxurious, "heavy" feel for the cards, whereas the sidebar needed a faster `.3s` transition to feel snappy on mobile. Tuning these values was critical for the professional feel.
* **The Power of Async/Await:** I initially struggled with songs not loading before the UI rendered. I learned to use `async` functions to ensure the folder structure was fully parsed before attempting to play music.
* **Audio State Management:** Handling the edge cases of the `Audio` object (e.g., what happens if the user clicks "Next" continuously?) taught me a lot about defending against runtime errors.

## 🔮 Future Improvements

* **Authentication:** Integrate Firebase to allow users to create their own accounts.
* **Persistent Storage:** Use `localStorage` to save the last played song and volume preference so it persists on page refresh.