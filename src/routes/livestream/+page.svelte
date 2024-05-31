<script>
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

  function showAlert(){
    alert("Invitation not allowed");
  }
 </script>
<header>
	<div class="logo"><a href="./"><h1>crown wedding films</h1></a></div>
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
<br>
<div class="copyright">
  <p>crown © 2024</p>
</div>
<style>

.copyright{
  display: flex;
  justify-content: center;
  align-items: center;
  top: 50px;
  position: relative;
  text-align: center;
}
.copyright p{
        font-size: 12px;
        color: rgb(181, 181, 181);
      }
   header{
      margin-top: -180px;
      height: 90px;
      background-color: black;
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
   .itms button{
	border: 1px solid rgb(255, 255, 255);
	color: rgb(255, 255, 255);
}
   .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      justify-content: center;
      align-items: center;
      text-align: center;
      margin-top: 180px;
    }
    .container h1{
      font-size: 48px;
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
</style>