<script>
    import { onMount } from 'svelte';
    let username = '';
    let password = '';
    let message = '';
    let success = false;
  
    const registerUser = async () => {
      const response = await fetch('https://backend.crownweddingfilms.com/users/register', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({ username, password }),
      });
  
      const data = await response.json();
  
      if (response.ok) {
        message = 'Registration successful!';
        success = true;
      } else {
        message = data.message || 'Registration failed!';
        success = false;
      }
    };
  </script>
  
  <style>
    .black{
        color: black;
    }
        div{
        color: red;
    }
  </style>
  
  <div class="black">
    <h1>Register</h1>
    <form on:submit|preventDefault={registerUser}>
      <label for="username">Username:</label>
      <input type="text" id="username" bind:value={username} required />
  
      <label for="password">Password:</label>
      <input type="password" id="password" bind:value={password} required />
  
      <button type="submit">Register</button>
    </form>
    {#if message}
      <div class:message class:success={success} class:error={!success}>
        {message}
      </div>
    {/if}
  </div>
  