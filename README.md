# Autentication
firebase Authentication service

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Firebase Authentication Example</title>
  <!-- Add Firebase SDK -->
  <script defer src="https://www.gstatic.com/firebasejs/9.6.4/firebase-app.js"></script>
  <script defer src="https://www.gstatic.com/firebasejs/9.6.4/firebase-auth.js"></script>

  <!-- Your Firebase Config -->
  <script defer>
    var firebaseConfig = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_AUTH_DOMAIN",
      projectId: "YOUR_PROJECT_ID",
      storageBucket: "YOUR_STORAGE_BUCKET",
      messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
      appId: "YOUR_APP_ID"
    };

    // Initialize Firebase
    firebase.initializeApp(firebaseConfig);
  </script>
</head>
<body>
  <h1>Firebase Authentication Example</h1>
  <div id="auth-container">
    <button onclick="signUp()">Sign Up</button>
    <button onclick="signIn()">Sign In</button>
    <button onclick="signOut()">Sign Out</button>
  </div>

  <script defer>
    // Sign up with email and password
    function signUp() {
      var email = prompt("Enter your email:");
      var password = prompt("Enter your password:");

      firebase.auth().createUserWithEmailAndPassword(email, password)
        .then((userCredential) => {
          alert("User signed up successfully");
        })
        .catch((error) => {
          alert("Error: " + error.message);
        });
    }

    // Sign in with email and password
    function signIn() {
      var email = prompt("Enter your email:");
      var password = prompt("Enter your password:");

      firebase.auth().signInWithEmailAndPassword(email, password)
        .then((userCredential) => {
          alert("User signed in successfully");
        })
        .catch((error) => {
          alert("Error: " + error.message);
        });
    }

    // Sign out
    function signOut() {
      firebase.auth().signOut().then(() => {
        alert("Sign-out successful.");
      }).catch((error) => {
        alert("Error: " + error.message);
      });
    }
  </script>
</body>
</html>
