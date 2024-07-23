<script>
    import { onMount } from 'svelte';
    let username = '';
    let password = '';
    let message = '';
    let success = false;
  
    const registerUser = async () => {
      const response = await fetch('http://localhost:3000/users/register', {
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
        display: grid;
        text-align: center;
        place-content: center;
        place-items: center;

    }
    form{
      width: 400px;
      border: 1px solid rgba(0, 0, 0, 0.322);
        display: grid;
        gap: 10px;
        padding: 20px 20px;
        text-align: center;
        place-content: center;
        place-items: center;
    }
    button{
      width: 150px;
      height: 30px;
      border: none;
      background-color: black;
      color: white;
      border-radius: 5px;
    }
    input{
      width: 200px;
      height: 30px;
      border: 1px solid black;
      background-color: transparent;
      color: black;
      border-radius: 5px;
    }
        div{
        color: red;
    }
  </style>
  
  <div class="black">
    <h1>Crown Admin to register a new user</h1>
    <form on:submit|preventDefault={registerUser}>
      <label for="username">Username</label>
      <input type="text" id="username" bind:value={username} required />
  
      <label for="password">Wedding Day</label>
      <input type="password" id="password" bind:value={password} required />
  
      <button type="submit">Submit</button>
    </form>
    {#if message}
      <div class:message class:success={success} class:error={!success}>
        {message}
      </div>
    {/if}
  </div>
  