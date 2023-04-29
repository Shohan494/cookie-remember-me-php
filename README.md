# cookie-remember-me-php

To implement a "Remember Me" feature using cookies, you can set a cookie with a long expiration time that stores a unique identifier for the user, and then check for that cookie on subsequent requests to automatically log the user in if the cookie is present.

Here's an example code for setting a cookie to remember a user:

```

<?php
// Set the cookie to expire in 30 days
$expire = time() + 60 * 60 * 24 * 30;

// Generate a unique identifier for the user
$user_id = 123;

// Set the cookie with the user ID and expiration time
setcookie('remember_me', $user_id, $expire);

// Redirect the user to the home page
header('Location: /home.php');
?>
```
And here's an example code for checking for the cookie on subsequent requests:

```

<?php
// Check if the remember me cookie is set
if (isset($_COOKIE['remember_me'])) {
  // Get the user ID from the cookie
  $user_id = $_COOKIE['remember_me'];

  // TODO: Authenticate the user based on the user ID
}
?>
```

Note that storing user credentials or sensitive information in cookies is generally not recommended for security reasons. Instead, you should consider using a session-based authentication system that stores the user credentials on the server side.
