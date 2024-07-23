<script>
    let username = '';
    let password = '';
    let registerUsername = '';
    let registerPassword = '';
    let message = '';
    let registerMessage = '';
    let success = false;
    let registerSuccess = false;
  
    const loginUser = async () => {
      const response = await fetch('http://localhost:3000/users/login', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ username, password }),
      });
  
      const data = await response.json();
  
      if (response.ok) {
        message = 'Login successful!';
        success = true;
        localStorage.setItem('token', data.token); // Store JWT token in localStorage
        localStorage.setItem('userId', data.id); // Store user ID in localStorage
        window.location.href = '/account'; // Redirect to /loginaccount page
      } else {
        message = data.message || 'Login failed!';
        success = false;
      }
    };
  
    const registerUser = async () => {
      const response = await fetch('http://localhost:3000/users/register', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ username: registerUsername, password: registerPassword }),
      });
  
      const data = await response.json();
  
      if (response.ok) {
        registerMessage = 'Registration successful!';
        registerSuccess = true;
      } else {
        registerMessage = data.message || 'Registration failed!';
        registerSuccess = false;
      }
    };
  </script>
  <section>
  <div>
    <h1>Login</h1>
    <form on:submit|preventDefault={loginUser}>
      <label for="login-username">Username:</label>
      <input type="text" id="login-username" bind:value={username} required />
  
      <label for="login-password">Password:</label>
      <input type="password" id="login-password" bind:value={password} required />
  
      <button type="submit">Login</button>
    </form>
    {#if message}
      <div class:message class:success={success} class:error={!success}>
        {message}
      </div>
    {/if}
  </div>
  
  <div class="black">
    <h1>Register</h1>
    <form on:submit|preventDefault={registerUser}>
      <label for="register-username">Username:</label>
      <input type="text" id="register-username" bind:value={registerUsername} required />
  
      <label for="register-password">Password:</label>
      <input type="password" id="register-password" bind:value={registerPassword} required />
  
      <button type="submit">Register</button>
    </form>
    {#if registerMessage}
      <div class:message class:success={registerSuccess} class:error={!registerSuccess}>
        {registerMessage}
      </div>
    {/if}
  </div>
  </section>
  <style>
    section {
      color: black;
    }
  </style>