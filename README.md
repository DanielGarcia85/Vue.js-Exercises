# Vue.js Exercises

This repository contains a series of exercises and tutorials aimed at learning the basics of the **Vue.js** framework using **HTML**, **JavaScript**, and **CSS**, and modern tool such as **Vite**, **Vue Router**, **ESLint** and **Prettier**. These exercises were developed as part of the ***65-41 Interschool Software Development*** course at **Haute École de Gestion (HEG)**.

## Prerequisites

Before starting, make sure you have:
- A modern browser (Chrome, Firefox, Edge...)
- A code editor (*VS Code recommended*)
- Node.js (LTS version recommended)
- npm or yarn for package management
- Basic knowledge of JavaScript and Vue.js

## Project Overview

The project is organized into several levels, each introducing different concepts of Vue.js:
- **Tuto/** : A tutorial explaining certain concepts of **Vue.js** with an example of a **child component**.
- **Level0/** : First introductory exercise to **Vue.js** with **HTML** and **JavaScript**.
- **Level1/** : More advanced exercises integrating **CSS** for styling.
- **Level2/** : A comprehensive Vue.js 3 project leveraging Vite for efficient development, Vue Router for dynamic navigation, and structured component-based design for modularity.

## Level 2 Management with Vue.js

The Level 2 folder contains an advanced Vue.js project focused on order management, demonstrating Vue Router, component-based architecture, and structured state management.

### Project Structure:
- index.html : The html outside of the vue app (should not be edited, except for icon and title)
- src/App.vue : The root Vue component (the main Vue View).
- src/main.js : Entry point for mounting the Vue application, where the vue app is created and configured with plugins like vue-router
- src/router/index.js : Defines application routes using Vue Router.
- src/assets/ : Contains CSS stylesheets.
- src/views/OrdersView.vue : Displays a list of orders.
- src/views/OrderAdd.vue : Provides a form for adding new orders.

### Technologies Used
- Vue 3
- Vite (for fast development and build)
- Vue Router (for navigation)
- ESLint & Prettier (for code formatting and quality control)

## Usage

### For Level 0 % Level 1

1. Clone this repository.
2. Open the `.html` files in a browser or serve them via a local server.
3. Explore and modify the files to better understand the workings of **Vue.js**.

### For Level 2

1. Install dependencies:
```shell
npm install
````
2. Run the following command to auto fix formatting and see errors:
```shell
npm run lint
npm run format
```
3. Start the development server:
```shell
npm run dev
````
4. Access the application at:
```shell
http://localhost:5173
```

## Useful Resources

- **Tutorial** : [https://vuejs.org/tutorial/](https://vuejs.org/tutorial/)
- **Level 0** : [https://learn.fritscher.ch/codelabs/vuejs-level-0/](https://learn.fritscher.ch/codelabs/vuejs-level-0/)
- **Level 1** : [https://learn.fritscher.ch/codelabs/vuejs-level-1/](https://learn.fritscher.ch/codelabs/vuejs-level-1/)
- **Level 2** : [https://learn.fritscher.ch/codelabs/vuejs-level-2/](https://learn.fritscher.ch/codelabs/vuejs-level-2/)

## License

This project is licensed under the *Creative Commons Attribution-ShareAlike (CC BY-SA)* license.

## Author

Project created by **Daniel Garcia** as part of the course ***65-41 Interschool Software Development*** at **Haute École de Gestion (HEG)** during the Spring semester of 2025.
