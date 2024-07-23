<script>
  import { onMount } from 'svelte';
  import { Lightbox, LightboxGallery, GalleryThumbnail, GalleryImage } from 'svelte-lightbox';
  import Footer from '../../footer.svelte';
  import Hade from '../../hade.svelte';

  // @ts-nocheck
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

    // Extract the userId from the URL path
    const urlPath = window.location.pathname;
    const pageUserId = urlPath.match(/\/wedding(\d+)/)?.[1];

    if (!pageUserId || pageUserId !== userId) {
      errorMessage = 'User ID mismatch or not found in URL.';
      window.location.href = './'; // Redirect to home page if userId doesn't match
      return;
    }

    try {
      const response = await fetch(`http://localhost:3000/users/${userId}`, {
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

<Hade/>
<section>
  <h2><span>Welcome back,</span> {username}!</h2>
  <h1>Data is not set</h1>
</section>
<Footer />

<style>
  section {
    color: black;
    position: absolute;
    margin-top: 150px;
  }
</style>
