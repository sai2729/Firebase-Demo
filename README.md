# Firebase Demo Project

This repository contains two main sections to help you understand and implement various Firebase features. There are two folders: **Templates** (starter code without Firebase integration) and **Final** (completed code with Firebase integration). Follow the steps below to set up and explore each demo.

## Prerequisites

Before you begin, make sure you have the following installed:
1. **Code Editor**: Recommended - [Visual Studio Code](https://code.visualstudio.com/Download)
2. **Node.js and npm**: [Download Node.js](https://nodejs.org/)
   - Verify the installation by running:
     ```bash
     node -v
     npm -v
     ```
3. **Firebase CLI**: Install using:
   ```bash
   npm install -g firebase-tools
   ```
   - Verify the Installation
   ```bash
   firebase --version
   ```
4. **Firebase Account**: Log in using:
   ```bash
   firebase login
   ```
## Project Folder Structure

### Final
Contains completed code with Firebase integration for:
- **Authentication**
  - `signin.html`
  - `signup.html`
  - `styles.css`
- **CRUD Operations**
  - `crud.html`

### Templates
Contains starter code to begin working on Firebase features:
- **Authentication**
  - `signin.html`
  - `signup.html`
  - `styles.css`
- **CRUD Operations**
  - `crud.html`
# Demo 1: Firebase Authentication

## Prerequisites
- Ensure **Firebase Authentication** is enabled in your Firebase Console.

## Instructions

1. Open the **Authentication** folder inside `Templates`.

2. **Templates:**
   - Add Below script code in `signup.html` to integrate Firebase Authentication.
  ```bash
  <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.14.1/firebase-app.js";
        import { getAuth, createUserWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/10.14.1/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "fir-demoinclass-b92f4.firebaseapp.com",
            projectId: "fir-demoinclass-b92f4",
            storageBucket: "fir-demoinclass-b92f4.appspot.com",
            messagingSenderId: "683282127140",
            appId: "1:683282127140:web:87ff88f2c3b37fd803bbb1",
            measurementId: "G-96RSW4N00E"
        };

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const auth = getAuth();
        function signUp() {
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;
            createUserWithEmailAndPassword(auth, email, password)
                .then((userCredential) => {
                    // Signed up successfully
                    alert("Sign Up Successful");
                    console.log(userCredential);
                })
                .catch((error) => {
                    alert("Error: " + error.message);
                });
        }

        // Attach the function to the global scope
        window.signUp = signUp;
    </script>
  ```
   - Add Below script code in `signin.html` to integrate Firebase Authentication.
   ```bash
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.14.1/firebase-app.js";
        import { getAuth, signInWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/10.14.1/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "fir-demoinclass-b92f4.firebaseapp.com",
            projectId: "fir-demoinclass-b92f4",
            storageBucket: "fir-demoinclass-b92f4.appspot.com",
            messagingSenderId: "683282127140",
            appId: "1:683282127140:web:87ff88f2c3b37fd803bbb1",
            measurementId: "G-96RSW4N00E"
        };

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const auth = getAuth();
        function signIn() {
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;
            signInWithEmailAndPassword(auth, email, password)
                .then((userCredential) => {
                    // Signed in
                    alert("Sign In Successful");
                    console.log(userCredential);
                })
                .catch((error) => {
                    alert("Error: " + error.message);
                });
        }

        window.signIn = signIn;
    </script>
   ```

4. **Run the Project:**
   - Open the HTML files in your browser and test the **Sign Up** and **Sign In** functionalities.

