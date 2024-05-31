<script>
  import { onMount } from 'svelte';

  onMount(() => {
    const videos = document.querySelectorAll('video');
    const imgs = document.querySelectorAll('.img');

    function pauseOtherVideos(except) {
      videos.forEach(video => {
        if (video !== except) {
          video.pause();
        }
      });
    }

    function playVideo(video) {
      video.play();
    }

    videos.forEach(video => {
      video.addEventListener('mouseenter', () => {
        pauseOtherVideos(video);
        playVideo(video);
      });

      video.addEventListener('mouseleave', () => {
        videos.forEach(video => {
          video.play();
        });
      });
    });

    imgs.forEach(img => {
      img.addEventListener('mouseenter', () => {
        pauseOtherVideos(null);
      });

      img.addEventListener('mouseleave', () => {
        videos.forEach(video => {
          video.play();
        });
      });
    });
  });
</script>
<section class="tops">
  <div class="logos" id="live">
    <div class="logos-slide">
      <div class="img">
        <video autoplay muted loop>
          <source src="1.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="2.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="3.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="4.mp4" type="video/mp4">
        </video>
      </div>
    </div>
    <div class="logos-slide">
      <div class="img">
        <video autoplay muted loop>
          <source src="1.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="2.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="3.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="4.mp4" type="video/mp4">
        </video>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="logos" id="live">
    <div class="logos-sli">
      <div class="img">
        <video autoplay muted loop>
          <source src="5.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="6.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="7.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="8.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="9.mp4" type="video/mp4">
        </video>
      </div>
    </div>
    <div class="logos-sli">
      <div class="img">
        <video autoplay muted loop>
          <source src="5.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="6.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="7.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="8.mp4" type="video/mp4">
        </video>
      </div>
      <div class="img">
        <video autoplay muted loop>
          <source src="9.mp4" type="video/mp4">
        </video>
      </div>
    </div>
  </div>
</section>
<!-- svelte-ignore a11y-media-has-caption -->
<div class="preview">
  <div class="ovideo">
    <video controls autoplay muted loop>
      <source src="1.mp4" type="video/mp4">
    </video>
  </div>
</div>
<style>
 .preview{
  width: 100%;
  height: 100%;
  display: none;
  position: fixed;
  background-color: rgba(0, 0, 0, 0.7);
  top: 0;
  left: 0;
  justify-content: center;
  align-items: center;
  text-indent: center;
  z-index: 100;
 }
 .preview .ovideo{
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
 }
 .ovideo video{
  width: 70%;
 }
   @keyframes slide {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes sli {
    from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}

.tops{
  margin-top: 260px;
}
.logos {
  overflow: hidden;
  display: flex;
  margin-top: 50px;
  position: relative;
}
.logos-slide {
  gap: 20px;
  display: flex;
  margin-left: 20px;
  animation: 40s slide infinite linear;
}
.img{
    width: 623px;
    height: 376px;
    justify-content: center;
    transition: .5s;
    align-items: center;
    display: flex;
    gap: 20px;
    
}

.img:hover{
  gap: 30px;
  filter: brightness(0.7);
  transition: .3s;
  cursor: pointer;
  scale: 104.5%;
  
}
.img video{
  width: 100%;
  transition: .5s;
}
.img video:hover{
  border-radius: 10px;
  transition: .5s;
}
.logos-sli {
  gap: 20px;
  display: flex;
  margin-left: 10px;
  animation: 40s sli infinite linear;
}
.logos:before,
.logos:after {
  position: absolute;
  top: 0;
  width: 100px;
  height: 100%;
  content: "";
  z-index: 2;
}
.logos:before {
  left: 0;
  background: linear-gradient(to left, rgba(255, 255, 255, 0), white);
}

.logos:after {
  right: 0;
  background: linear-gradient(to right, rgba(255, 255, 255, 0), white);
}
.logos:hover .logos-sli {
  animation-play-state: paused;
}
.logos:hover .logos-slide {
  animation-play-state: paused;
}
    @media (max-width: 900px){
      .img{
        width: 523px;
        height: 306px;
      }
    }
@media (max-width: 600px){
  .logos:before {
  left: 0;
  background: linear-gradient(to left, rgba(255, 255, 255, 0), rgba(0, 0, 0, 0.1));
}

.logos:after {
  right: 0;
  background: linear-gradient(to right, rgba(255, 255, 255, 0), rgba(0, 0, 0, 0.1));
}
}
</style>