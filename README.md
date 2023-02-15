This is a starter template for [Learn Next.js](https://nextjs.org/learn).
Process to migrate to next js
### 1- remove react scripts (npm uninstall react-scripts).
### 2- In package.json file remove the old scripts add these new one:
 "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
### 3- Create next.config.js file and paste the following code in it:
module.exports = {
  reactStrictMode: true,
};
### 4- Create Pages folder inside src folder.
### 5- create files index.js and _app.js inside the pages folder.
### 6- index.js is the entry point of application so migrate the code from app.js to index.js and change the functional component name from App to Home.
### 7- Open _app.js file paste the following code in it:
import { FirebaseContextProvider } from "../contexts/firebaseContex";
import "../styles/globals.scss";

function App({ Component, pageProps }) {
  return (
    <FirebaseContextProvider>
      <Component {...pageProps} />;
    </FirebaseContextProvider>
  );
}

export default App;
### 8- Delete the old index.js and App.js files.
### 9- Move all images and static assets inside the public folder.
### 10- for styles create styles folder at root and create a file globals.scss init and paste your all styles init.
### 11- As DifferentAccountCheckPopup component is using its seperate styles file so rename DifferentAccountCheckPopUP.css to DifferentAccountCheckPopUP.module.css.
### 12- Inside DifferentAccountCheckPopUP.js file import its styles as:
import styles from "./DifferentAccountCheckPopUP.module.css";
### 13- change  the css classes names to camelCase as now they are accessible as properties of obj eg styles.popupBox.
### 14- Delete the index.html file from public folder. 
