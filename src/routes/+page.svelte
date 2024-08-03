<script>
  import Albums from "./albums.svelte";
  import Slide from "./slide.svelte";
  import About from "./about.svelte";
  import Hade from "./hade.svelte";
  import Footer from "./footer.svelte";
  import Photos from "./photos.svelte";
  import LazyLoadWrapper from './LazyLoadWrapper.svelte';
  let isMuted = true;
    let videoElement;

    function toggleMute() {
        isMuted = !isMuted;
        videoElement.muted = isMuted;
    }
  function showAlert() {
    alert("Invitation not allowed");
  }
</script>

<Hade />
<section>
  <div class="firstsection">
    <div class="video-container">
      <video autoplay width="100%" muted bind:this={videoElement} loop class="desktop">
        <source src="yo.mp4" type="video/mp4" />
    </video>
    
    {#if isMuted}
        <svg on:click={toggleMute} version="1.2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000">
            <style>.a{fill:none;stroke:#020202;stroke-linecap:round;stroke-miterlimit:10;stroke-width:22}</style>
            <path class="a" d="m607.1 449.3l133-94.4"/>
            <path class="a" d="m736.6 644.6l-130.5-92.6"/>
            <path class="a" d="m608.5 496.9l158.5-0.2"/>
            <path fill-rule="evenodd" class="a" d="m231 358.6h122v282.8h-122c-8.2 0-16.4-1.6-24-4.8-7.7-3.1-14.6-7.8-20.4-13.6-5.8-5.8-10.5-12.8-13.6-20.4-3.2-7.6-4.8-15.8-4.8-24v-157.2c0-8.2 1.6-16.4 4.8-24 3.1-7.7 7.8-14.6 13.6-20.4 5.8-5.8 12.7-10.5 20.4-13.6 7.6-3.2 15.8-4.8 24-4.8z"/>
            <path class="a" d="m579 408.6v409.6c0 3.1-4.6 5-7.8 3l-145.9-121.7"/>
            <path class="a" d="m394.5 672l-42.1-35.5v-273l218.8-184.7c3.2-2 7.8-0.2 7.8 3v157.8"/>
        </svg>
    {:else}
        <svg on:click={toggleMute} viewBox="0 0 1000 1000" data-name="Layer 2" id="Layer_2" xmlns="http://www.w3.org/2000/svg">
            <defs><style>.cls-1{fill:none;stroke:#020202;stroke-linecap:round;stroke-miterlimit:10;stroke-width:22px;}</style></defs>
            <line class="cls-1" x1="644.38" x2="831.85" y1="393.76" y2="606.24"/>
            <line class="cls-1" x1="831.85" x2="644.38" y1="393.76" y2="606.24"/>
            <path class="cls-1" d="M231,358.6H353a0,0,0,0,1,0,0V641.4a0,0,0,0,1,0,0H231a62.81,62.81,0,0,1-62.81-62.81V421.4A62.81,62.81,0,0,1,231,358.6Z"/>
            <path class="cls-1" d="M579,408.64V818.16c0,3.19-4.65,5-7.83,3L425.27,699.55"/>
            <path class="cls-1" d="M394.53,672l-42.08-35.52v-273L571.19,178.83c3.18-2,7.83-.18,7.83,3V339.6"/>
        </svg>
    {/if}<video autoplay width="100%" muted loop class="phone">
        <source src="yophone.mp4" type="video/mp4" />
      </video>
      <div class="gradient-overlay"></div>
    </div>
    <div class="sec">
      <h1>our masterpieces!</h1>
      <a href="/gallery"><button>view gallery</button></a>
    </div>
  </div>
</section>
<LazyLoadWrapper animation="slide-left" rootMargin="0px 0px -30% 0px">
  <Photos />
</LazyLoadWrapper>

<LazyLoadWrapper animation="slide-top">
<section>
  <div class="container">
    <h1>Livestream</h1>
    <div class="box">
      <div>
        <h2>Special day in real-time with our exclusive live stream feature</h2>
      </div>
      <div>
        <h3>enter invitation code</h3>
      </div>
      <div>
        <input type="password" placeholder="Enter invitation code" />
      </div>
      <div>
        <button on:click={showAlert}>watch live now</button>
      </div>
    </div>
  </div>
</section>

</LazyLoadWrapper>

<LazyLoadWrapper animation = "slide-scale-down" rootMargin="0px 0px -60% 0px">
<About />
</LazyLoadWrapper>

<LazyLoadWrapper  animation = "slide-albums" rootMargin="0px 0px -40% 0px">

<Albums /></LazyLoadWrapper>
<LazyLoadWrapper>
<div class="ready">
  <h1>Join the family !</h1>
  <img src="images/tr.jpg" alt="" />
</div>
<div class="contact" id="contact">
  <div class="contact-box">
    <div class="contact-box-1">
      <div>
        <h1>Contact Us</h1>
        <p>crownweddingfilms@gmail.com</p>
        <p>+251 939 261 972</p>
        <a href="https://www.instagram.com/crownweddingfilms/" target="_blank"
          ><img
            src="images/ilogo.svg"
            alt="logo"
            width="70px"
            style="opacity: 0.8;"
          /></a
        >
        <p>bole atlas PLATINum building</p>
      </div>
    </div>
    <div class="map">
      <!-- svelte-ignore a11y-missing-attribute -->
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1122.4293261734808!2d38.7798783!3d9.000736100000008!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x164b853ac5bead97%3A0x249ee211eb1c5b72!2sCrown%20Wedding%20Films!5e1!3m2!1sen!2set!4v1716912211671!5m2!1sen!2set"
        style="border:0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
    </div>
  </div>
</div></LazyLoadWrapper>
<br><br>
<br><Footer /><br>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    justify-content: center;
    justify-content: center;
    align-items: center;
    background-color: rgb(19, 19, 19);
    text-align: center;
    margin-top: 10px;
  }
  .container h1 {
    font-size: 48px;
    margin-top: 150px;
    text-transform: capitalize;
  }
  .box {
    margin-bottom: 50px;
    margin: 50px;
    text-transform: capitalize;
  }
  .box h2 {
    color: rgb(208, 208, 208);
    font-weight: 400;
    font-size: 19px;
    width: 100%;
  }
  @keyframes scaleInOut {
    0% {
      transform: scale(1);
    }
    50% {
      transform: scale(1.15);
    }
    100% {
      transform: scale(1);
    }
  }
  .box h3 {
    color: rgb(172, 172, 172);
    margin: 50px;
    animation: scaleInOut 2s infinite;
  }
  .box input {
    justify-content: center;
    text-align: center;
    align-items: center;
    border: 1px solid rgb(137, 137, 137);
    width: 70%;
    outline: none;
    font-family: "Cinzel", serif;
    height: 40px;
    background-color: transparent;
    color: rgb(172, 172, 172);
    font-size: 15px;
    border-radius: 50px;
  }
  .box button {
    justify-content: center;
    text-align: center;
    align-items: center;
    border: 1px solid rgb(137, 137, 137);
    width: 40%;
    outline: none;
    font-family: "Cinzel", serif;
    height: 40px;
    cursor: pointer;
    background-color: transparent;
    color: rgb(209, 209, 209);
    font-size: 18px;
    border-radius: 50px;
    margin-bottom: 100px;
    margin-top: 50px;
  }
  .phone {
    display: none;
  }
  .firstsection {
    top: 80px;
    position: relative;
  }
  .ready {
    width: 100%;
    z-index: 99;
    position: relative;
    text-align: center;
    justify-content: center;
    display: flex;
    background-color: black;
    align-items: center;
    height: 100vh;
  }
  .ready img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0.4;
  }
  .ready h1 {
    font-size: 73px;
    position: absolute;
    text-transform: capitalize;
    text-shadow: 0 0 150px white;
    transition: transform 3s; /* Ensure smooth transition */
  }

  /* Target the h1 when hovering over the .ready container */
  .ready:hover h1 {
    animation: hovreday 3s infinite;
    transform: scale(1.07); /* Scale up to 105% */
  }

  .sec {
    padding-left: 60px;
    padding-right: 60px;
    background-color: rgb(255, 255, 255);
    height: 250px;
    justify-content: space-between;
    display: flex;
    text-align: center;
    margin-top: -10px;
    align-items: center;
    color: black;
    text-transform: capitalize;
    font-family: "Cinzel", serif;
  }
  .sec h1 {
    font-size: 50px;
  }
  .sec button {
    border: 1px solid rgb(0, 0, 0);
    border-radius: 50px;
    background-color: transparent;
    color: rgb(0, 0, 0);
    font-family: "Cinzel", serif;
    padding: 8px 16px 8px 16px;
    text-transform: capitalize;
    height: 45px;
    transition: 0.5s;
    cursor: pointer;
    font-size: 17px;
    width: 160px;
  }
  .sec button:hover {
    scale: 110%;
    border: 1.5px solid rgb(0, 0, 0);
  }
  @keyframes hovreday {
    0% {
      transform: scale(1);
    }
    50% {
      transform: scale(105%);
    }
    100% {
      transform: scale(1);
    }
  }
  .contact {
    display: flex;
    padding-left: 80px;
    color: black;
    background: linear-gradient(to bottom, white 0%, white 5%, rgb(238, 238, 238) 95%, rgb(238, 238, 238) 100%);
    padding-right: 80px;
    height: 80vh;
    border-bottom-left-radius: 380px;
    flex-direction: column;
  }
  .contact-box {
    margin-top: 100px;
    width: 100%;
    display: flex;
    border: 2px solid rgb(107, 107, 107);
    padding: 30px 20px;
    border-bottom-left-radius: 280px;
    justify-content: space-between;
    align-items: center;
  }
  .contact-box-1 {
    justify-content: center;
    text-align: center;
    align-items: center;
    display: flex;
    width: 100%;
  }
  .contact-box-1 img:hover {
    width: 80px;
    transition: 0.3s;
    cursor: pointer;
  }
  .contact .map {
    width: 100%;
    border: 1px solid rgb(107, 107, 107);
  }
  .contact .map:hover {
    transition: 0.4s;
    scale: 1.1;
  }
  iframe {
    border-radius: 10px;
    width: 100%;
    height: 450px;
  }
  .video-container {
    position: relative;
    width: 100%;
  }
  .video-container svg {
    position: absolute;
    top: 84%;
    cursor: pointer;
    left: 93%;
    width: 70px;
    z-index: 1;
  }
  .video-container video {
    width: 100%;
  }
  @media (max-width: 900px) {
    .ready h1 {
      font-size: 43px;
    }
    .video-container svg {
    top: 74%;
    left: 90%;
    width: 60px;
  }
  }
  @media (max-width: 640px) {
    .video-container svg {
    top: 74%;
    left: 88%;
    width: 50px;
  }
    .contact .map {
      width: 100%;
      outline: none;
      border: 1px solid rgb(107, 107, 107);
  }
    .ready h1 {
      font-size: 38px;
    }
    .box input {
      width: 100%;
    }
    .box button {
      width: 70%;
    }
    .sec {
      place-content: center;
      place-items: center;
      display: grid;
      text-align: center;
      margin-top: -10px;
      padding-left: 0px;
      padding-right: 0px;
    }
    .box h3 {
      color: rgb(172, 172, 172);
      margin: 50px;
      font-size: 15px;
      animation: scaleInOut 2s infinite;
    }
    .sec h1 {
      font-size: 35px;
    }
    .contact {
      border-bottom-left-radius: 0;
      padding-left: 10px;
      padding-right: 10px;
      height: auto;
    }
    .contact-box {
      border: 1px solid rgb(168, 168, 168);
      margin-top: 70px;
      display: grid;
      padding: 1px 1px;
      justify-content: center;
      border-bottom-left-radius: 0;
    }
    .contact-box-1 h1 {
      font-size: 60px;
    }
  }
  @media (max-width: 400px) {
    .video-container svg {
    display: none;
  }
    .desktop {
      display: none;
    }
    .contact-box-1 h1 {
      font-size: 40px;
    }
    .phone {
      display: block;
    }
    .firstsection {
      top: 70px;
    }
  }
</style>
