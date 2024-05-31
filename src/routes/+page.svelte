<script>
  import Albums from './albums.svelte';
  import Slide from './slide.svelte';
  import About from './about.svelte';
  import Hade from './hade.svelte';
  import Footer from './footer.svelte';
  import Photos from './photos.svelte';

  function showAlert(){
    alert('Invitation not allowed');
  }
</script>

<Hade/>
<section>
    <div class="firstsection">
        <div class="video-container">
            <video autoplay width="100%" muted loop class="desktop">
              <source src="yo.mp4" type="video/mp4">
            </video>
            <video autoplay width="100%" muted loop class="phone">
              <source src="yophone.mp4" type="video/mp4">
            </video>
            <div class="gradient-overlay"></div>
          </div>
          <div class="sec">
            <h1>our masterpieces</h1>
            <a href="/gallery"><button>view gallery</button></a>
        </div>
    </div> 
</section>
<Photos/>
<section>
  <div class="container">
     <h1>Livestream</h1>
     <div class="box">
        <div>
           <h2>experience the magic of your loed ones' special day in real-time with our exclusive live stream feature</h2>
        </div>
        <div>
           <h3>enter invitation code</h3>
        </div>
        <div>
           <input type="password" placeholder="Enter invitation code">
        </div>
        <div>
           <button on:click={showAlert}>watch live now</button>
        </div>
     </div>
  </div>
</section>
<About/>
<Slide/>

<Albums/>
  <div class="ready">
    <h1>ready for your big moment?</h1>
  </div>
  <div class="contact" id="contact">
    <div class="contact-box">
      <div class="contact-box-1">
        <div>
      <h1>Contact Us</h1>
      <p>crownweddingfilms@gmail.com</p>
      <p>+251 939 261 972</p>
      <a href="https://www.instagram.com/crownweddingfilms/" target="_blank"><img src="images/ilogo.svg" alt="logo" width="70px" style="opacity: 0.8;"></a>
      <p>bole atlas PLATINum building</p>
    </div>
    </div>
    <div class="map">
      <!-- svelte-ignore a11y-missing-attribute -->
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1122.4293261734808!2d38.7798783!3d9.000736100000008!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x164b853ac5bead97%3A0x249ee211eb1c5b72!2sCrown%20Wedding%20Films!5e1!3m2!1sen!2set!4v1716912211671!5m2!1sen!2set" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe></div>
  </div>
</div>
<Footer/>
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
      margin-top: 180px;
    }
    .container h1{
      font-size: 48px;
      margin-top: 150px;
      text-transform: capitalize;
    }
    .box{
      margin-bottom: 50px;
      margin: 50px;
      text-transform: capitalize;
    }
    .box h2{
      color: rgb(208, 208, 208);
      font-weight: 400;
      font-size: 19px;
      width: 900px;
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
    .box h3{
      color:rgb(172, 172, 172);
      margin: 50px;
      animation: scaleInOut 2s infinite;
    }
    .box input{
      justify-content: center;
      text-align: center;
      align-items: center;
      border: 1px solid rgb(137, 137, 137);
      width: 50%;
      outline: none;
      font-family: "Cinzel", serif;
      height: 40px;
      background-color: transparent;
      color: rgb(172, 172, 172);
      font-size: 15px;
      border-radius: 50px;
    }
    .box button{
      justify-content: center;
      text-align: center;
      align-items: center;
      border: 1px solid rgb(137, 137, 137);
      width: 30%;
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
   .phone{
      display: none;
    }
    .firstsection{
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

.ready h1 {
  font-size: 63px;
  text-transform: capitalize;
  text-shadow: 0 0 150px white;
  transition: transform 3s; /* Ensure smooth transition */
}

/* Target the h1 when hovering over the .ready container */
.ready:hover h1 {
  animation: hovreday 3s infinite;
  transform: scale(1.07); /* Scale up to 105% */
}

    .sec{
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
  .sec h1{
	font-size: 50px;
  }
  .sec button{
	border: 1px solid rgb(0, 0, 0);
	border-radius: 50px;
	background-color: transparent;
	color: rgb(0, 0, 0);
	font-family: "Cinzel", serif;
	padding: 8px 16px 8px 16px;
	text-transform: capitalize;
	height: 45px;
	transition: .5s;
	cursor: pointer;
	font-size: 17px;
	width: 160px;
  }
  .sec button:hover{
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
    .contact{
      display: flex;
      padding-left: 80px;
      color: black;
      background-color: rgb(239, 239, 239);
      padding-right: 80px;
      height: 80vh;
      border-bottom-left-radius: 380px;
      flex-direction: column;
    }   
    .contact-box{
      margin-top: 100px;
      display: flex;
      border: 2px solid rgb(107, 107, 107);
      padding: 30px 20px;
      border-bottom-left-radius: 280px;
      justify-content: space-between;
      align-items: center;
    }
    .contact-box-1{
      justify-content: center;
      text-align: center;
      align-items: center;
      display: flex;
      width: 100%;
    }
    .contact-box-1 img:hover{
      width: 80px;
      transition: .3s;
      cursor: pointer;
    }
    .contact .map{
      width: 100%;
      border: 1px solid rgb(107, 107, 107);
    }
    .contact .map:hover{
      transition: .4s;
      scale: 1.1;
    }
    iframe{
      border-radius: 10px;
      width: 100%;
      height: 450px;
    }
    .video-container {
	position: relative;
	width: 100%;
  }
  .video-container video {
	width: 100%;
  }
  

  
    
    
@media (max-width: 640px){

.contact{
  padding-left: 40px;
  padding-right: 40px;
} .contact{
      margin-bottom: 250px;
    } 
.contact-box{
  display: grid;
  justify-content: center;
}
.contact-box-1 h1{
      font-size: 60px;
    }
}
@media (max-width: 400px){
  .desktop{
    display: none;
  }
 
    .contact-box-1 h1{
      font-size: 40px;
    }
  .phone{
    display: block;
  }
  .firstsection{
      top: 70px;
  }
  
  }
</style>