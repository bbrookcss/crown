<script>
    let username = '';
    let password = '';
    let message = '';
    let success = false;
  
    const loginUser = async () => {
      const response = await fetch('https://backend.crownweddingfilms.com/users/login', {
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
    
  </script>
  
  <style>
    .message {
      margin-top: 10px;
      padding: 10px;
      border-radius: 5px;
    }
    .success {
      background-color: #d4edda;
      color: #155724;
    }
    .error {
      background-color: #f8d7da;
      color: #721c24;
    }
  </style>
  
  <div>
    <h1>Login</h1>
    <form on:submit|preventDefault={loginUser}>
      <label for="username">Username:</label>
      <input type="text" id="username" bind:value={username} required />
      <label for="password">Password:</label>
      <input type="password" id="password" bind:value={password} required />
      {#if message}
        <p class:message class:success={success} class:error={!success}>{message}</p>
    {/if}
      <button type="submit">Login</button>
    </form>
    
  </div>
  