<script>
	// @ts-nocheck
	import { onMount, onDestroy } from 'svelte';
  
 let originalBackgroundColor;
 
 onMount(() => {
	 // Save the original background color
	 originalBackgroundColor = document.body.style.backgroundColor;
	 // Set the new background color for this page
	 document.body.style.backgroundColor = 'black';
 });
 
 onDestroy(() => {
	 // Restore the original background color when this component is destroyed
	 document.body.style.backgroundColor = originalBackgroundColor;
 });
  </script>
<header>
	<div class="logo"><a href="../"><h1>crown wedding films</h1></a></div>
	<div class="list">
		<div class="itms">
			<a href="../#about"><p>about us</p></a>
			<a href="../gallery"><p>Gallery </p></a></div>
		<div class="itms">
			<a href="../livestream"><p >livestream</p></a>
			<button>Login</button>
		</div>
	</header>

	<section>
		<div class="cont">
			<div class="bi">
				<img src="images/play.jpeg" alt="play">
			</div>
			<div class="playbutton">
			<img src="images/play.svg" alt="play button">
		</div>
		</div>
	</section>
	<div class="copyright">
		<p>crown © 2024</p>
	  </div>
	  <style>
	  
	  .copyright{
		display: flex;
		justify-content: center;
		align-items: center;
		top: 40px;
		position: relative;
		text-align: center;
	  }
	  .copyright p{
			  font-size: 12px;
			  color: rgb(181, 181, 181);
			}
   header{
      margin-top: -150px;
	  background-color: black;
	  height: 90px;
   }
   .itms button{
	border: 1px solid rgb(255, 255, 255);
	color: rgb(255, 255, 255);
}
   .logo a{
      text-decoration: none;
      color: white;
   }
  .logo {
		justify-content: center;
		display: flex;
	}
	.list{
		display: flex;
		padding-left: 30px;
		padding-right: 30px;
		justify-content: space-between;
	}
	.itms{
		display: flex;
	}
	.itms a{
		text-decoration: none;
		color: white;
	}
	.cont{
		padding-left: 80px;
		padding-right: 80px;
	}
    .cont .bi{
		overflow: hidden;
		margin-top: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 70vh;
		opacity: 60%;
		width: 100%;
    }
	.bi img{
		width: 100%;
		scale: 110%;
		position: relative;
	}
	.playbutton{
		display: flex;
		position: relative;
		bottom: 350px;
		margin-top: -30px;
		justify-content: center;
		align-items: center;
		text-align: center;
    }
	.playbutton img{
		width: 90px;
		cursor: pointer;
		animation: buttonfor 2s infinite;
	}
	.playbutton img:hover{
		animation-play-state: paused;
	}
	@keyframes buttonfor {
    0% {
      transform: scale(1);
    }
    50% {
      transform: scale(1.2);
    }
    100% {
      transform: scale(1);
    }
  }
</style>