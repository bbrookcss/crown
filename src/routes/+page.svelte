<script>
  import Albums from './albums.svelte';
  import Slide from './slide.svelte';
  import About from './about.svelte';
  import Hade from './hade.svelte';
  import Footer from './footer.svelte';
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
            <h1>capture the moments</h1>
          </div>
          <div class="sec">
            <h1>our masterpieces</h1>
            <a href="/gallery"><button>view gallery</button></a>
        </div>
    </div> 
</section>

  <div class="firstbox">
  <div class="box">
    <div class="fir">
      <img src="15imges.jpg" width="53%" height="500px" alt="imges">
      <img class="abc" src="15imges.jpg" width="33%" height="500px" alt="imges">
    </div>
    <div class="fir">
      <img class="abc" src="2imges.jpg" width="43%" height="394px"  alt="imges">
      <img src="15imges.jpg" width="43%" height="394px" alt="imges">
    </div>
  </div>
</div>
<section>
    <div class="scroll" id="live">
      <div class="text">
        <h1>we capture your memories</h1>
      <h2>that willlast forever</h2>
      </div>
      <div class="scrollbet">
          <div class="imgs">
            <img class="a" src="imges.webp" alt="">
            <img class="b" src="imges2.webp" alt="">
            <img class="c" src="imges4.webp" alt="">
          </div>
          <div class="imggs" id="t">
            <img class="a" src="imges6.webp" alt="">
            <img class="b" src="imges5.webp" alt="">
            <img class="c" src="imges3.webp" alt="">
          </div>
      </div>
    </div>
</section>
<Slide/>
<About/>
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
      <p>+254712345678</p>
      <p>+254712345678</p>
      <p>New building</p>
    </div>
    </div>
    <div class="map">
      <iframe src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d4544.804037669241!2d38.778817249511256!3d9.000229774552087!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sen!2set!4v1712917197465!5m2!1sen!2set"style="border:0;" allowfullscreen="" loading="lazy" title="Google Maps" referrerpolicy="no-referrer-when-downgrade"></iframe></div>
  </div>
</div>
<Footer/>
<style>
    .phone{
      display: none;
    }
    .firstsection{
      top: 90px;
      position: relative;
    }
    .scroll{
      margin-top: 150px;
      margin-bottom: 50px;
      justify-content: center;
      align-items: center;
      overflow: auto;
      text-align: center;
      height: 80vh;
    }
    .scroll .text{
      position: sticky;
      top: 300px; 
      z-index: 2;
    }
    .text h1{
      font-size: 65px;
      text-transform: capitalize;
      font-family: sans-serif;
      margin-bottom: -10px;
      -webkit-text-stroke: 1px;
      -webkit-text-stroke-color: white;
      color: transparent;
      text-shadow: 0 0 150px white;
     
    }
    .text h2{
      text-shadow: 0 0 90px white;
      font-size: 55px;
        text-transform: capitalize;
        font-family: "Cinzel", serif;
      
    }
    .scrollbet{
      width: 100%;
      display: flex;
      justify-content: space-between;
    }
    .imgs {
      display: grid;
    }
    .imggs {
      display: grid;
      
    }
    .imgs img{
      width: 300px;
      height: 400px;
      position: relative;
      object-fit: cover;
    }
    .imggs img{
      position: relative;
      width: 300px;
      bottom: 260px;
      height: 400px;
      margin-bottom: 150px;
      object-fit: cover;
    }
    .imggs .a{
      transform: rotate(-20deg);
      right: 170px;
      width: 250px;
      border-radius: 30px;
      height: 300px;
    }
    .imggs .b{
      right: 70px;
      border-radius: 20px;
      bottom: 320px
    }
    .imggs .c{
      right: 170px;
      border-top-left-radius: 100px;
      border-bottom-left-radius: 100px;
      width: 400px;
      height: 500px;
    }
    .imgs .a{
      left: 110px;
    }
    .imgs .b{
      left: 400px;
    }
    .imgs .c{
      border-radius: 30px;
      left: 200px;
      transform: rotate(20deg);
    }
    .ready{
      width: 100%;
      text-align: center;
      justify-content: center;
      text-align: center;
      display: flex;
      align-items: center;
      height: 90vh;
    }
    .ready h1{
      font-size: 63px;
      text-transform: capitalize;
      text-shadow: 0 0 150px white;
    }
    .ready h1:hover{
      animation: hovreday 2s infinite;
      
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
      padding-right: 80px;
      height: 80vh;
      flex-direction: column;
    }   
    .contact-box{
      display: flex;
      border: 2px solid rgb(189, 189, 189);
      padding: 30px 20px;
      border-radius: 10px;
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
    
    .contact .map{
      width: 100%;
    }
    .contact .map:hover{
      scale: 1.1;
    }
    iframe{
      border-radius: 10px;
      width: 100%;
      height: 450px;
    }
    @media (max-width: 1224px){
     
    .imggs .a{
      right: 170px;
    }
    .imggs .b{
      right: 80px;
    }
    .imggs .c{
      right: 80px;
      width: 300px;
      height: 400px;
    }
    .imgs .c{
      left: 150px;
      transform: rotate(25deg);
    }
    .text h1{
      font-size: 60px;
    }
    }
    @media (max-width: 1024px){
      .imggs .a{
        transform: rotate(-30deg);
      right: 140px;
      width: 200px;
      height: 250px
      
    }
    .imggs .b{
      right: 80px;
      width: 300px;
      height: 350px;
    }
    .imggs .c{
      right: 80px;
      width: 300px;
      height: 400px;
    }
    .imgs .a{
      width: 250px;
      height: 300px;
    }
    .imgs .b{
      left: 200px;
    }
    .text h1{
      font-size: 50px;
    }
    
    }
@media (max-width: 900px){
      .imggs img{
        margin-bottom: 300px;
    }
    .imgs img{
      margin-bottom: 400px;
    }
    } 
@media (max-width: 640px){
.scrollbet{
  display: none;
}
.scroll{
  margin-top: 0px;
}
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
  .text {
    font-size: 70px;
    width: 80px;
    display: flex;
    justify-content: center;
    align-items: start;
    text-align: center;
    padding-left: 70px;
    flex-direction: column;
  }
  .text h1{
    font-size: 60px;
  }
  }
</style>