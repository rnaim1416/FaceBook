<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Register</title>
    <style>
        body { font-family: Arial, sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; background-color: #f0f2f5; }
        .register-container { background-color: white; padding: 20px; border-radius: 8px; box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); }
        h1 { color: #1877f2; text-align: center; }
        form { display: flex; flex-direction: column; }
        input { margin: 10px 0; padding: 10px; border: 1px solid #dddfe2; border-radius: 6px; }
        button { background-color: #42b72a; color: white; border: none; padding: 10px; border-radius: 6px; cursor: pointer; }
        button:hover { background-color: #36a420; }
        .flash { color: red; margin-bottom: 10px; }
    </style>
</head>
<body>
    <div class="register-container">
        <h1>Register</h1>
        {% with messages = get_flashed_messages() %}
            {% if messages %}
                {% for message in messages %}
                    <p class="flash">{{ message }}</p>
                {% endfor %}
            {% endif %}
        {% endwith %}
        <form method="post">
            <input type="text" name="username" placeholder="Username" required>
            <input type="password" name="password" placeholder="Password" required>
            <button type="submit">Register</button>
        </form>
        <p>Already have an account? <a href="{{ url_for('login') }}">Login</a></p>
    </div>
</body>
</html>
