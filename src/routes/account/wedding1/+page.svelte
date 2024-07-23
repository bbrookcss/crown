<script>
    import { onMount } from 'svelte';
  
    let userId;
    let username;
    let errorMessage;
  // @ts-nocheck
    
  import { Lightbox, LightboxGallery,  GalleryThumbnail, GalleryImage } from 'svelte-lightbox';
      import Footer from '../../footer.svelte';
      import Hade from '../../hade.svelte';
    function shmgelena() {
      const gallerElement = document.getElementById("galler");
      const galleElement = document.getElementById("galle");
      const galleryElement = document.getElementById("gallery");
    
      if (gallerElement) {
        gallerElement.style.display = "none";
      }
      if (galleElement) {
        galleElement.style.display = "flex";
      }
      if (galleryElement) {
        galleryElement.style.display = "none";
      }
    }
    function wedding() {
      const gallerElement = document.getElementById("galler");
      const galleElement = document.getElementById("galle");
      const galleryElement = document.getElementById("gallery");
    
      if (gallerElement) {
        gallerElement.style.display = "none";
      }
      if (galleElement) {
        galleElement.style.display = "none";
      }
      if (galleryElement) {
        galleryElement.style.display = "flex";
      }
    }
    function melse() {
      const gallerElement = document.getElementById("galler");
      const galleElement = document.getElementById("galle");
      const galleryElement = document.getElementById("gallery");
    
      if (gallerElement) {
        gallerElement.style.display = "flex";
      }
      if (galleElement) {
        galleElement.style.display = "none";
      }
      if (galleryElement) {
        galleryElement.style.display = "none";
      }
    } 
    const fetchUserDetails = async () => {
      userId = localStorage.getItem('userId');
      const token = localStorage.getItem('token');
  
      if (!userId || !token) {
        errorMessage = 'No user ID or token found. Please log in.';
        window.location.href = './'; // Redirect to home page if no user ID or token found
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
  <div class="gili">
    {#if errorMessage}
      <p class="error">{errorMessage}</p>
    {:else}
      {#if username}
        <div class="fixheader"></div>
        <section>
          <div class="container" id="gallery">
            <h2><span>Welcome back,</span> {username}!</h2>
            <div class="open">
              <button on:click={wedding} class="wedding"> <h1 class="mk">Video</h1></button>
              <button on:click={melse} class="melse"> <h1 >Photo</h1></button>
            </div>
            <div class="box">
              <LightboxGallery>
                <svelte:fragment slot="thumbnail">
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges2.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges4.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges6.webp" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/imges6.webp" alt="Simple lightbox">
                </GalleryThumbnail>	
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges2.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
              </div> 
            </svelte:fragment>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges2.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges4.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges6.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges6.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges2.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
            </LightboxGallery>
            </div>
          </div>
          <div class="container" id="galler">
            <h2>Welcome, {username}!</h2>
            <div class="open">
              <button on:click={wedding} class="wedding"> <h1 >Video</h1></button>
              <button on:click={melse} class="melse"> <h1 class="mk">Photo</h1></button>
            </div>
            <div class="box">
              <LightboxGallery>
                <svelte:fragment slot="thumbnail">
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges2.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges4.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges6.webp" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>	
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges6.webp" alt="Simple lightbox">
                </GalleryThumbnail>
              </div>
              <div class="imgs">
                <GalleryThumbnail>
                  <img src="/images/imges2.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/imges.webp" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/2imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
                <GalleryThumbnail>
                  <img src="/images/8imges.jpg" alt="Simple lightbox">
                </GalleryThumbnail>
              </div> 
            </svelte:fragment>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges2.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges4.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges6.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges6.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/imges2.webp" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/2imges.jpg" alt="Simple lightbox">
              </GalleryImage>
              <GalleryImage>
                <img src="/images/8imges.jpg" alt="Simple lightbox">
              </GalleryImage>
            </LightboxGallery>
            </div>
          </div>
          <div class="lode">
          <h1>lode more</h1></div>
        </section>
      {:else}
        <p>Loading user details...</p>
      {/if}
    {/if}
    </div>
    <br><br><br><br><br><br>
    <Footer/>
        <style>
          .gili{
            display: flex;
            position: relative;
            text-align: center;
            justify-content: center;
            align-items: center;
            top: 60px;
          }
          .gili p{
            margin-top: 60px;
            font-size: 20px;
          }
         .error {
      color: red;
    }
        .lode{
          display: flex;
          justify-content: center;
          align-items: center;
        }
        .lode h1{
          border-bottom: 2px solid rgb(35, 35, 35);
          font-weight: 300;
          padding: 10px;
          color: black;
                transition: .5s;
        }
            .lode h1:hover{
                cursor: pointer;
                border-top: 4px solid rgb(49, 49, 49);
                border-right: 2px solid rgb(60, 60, 60);
                border-bottom: none;
            }
        #galler{
          display: none;
        }
        #galle{
          display: none;
        }
        .fixheader{
          margin-top: -40px;
        }
        
      .open{
        display: flex;
        gap: 50px;
        margin-bottom: 30px;
      }
      .open button{
        background-color: transparent;
        border: none;
      }
      button h1{
        cursor: pointer;
        font-weight: 300;
        text-transform: capitalize;
        color: rgb(0, 0, 0);
        font-size: 25px;
        font-family: "Cinzel", serif;
      }
      .mk{
        color: rgb(117, 117, 117);
        border-bottom: 1px solid rgb(117, 117, 117);
      }
      .container span{
        font-weight: 100;
        font-size: 23px;
      }
      .container {
        color: black;
            padding-left: 60px;
            padding-right: 60px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            margin: 40px 20px 0 20px;
        }
        .container .box {
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;
        }
        .container .box .imgs {
            display: flex;
            flex-direction: column;
            width: 23.5%;
        }
        .container .box .imgs img {
            width: 100%;
        cursor: pointer;
            margin-bottom: 15px;
            border-radius: 5px;
            height: auto;
        }
        @media (max-width: 640px) {
        
        .container {
            padding-left: 10px;
            padding-right: 10px;
        }
        .container .box {
            flex-direction: column;
            margin-top: 10px;
        }
        .container .box .imgs {
            width: 100%;
        }.open{
		gap: 10px;
		margin-bottom: 10px;
	}button h1{
		font-size: 25px;
    color: black;
		font-family: "Cinzel", serif;
	}
    }
        </style>