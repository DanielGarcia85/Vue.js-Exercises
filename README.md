# Vue.js Exercises

This repository contains a series of exercises and tutorials aimed at learning the basics of the **Vue.js** framework using **HTML**, **JavaScript**, and **CSS**, developed as part of the ***65-41 Interschool Software Development*** course at **Haute École de Gestion (HEG)**.

## Structure of the Project

The project is organized into several folders:
- **Tuto/** : A tutorial explaining certain concepts of **Vue.js** with an example of a **child component**.
- **Level0/** : First introductory exercise to **Vue.js** with **HTML** and **JavaScript**.
- **Level1/** : More advanced exercises integrating **CSS** for styling.
- **Level2/** : Advanced exercises focused on building a Vue.js project with routing and component-based architecture.

## Prerequisites

Before starting, make sure you have:
- A modern browser (Chrome, Firefox, Edge...)
- A code editor (*VS Code recommended*)

## Usage

1. Clone this repository.
2. Open the `.html` files in a browser or serve them via a local server.
3. Explore and modify the files to better understand the workings of **Vue.js**.

## Exercise Content

- **Tuto/tuto.html** : A tutorial detailing the use of **Vue.js** components.
- **Tuto/childComp/ChildComp.js** : A **JavaScript** file defining a **Vue.js child component**.
- **Tuto/css/style.css** : Stylesheet for the **Vue.js** tutorial.
- **Level0/index.html** : Introduction to **Vue.js** with basic directives in **HTML** and **JavaScript**.
- **Level1/index.html** : Exercises integrating **CSS** and more advanced **Vue.js** functionalities.
- **Level2/** : A complete Vue.js 3 project structured with Vite and using Vue Router for navigation.

## LEvel2 Management with Vue.js

The Level2 folder contains an advanced Vue.js project focused on order management, demonstrating Vue Router, component-based architecture, and structured state management.

### 📂 Project Structure:
- index.html : The html outside of the vue app (should not be edited, except for icon and title)
- src/App.vue : The root Vue component (the main Vue View).
- src/main.js : Entry point for mounting the Vue application, where the vue app is created and configured with plugins like vue-router
- src/router/index.js : Defines application routes using Vue Router.
- src/assets/ : Contains CSS stylesheets.
- src/views/OrdersView.vue : Displays a list of orders.
- src/views/OrderAdd.vue : Provides a form for adding new orders.

###🚀 Installation and Running the Project

1. Install dependencies:
npm install
2. Start the development server:
npm run dev
3. Access the application at:
http://localhost:5173

### ⚙️ Technologies Used
- Vue 3
- Vite (for fast development and build)
- Vue Router (for navigation)
- ESLint & Prettier (for code formatting and quality control)

## Useful Resources

- **Tutorial** : [https://vuejs.org/tutorial/](https://vuejs.org/tutorial/)
- **Level 0** : [https://learn.fritscher.ch/codelabs/vuejs-level-0/](https://learn.fritscher.ch/codelabs/vuejs-level-0/)
- **Level 1** : [https://learn.fritscher.ch/codelabs/vuejs-level-1/](https://learn.fritscher.ch/codelabs/vuejs-level-1/)
- **Level 2** : [https://learn.fritscher.ch/codelabs/vuejs-level-2/](https://learn.fritscher.ch/codelabs/vuejs-level-2/)

## License

This project is licensed under the *Creative Commons Attribution-ShareAlike (CC BY-SA)* license.

## Author

Project created by **Daniel Garcia** as part of the course ***65-41 Interschool Software Development*** at **Haute École de Gestion (HEG)** during the Spring semester of 2025.
