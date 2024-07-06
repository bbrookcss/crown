<script>
	import { onMount } from 'svelte';
	let isLoginVisible = false;
    let username = '';
    let password = '';
    let message = '';
    let success = false;

    const loginUser = async () => {
        if (!username || !password) {
            message = 'Username and password are required!';
            success = false;
            return;
        }

        const response = await fetch('https://backend.crownweddingfilms.com/users/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify({ username, password }),
        });

        const data = await response.json();

        if (response.ok) {
            message = 'Login successful!';
            success = true;
            localStorage.setItem('token', data.token); // Store JWT token in localStorage
            localStorage.setItem('userId', data.id); // Store user ID in localStorage
            window.location.href = '/account'; // Redirect to /account page
        } else {
            message = data.message || 'Login failed!';
            success = false;
        }
    };
	
  
	function showLogin() {
	  isLoginVisible = true;
	}
  
	function preventSpaces(event) {
	  if (event.key === ' ') {
		event.preventDefault();
	  }
	}
  
	function handleLoginClick() {
	  isLoginVisible = false;
	}
  
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
  
	// Function to handle screen resize
	
  </script>
  
  <header>
	<div class="navbutton">
	  <!-- svelte-ignore a11y-invalid-attribute -->
	  <a href="#" on:click={navbutt}><img src="/images/nav.png" alt="" class="navbutton" /></a>
	</div>
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<!-- svelte-ignore a11y-no-static-element-interactions -->
	<div class="backblur" on:click={navx}>
	  <button>X</button>
	</div>
	<div class="logo">
	  <a href="../"><h1>crown wedding films</h1></a>
	</div>
	<div class="list">
	  <div class="itms">
		<a href="../#about"><p>about us</p></a>
		<a href="../gallery"><p>Gallery</p></a>
	  </div>
	  <div class="itms">
		<a href="../livestream"><p>livestream</p></a>
		<button on:click={showLogin}>Login</button>
	  </div>
	</div>
  </header>
  
  {#if isLoginVisible}
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<!-- svelte-ignore a11y-no-static-element-interactions -->
	<div class="login" on:click={handleLoginClick}>
	  <div class="logbox" on:click|stopPropagation>
		<h1>Find your moment</h1>
		<form on:submit|preventDefault={loginUser}>
			<input type="text" placeholder="Bride & Groom (betty&natty)" on:keydown={preventSpaces} id="username" bind:value={username} required />
			<input type="number" placeholder="Wedding day (28)" id="password" bind:value={password} required />
			
			<button type="submit">Login</button>
			{#if message}
			  <p class:message class:success={success} class:error={!success}>{message}</p>
		  {/if}
		  </form>
	  </div>
	</div>
  {/if}
  
  <style>
	.login {
	  width: 100%;
	  height: 100%;
	  display: flex;
	  position: fixed;
	  background-color: rgba(0, 0, 0, 0.7);
	  top: 0;
	  left: 0;
	  justify-content: center;
	  align-items: center;
	  text-indent: center;
	  z-index: 100;
	}
	.login .logbox {
	  width: 500px;
	  height: 310px;
	  background-color: white;
	  border-radius: 10px;
	  display: flex;
	  flex-direction: column;
	  justify-content: center;
	  align-items: center;
	  text-align: center;
	}
	.login .logbox h1 {
	  font-size: 30px;
	  color: black;
	}
	.logbox p{
		color: red;
	}
	.logbox input {
	  width: 70%;
	  margin-bottom: 10px;
	  height: 40px;
	  border-radius: 10px;
	  border: 1px solid black;
	  padding: 0 20px;
	  font-size: 15px;
	}
	.logbox button {
	  width: 40%;
	  height: 40px;
	  border-radius: 10px;
	  border: none;
	  padding: 0 20px;
	  font-size: 23px;
	  background-color: #013b1579;
	  color: white;
	}
	.logbox button:hover {
	  background-color: #013b15;
	  transition: .3s;
	}
	.logo {
	  justify-content: center;
	  display: flex;
	}
	.logo a {
	  text-decoration: none;
	  color: rgb(0, 0, 0);
	}
	.list {
	  display: flex;
	  padding-left: 30px;
	  padding-right: 30px;
	  margin-top: -10px;
	  justify-content: space-between;
	}
	.itms {
	  display: flex;
	}
	.itms a {
	  text-decoration: none;
	  color: rgb(0, 0, 0);
	}
	.backblur {
	  display: none;
	}
	.navbutton {
	  display: none;
	}
	@media (max-width: 900px) {
	  .list {
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
	  .itms p {
		margin: 20px 15px;
		font-size: 23px;
		justify-content: center;
		text-align: center;
		align-items: center;
	  }
	  .backblur {
		width: 100%;
		height: 100%;
		position: fixed;
		top: 0;
		left: 0;
		background-color: rgba(0, 0, 0, 0.7);
		backdrop-filter: blur(8px);
	  }
	  .backblur button {
		border: none;
		left: 4%;
		top: 2%;
		justify-content: center;
		text-align: center;
		font-weight: 200;
		color: white;
		font-family: Arial, Helvetica, sans-serif;
		background: transparent;
		font-size: 50px;
		position: absolute;
	  }
	  .navbutton {
		position: absolute;
		display: flex;
		left: 90%;
	  }
	  .navbutton img {
		width: 50px;
		outline: hidden;
		height: 35px;
		top: 20px;
		position: relative;
		transition: .5s;
	  }
	  .navbutton img:hover {
		cursor: pointer;
		scale: 1.1;
		transition: .5s;
	  }
	}
	@media (max-width: 640px) {
	  .logo {
		padding-right: 50px;
	  }
	  .logo h1 {
		font-size: 28px;
	  }
	  .navbutton img {
		width: 40px;
		height: 33px;
		top: 20px;
		position: relative;
		transition: .5s;
	  }
	  .backblur button {
		font-size: 40px;
	  }
	}
	@media (max-width: 400px) {
	  .logo h1 {
		font-size: 25px;
	  }
	  .logo {
		padding-right: 40px;
	  }
	  .navbutton img {
		width: 35px;
		height: 30px;
		top: 20px;
		position: relative;
		transition: .5s;
	  }
	  .navbutton {
		left: 88%;
	  }
	}
  </style>
  