<script>
	import { Lightbox, LightboxGallery,  GalleryThumbnail, GalleryImage } from 'svelte-lightbox';
	import Footer from '../footer.svelte';
	import Hade from '../hade.svelte';
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
</script>
<Hade/>
<div class="fixheader"></div>
	<section>
		<div class="container" id="gallery">
			<div class="open">
				<button on:click={wedding} class="wedding"> <h1 class="mk">wedding</h1></button>
				<button on:click={melse} class="melse"> <h1 >melse</h1></button>
				<button on:click={shmgelena} class="shmgelena"> <h1 >shmgelena</h1></button>
			</div>
			<div class="box">
				<LightboxGallery>
					<svelte:fragment slot="thumbnail">
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges4.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>	
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
				</div> 
			</svelte:fragment>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges4.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
			</LightboxGallery>
			</div>
		</div>
		<div class="container" id="galler">
			<div class="open">
				<button on:click={wedding} class="wedding"> <h1 >wedding</h1></button>
				<button on:click={melse} class="melse"> <h1 class="mk">melse</h1></button>
				<button on:click={shmgelena} class="shmgelena"> <h1 >shmgelena</h1></button>
			</div>
			<div class="box">
				<LightboxGallery>
					<svelte:fragment slot="thumbnail">
				<div class="imgs">
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges4.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>	
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
				</div> 
			</svelte:fragment>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges4.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
			</LightboxGallery>
			</div>
		</div>
		<div class="container" id="galle">
			<div class="open">
				<button on:click={wedding} class="wedding"> <h1 >wedding</h1></button>
				<button on:click={melse} class="melse"> <h1>melse</h1></button>
				<button on:click={shmgelena} class="shmgelena"> <h1 class="mk">shmgelena</h1></button>
			</div>
			<div class="box">
				<LightboxGallery>
					<svelte:fragment slot="thumbnail">
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges4.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges6.webp" alt="Simple lightbox">
					</GalleryThumbnail>	
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
				</div>
				<div class="imgs">
					<GalleryThumbnail>
						<img src="imges.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="imges2.webp" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="2imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
					<GalleryThumbnail>
						<img src="8imges.jpg" alt="Simple lightbox">
					</GalleryThumbnail>
				</div> 
			</svelte:fragment>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges4.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges6.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="imges2.webp" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="2imges.jpg" alt="Simple lightbox">
				</GalleryImage>
				<GalleryImage>
					<img src="8imges.jpg" alt="Simple lightbox">
				</GalleryImage>
			</LightboxGallery>
			</div>
		</div>
		<div class="lode">
		<h1>lode more</h1></div>
	</section>
	<br><br><br><br><br><br>
	<Footer/>
    <style>
		.lode{
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.lode h1{
			border-bottom: 2px solid rgb(204, 204, 204);
			font-weight: 300;
			padding: 10px;
            transition: .5s;
		}
        .lode h1:hover{
            cursor: pointer;
            border-top: 4px solid rgb(204, 204, 204);
            border-right: 2px solid rgb(204, 204, 204);
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
		color: rgb(187, 187, 187);
		font-size: 25px;
		font-family: "Cinzel", serif;
	}
	.mk{
		color: white;
		border-bottom: 1px solid white;
	}
	.container h1{
		margin-top: 200px;
		
	}
	.container {
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
	
    </style>