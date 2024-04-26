<script>
	function navbutt() {
	  const backblurElements = document.getElementsByClassName("backblur");
	  const itmsElements = document.getElementsByClassName("itms");
  
	  if (backblurElements.length > 0) {
		for (let i = 0; i < backblurElements.length; i++) {
		  backblurElements[i].style.display = "block";
		}
	  }
  
	  if (itmsElements.length > 0) {
		for (let i = 0; i < itmsElements.length; i++) {
		  itmsElements[i].style.display = "block";
		}
	  }
	}
	function navx() {
	  const backblurElements = document.getElementsByClassName("backblur");
	  const itmsElements = document.getElementsByClassName("itms");
  
	  if (backblurElements.length > 0) {
		for (let i = 0; i < backblurElements.length; i++) {
		  backblurElements[i].style.display = "none";
		}
	  }
  
	  if (itmsElements.length > 0) {
		for (let i = 0; i < itmsElements.length; i++) {
		  itmsElements[i].style.display = "none";
		}
	  }


}
  </script>
  
  <header>
	<div class="navbutton">
	  <a href="#" on:click={navbutt}><img src="nav.png" alt=""></a>
	</div>
	<div class="backblur">
	  <button on:click={navx}>X</button>
	</div>
	<div class="logo">
	  <a href="./"><h1>crown wedding films</h1></a>
	</div>
	<div class="list">
	  <div class="itms">
		<a href="./#about"><p>about us</p></a>
		<a href="/gallery"><p>Gallery</p></a>
	  </div>
	  <div class="itms">
		<a href="./livestream"><p>livestream</p></a>
		<button>Login</button>
	  </div>
	</div>
  </header>
    <style>
    .logo {
		justify-content: center;
		display: flex;
	}
    .logo a{
        text-decoration: none;
        color: white;
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
	.backblur{
		display: none;
	}
	.navbutton{
		display: none;
	}
	@media (max-width: 900px){
		.list{
			justify-content: center;
			text-align: center;
			align-items: center;
			display: grid;
		}
		
		.itms {
			display: grid;
			top: 100px;
			justify-content: center;
			text-align: center;
			display: none;
			align-items: center;
			position: relative;
		}
		.itms p{
			margin: 20px 15px;
			font-size: 23px;
			justify-content: center;
			text-align: center;
			align-items: center;
		}
		.backblur{
			width: 100%;
			height: 100%;
			position: fixed;
			top: 0;
			left: 0;
			background-color: rgba(0, 0, 0, 0.7);
			backdrop-filter: blur(8px);
		}
		.backblur button{
			border: none;
			left: 4%;
			top: 2%;
			justify-content: center;
			text-align: center;
			font-weight: 200;
			color: white;
			font-family: sans-serif;
			background: transparent;
			font-size: 50px;
			position: absolute;
		}
		.navbutton{
			position: absolute;
			display: flex;
			left: 90%;
		}
		.navbutton img{
			width: 50px;
			outline: hidden;
			height: 35px;
			top: 20px;
			position: relative;
			transition: .5s;
		}
		.navbutton img:hover{
			cursor: pointer;
			scale: 1.1;
			transition: .5s;
		}
	}
	@media (max-width: 640px){
		.logo{
			padding-right: 50px;
		}
		.logo h1{
			font-size: 28px;
		}
		.navbutton img{
			width: 40px;
			height: 33px;
			top: 20px;
			position: relative;
			transition: .5s;
		}
		.backblur button{
			font-size: 40px;
		}
	}
	@media (max-width: 400px){
		.logo h1{
			font-size: 25px;
		}
		.logo{
			padding-right: 40px;
		}
		.navbutton img{
			width: 35px;
			height: 30px;
			top: 20px;
			position: relative;
			transition: .5s;
		}
		.navbutton{
			left: 88%;
		}
	}
    </style>