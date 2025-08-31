Simple Honeypot Web App
This project is a single-page web application that serves as a simple yet effective honeypot. It simulates a login form to attract and identify automated bots, logging their activity in real time to a Firebase Firestore database. The application is designed to be easy to deploy and understand, making it an excellent starting point for learning about web security and bot detection.

How It Works
The core of this honeypot is a hidden form field. A human user, viewing the rendered webpage, will only see the "Username" and "Password" fields. An automated bot, however, will typically read the raw HTML source code and fill in all available input fields, including the one that is hidden from view.

The application detects a bot when the hidden field is submitted with a non-empty value. The submission, along with other data like the user agent and IP address, is then logged to a Firestore collection, providing a live feed of all detected bot activity.

Features
Bot Detection: Accurately identifies bots by checking for a filled-in hidden form field.

Real-time Logging: Uses Firebase Firestore to log bot submissions and display them instantly on the page.

Single-File Application: The entire project is self-contained within a single index.html file, making it easy to set up and deploy.

Responsive Design: Built with Tailwind CSS, the interface is clean and works well on both desktop and mobile devices.

Setup and Deployment
Firebase Project:

Go to the Firebase Console and create a new project.

Enable Firestore Database for your project.

Set up Firestore security rules to allow authenticated users to read and write data. The Canvas environment handles user authentication, but you can set up your own rules if you're deploying outside of it.

Note: This app is designed to work with the Canvas environment's authentication and configuration. To use it on your own server, you will need to replace the environment-specific variables (__app_id, __firebase_config, __initial_auth_token) with your own Firebase credentials and authentication logic.

Clone the Repository:

git clone [https://github.com/your-username/Simple-honey-pot.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

Deploy:

The index.html file is a complete, self-contained application. You can deploy it to any static web hosting service (e.g., Firebase Hosting, GitHub Pages, Netlify, Vercel).

Simply upload the index.html file to your hosting provider. The Firebase SDKs are loaded from a CDN, so no npm install is required.
