<!DOCTYPE html>
<html>
<head>
    <title>Login Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-image: url('binary.jpeg'); /* Set the path to your custom wallpaper image */
            background-size: cover;
            background-repeat: no-repeat;
            background-attachment: fixed;
        }
        .container {
            width: 300px;
            margin: 0 auto;
            padding: 20px;
            background-color: transparent; /* Set the background color to transparent for the container */
            color: white; /* Text color for the container */
        }
        input[type="text"], input[type="password"] {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
        }
        input[type="submit"] {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
        }
        .congratulations {
            background-color: transparent; /* Set the background color to transparent for the text */
        }
        .flag-block {
            background-color: #333; /* Background color for the flag block */
            color: white; /* Text color for the flag block */
            padding: 10px;
        }
        .bold-text {
            font-weight: bold; /* Make the text bold */
        }
        .single-line {
            white-space: nowrap; /* Display the text on a single line */
            text-align: center; /* Center-align the text */
        }
        .header {
            font-size: 24px; /* Adjust the font size as needed */
        }
    </style>
</head>
<body>
    <div class="container" id="login-container">
        <h1 class="header">ACM Cyber Security</h1> <!-- Add the header here -->
        <h2 style="color: white;">Login</h2>
        <form id="loginForm" action="#" onsubmit="return validateForm()">
            <input type="text" name="cred1" id="cred1" placeholder="Username" required autocomplete="off"><br>
            <input type="password" name="cred2" id="cred2" placeholder="Password" required autocomplete="off"><br>
            <input type="submit" value="Login">
        </form>
    </div>

    <div class="container" id="welcome-container" style="display: none;">
        <h2 style="color: white;" class="single-line">Congratulations, you have successfully completed this challenge</h2>
        <div class="flag-block">
            <p>Here's your flag for this challenge: <strong class="bold-text">"ACMCYS{H@ck3R_M@N}"</strong></p>
        </div>
    </div>

    <script>
        function validateForm() {
            var cred1 = document.getElementById("cred1").value;
            var cred2 = document.getElementById("cred2").value;

            if (cred1 === "studyhard" && cred2 === "Noob") {
                document.getElementById("login-container").style.display = "none";
                document.getElementById("welcome-container").style.display = "block";
                return false; // Prevent form submission
            } 
	    else if (cred1 === "uzair" && cred2 === "cybersecurity") {
			alert("Congratulations you've been pranked, try to find the correct credentials. You can also try other directories :)");
               		return false; // Prevent form submission
	    }
	    else {
                alert("Invalid username or password. Please try again.");
                return false; // Prevent form submission
            }
        }
    </script>
</body>
</html>
