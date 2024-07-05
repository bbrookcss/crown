<script>
    import { onMount } from 'svelte';
  
    let userId;
    let username;
    let errorMessage;
  
    const fetchUserDetails = async () => {
      userId = localStorage.getItem('userId');
      const token = localStorage.getItem('token');
  
      if (!userId || !token) {
        errorMessage = 'No user ID or token found. Please log in.';
        window.location.href = './'; // Redirect to home page if no user ID or token found
        return;
      }
  
      try {
        const response = await fetch(`https://test.crownweddingfilms.com/users/${userId}`, {
          headers: {
            'Authorization': `Bearer ${token}`
          }
        });
  
        if (!response.ok) {
          throw new Error('Failed to fetch user details');
        }
  
        const user = await response.json();
        username = user.username;
      } catch (error) {
      errorMessage = error.message;
      window.location.href = './'; // Redirect to home page if there's an error
      }
    };
  
    onMount(fetchUserDetails);
  </script>
  
  <style>
    .error {
      color: red;
    }
  </style>
  
  <div>
    <h1>Login Account Page</h1>
    {#if errorMessage}
      <p class="error">{errorMessage}</p>
    {:else}
      {#if username}
        <p>Welcome, {username}!</p>
        <p>User ID: {userId}</p>
      {:else}
        <p>Loading user details...</p>
      {/if}
    {/if}
  </div>
  