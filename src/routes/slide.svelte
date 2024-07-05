<script>
 import { onMount } from 'svelte';
  import { onDestroy } from 'svelte';

  let isPreviewVisible = false;
  let previewVideoSrc = '';

  onMount(() => {
    const scrollContainers = document.querySelectorAll('.logos');

    scrollContainers.forEach((container, index) => {
      let scrollAmount = 0;
      const scrollStep = 1; // Adjust this value to control the scrolling speed
      const scrollInterval = 20; // Adjust this value to control the scrolling interval
      const direction = index % 2 === 0 ? 1 : -1; // Alternate direction for each container

      function startScrolling() {
        scrollAmount += scrollStep * direction;
        container.scrollLeft += scrollStep * direction;

        // Reset scroll position when reaching the end or beginning
        if (container.scrollLeft >= container.scrollWidth - container.clientWidth) {
          scrollAmount = 0;
          container.scrollLeft = 0;
        } else if (container.scrollLeft <= 0) {
          scrollAmount = container.scrollWidth - container.clientWidth;
          container.scrollLeft = scrollAmount;
        }
      }

      let scrollTimer = setInterval(startScrolling, scrollInterval);

      // Pause scrolling on hover
      container.addEventListener('mouseenter', () => clearInterval(scrollTimer));
      container.addEventListener('mouseleave', () => {
        scrollTimer = setInterval(startScrolling, scrollInterval);
      });
    });

    // Add event listeners to videos inside .img to pause on hover and play on mouse leave
    const imgVideos = document.querySelectorAll('.img video');
    imgVideos.forEach(video => {
      video.addEventListener('mouseenter', () => video.pause());
      video.addEventListener('mouseleave', () => video.play());
      video.addEventListener('click', () => {
        previewVideoSrc = video.querySelector('source').src;
        isPreviewVisible = true;
      });
    });
  });

  function closePreview() {
    isPreviewVisible = false;
  }
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
  </div>
</section>

<!-- svelte-ignore a11y-media-has-caption -->
{#if isPreviewVisible}
<div class="preview">
  <h2 on:click={closePreview}>x</h2>
  <div class="ovideo">
    <video controls autoplay >
      <source src={previewVideoSrc} type="video/mp4">
    </video>
  </div>
</div>
{/if}
<style>
  .preview {
    width: 100%;
    height: 100%;
    display: flex;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.7);
    top: 0;
    left: 0;
    z-index: 100;
  }
 .preview h2{
   color: white;
   font-weight: 100;
   display: flex;
   cursor: pointer;
   top: 70px;
   left: 85%;
   position: relative;
   font-size: 40px;
   font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
 }
  .preview .ovideo {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .ovideo video {
    width: 70%;
  }

  .tops {
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
  }

  .img {
    width: 623px;
    height: 376px;
    justify-content: center;
    transition: 0.5s;
    align-items: center;
    display: flex;
    gap: 20px;
  }

  .img:hover {
    gap: 30px;
    filter: brightness(0.7);
    transition: 0.3s;
    cursor: pointer;
    scale: 104.5%;
  }

  .img video {
    width: 100%;
    transition: 0.5s;
  }

  .img video:hover {
    border-radius: 10px;
    transition: 0.5s;
  }

  .logos-sli {
    gap: 20px;
    position: relative;
    display: flex;
  }


  @media (max-width: 900px) {
    .img {
      width: 523px;
      height: 306px;
    }
  }

  @media (max-width: 600px) {
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
