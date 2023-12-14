# Project Update

<api-title>
<api-url>
<discord-id>
<discord-title>  <!-- Join King Tech's Community -->
<homepage-logo-url> <!-- https://github.com/<repo-account>/<project-name> -->
<homepage-url>
<main-lang>
<main-file>
<name-alt-title>
<project-description>
<project-name-email>
<project-name>
<repo-account> <!-- Rohit19060/king-technologies-->
<video-id>
<video-title>

1. Add License

2. Update Package.json

```JSON
 {
  "name": "<project-name>",
  "version": "1.0.0",
  "description": "<project-description>",
  "author": {
    "name": "Rohit Jain",
    "email": "rohitjain19060@gmail.com",
    "url": "https://kingtechnologies.in/"
  },
  "contributors": [],
  "main": "<main-file>",
  "homepage": "<homepage-url>",
  "private": true,
  "repository": {
    "type": "git",
    "url": "https://github.com/<repo-account>/<project-name>"
  },
  "bugs": {
    "url": "https://github.com/<repo-account>/<project-name>/issues"
  },
  "dependencies": {
    "react-scripts": "4.0.2",
    "web-vitals": "^1.0.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "dev": "concurrently \" nodemon server\" \" npm run start\"",
    "serve": "node server",
     "migrate": "postgrator --config postgrator-config.js",
    "migrate:test": "env NODE_ENV=test npm run migrate",
    "migrate:production": "heroku run npm run migrate",
    "predeploy": "npm audit",
    "deploy": "git push heroku main"
  },
  "devDependencies": {
    "concurrently": "^5.3.0",
    "nodemon": "^2.0.7"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "engines": {
    "node": ">= 15.7.0",
    "npm": ">= 7.0.0",
    "yarn": "^1.22.0"
  },
  "keywords": [
    "real later",
    "watch later",
    "server",
    "client",
    "react",
    "node"
  ],
  "license": "MIT"
}

```

3 Add King Tech Logo Icon on Head before title tag

```HTML
<link rel="shortcut icon" href="https://kingtechnologies.in/assets/images/logo.png" type="image/x-icon" />
```

4. Update README.md

<p align="center">
  <a href="<High-Level Projects/\<homepage-logo-url\>>" title="<name-alt-title>">
    <img src="https://kingtechnologies.in/assets/images/logo.png" width="80px" alt="<name-alt-title>"/>
  </a>
</p>
<h1 align="center">🌟 <name-alt-title> 🌟</h1>
<p align="center"><project-description></p>

<p align="center">
<a href="https://github.com/<repo-account>/<project-name>/blob/master/LICENSE" title="License">
<img src="https://img.shields.io/github/license/<repo-account>/<project-name>?label=License&logo=Github&style=flat-square" alt="<name-alt-title> License"/>
</a>
<a href="https://github.com/<repo-account>/<project-name>/fork" title="Forks">
<img src="https://img.shields.io/github/forks/<repo-account>/<project-name>?label=Forks&logo=Github&style=flat-square" alt="<name-alt-title> Forks"/>
</a>
<a href="https://github.com/<repo-account>/<project-name>/stargazers" title="Stars">
<img src="https://img.shields.io/github/stars/<repo-account>/<project-name>?label=Stars&logo=Github&style=flat-square" alt="<name-alt-title> Stars"/>
</a>
<a href="https://github.com/<repo-account>/<project-name>/issues" title="Issues">
<img src="https://img.shields.io/github/issues/<repo-account>/<project-name>?label=Issues&logo=Github&style=flat-square" alt="<name-alt-title> Issues"/>
</a>
<a href="https://github.com/<repo-account>/<project-name>/pulls" title="Pull Requests">
<img src="https://img.shields.io/github/issues-pr/<repo-account>/<project-name>?label=Pull%20Requests&logo=Github&style=flat-square" alt="<name-alt-title> Pull Requests"/>
</a>
<a href="https://github.com/<repo-account>/<project-name>" title="Repo Size">
<img src="https://img.shields.io/github/repo-size/<repo-account>/<project-name>?label=Repo%20Size&logo=Github&style=flat-square" alt="<name-alt-title> Repo Size"/>
</a>
<a href="https://discord.gg/<discord-id>" title="<discord-title>">
<img src="https://img.shields.io/discord/737854816402800690?color=%236d82cb&label=Join%20Community&logo=discord&logoColor=%23FFFFFF&style=flat-square" alt="Join discord community for <name-alt-title>"/>
</a>
</p>

<p align="center" title="<name-alt-title>"><img src="<./High-Level Projects/assets/images/main.gif>" alt="<name-alt-title>"/></p>

<h2 align="center">🌐 Links 🌐</h2>
<p align="center">
    <a href="https://youtu.be/<video-id>" title="<video-title>">🖥️ Video</a>
    ·
    <a href="https://github.com/<repo-account>/<project-name>" title="<name-alt-title> Repo">📂 Repo</a>
    ·
    <a href="<High-Level Projects/\<homepage-url\>>" title="Visit">✨ Live View</a>
    ·
    <a href="<High-Level Projects/\<api-url\>>" title="<api-title>">🛳 API</a>
    ·
    <a href="https://github.com/<repo-account>/<project-name>/issues/new/choose" title="🐛Report Bug/🎊Request Feature">🚀 Got Issue</a>
</p>

## 🚀 Features

- **Store Links in JSON**

- **Easy form**

- **A couple of Sort types**

## 🦋 Prerequisite

- [Python](https://www.python.org/ "Python") Installed

- Basic Understanding of [HTML](https://youtu.be/JHv2jmnrLlA "HTML - First Step Towards Web Development")

- Basic Understanding of [CSS](https://youtu.be/d1tP7ow7HbQ "CSS - Second Step Towards Web Development")

- Basic Understanding of JavaScript

- Basic Understanding of [React](https://reactjs.org/ "React")

- Basic Understanding of [Express](https://expressjs.com/ "Express")

- Basic Understanding of [Node](https://nodejs.org/ "Node")

- Basic Understanding of [NPM](https://www.npmjs.com/ "NPM")

- Basic Understanding of [JSON](https://www.json.org/ "JSON")

- [XAMPP](https://www.apachefriends.org/download.html "XAMPP") Installed

- Basic Understanding of PHP

## 🛠️ Installation Steps

1. Clone the repository

```Bash
git clone https://github.com/<repo-account>/<project-name>.git
```

2. Change the working directory

```Bash
cd <project-name>
```

3. Install Dependencies

```Bash
npm i
```

4. Run the app using terminal

```Bash
npm run dev
```

**🎇 You are Ready to Go!**

## ❗ Available Commands

In the project directory, you can run:

```Bash
npm start
```

This command will execute `react-scripts start`. The app is built using `create-react-app so this command Runs the app in Development mode. Open [http://localhost:3000](http://localhost:3000) to view it in the browser. You also need to run the server file as well to completely run the app. The page will reload if you make edits. You will also see any lint errors in the console.

```Bash
npm run build
```

This command will execute `react-scripts build`. Builds the app for production to the `build` folder. It correctly bundles React in production mode and optimizes the build for the best performance. The build is minified and the filenames include the hashes. Your app will be ready to deploy!

```Bash
npm run test
```

This command will execute `react-scripts test`. Launches the test runner in the interactive watch mode.

```Bash
npm run dev
```

This command will execute `concurrently "nodemon server" "npm run start"`. For running the server and app together I am using concurrently this helps a lot of MERN applications as it runs both the server (client and server) concurrently. So you can work on them both together.

```Bash
npm run serve
```

This command will execute `node server`, For running the server file on you can use this command.

## 👷 Built with

- [HTML](https://youtu.be/JHv2jmnrLlA "HTML - First Step Towards Web Development"): For creating Markups

- [CSS](https://youtu.be/d1tP7ow7HbQ "CSS - Second Step Towards Web Development"): For Designing

- JavaScript: React is a JavaScript library.

- [React](https://reactjs.org/ "React")

- [Express](https://expressjs.com/ "Express")

- [Node](https://nodejs.org/ "Node")

- [NPM](https://www.npmjs.com/ "NPM")

- [JSON](https://www.json.org/ "JSON")

## 📂 Directory Structure

> [`./server.js`](https://github.com/<repo-account>/<project-name>/blob/main/server.js "server"): Main Server File

> [`./src/*.js`](https://github.com/<repo-account>/<project-name>/tree/main/src "Src Directory"): All React components are in this directory

> [`./docs/**.**`](https://github.com/<repo-account>/bookmark-store/tree/main/docs "Production"): Production Directory

## 🎊 Future Updates

- [ ] Add Direct Youtube Watch Later

## 🧑🏻 Author

**Rohit Jain**

- 🌌 [Profile](https://github.com/Rohit19060 "Rohit Jain")

- 🏮 [Email](mailto:rohitjain19060@gmail.com?subject=Hi%20from%20<project-name-email> "Hi!")

- 🦁 [Website](https://kingtechnologies.in "Welcome")

<h2 align="center">🤝 Support</h2>

<h3 align="center">🎀 Contributions (<a href="https://guides.github.com/introduction/flow" title="GitHub flow">GitHub Flow</a>), 🔥 issues, and 🥮 feature requests are most welcome!</h3>

<h3 align="center">💙 If you like this project, Give it a ⭐ and Share it with friends!</h3>
<h3 align="center">💰 Donations Links</h3>
<p align="center">
<a href="https://www.paypal.me/kingrohitJ" title="PayPal"><img src="https://kingtechnologies.in/assets/images/Paypal.png" alt="PayPal"/></a>
<a href="https://www.buymeacoffee.com/rohitjain" title="Buy me a Coffee"><img src="https://kingtechnologies.in/assets/images/Coffee.png" alt="Buy me a Coffee"/></a>
<a href="https://ko-fi.com/rohitjain" title="Ko-fi"><img src="https://kingtechnologies.in/assets/images/Kofi.png" alt="Ko-fi"/></a>
<a href="https://www.patreon.com/KingTechnologies" title="Patreon"><img src="https://kingtechnologies.in/assets/images/Patreon.png" alt="Patreon"/></a>
</p>

<p align="center">Made with <main-lang> & ❤️ in India</p>

4. Use Grammarly

5. Default FrontEnd Port 3000 & Backend || Server File 8000

6. Server message: `App listening on http://localhost:${port}/`

7. Add Preview image and settings
