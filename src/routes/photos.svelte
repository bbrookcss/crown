<script>
  // You can add any JavaScript or Svelte-specific logic here if needed.
</script>

<div class="container">
  <div class="row">
    <div class="box"><img src="/images/1.jpg" alt="alt"></div>
    <div class="box"><img src="/images/2.jpg" alt="alt"></div>
    <div class="box"><img src="/images/4.jpg" alt="alt"></div>
    <div class="box"><img src="/images/3.jpg" alt="alt"></div>
    <div class="box"><img src="/images/5.jpg" alt="alt"></div>
    <div class="box"><img src="/images/6.jpg" alt="alt"></div>
    <div class="box"><img src="/images/7.jpg" alt="alt"></div>
  </div>
</div>

<style>
  .container {
    display: flex;
    overflow-x: scroll; /* Change to horizontal scroll */
    overflow-y: hidden; /* Hide vertical scrollbar */
    flex-wrap: nowrap; /* Prevent wrapping */
    margin-top: 100px;
    scrollbar-width: none; /* Hide scrollbar for Firefox */
  }

  .container::-webkit-scrollbar {
    display: none; /* Hide scrollbar for WebKit browsers */
  }
  .row {
    display: flex;
    gap: 25px;
    padding-top: 15px;
    padding-right: 30px;
    padding-bottom: 15px;
    margin-left: 100px;
  }

  .box {
    width: 27%;
    height: 77vh;
    border-radius: 30px;
    transition: .3s;
    flex: 0 0 auto; /* Prevent box from shrinking or growing */
  }
  .box:hover {
    scale: 104%;
    transition: .3s ease-in-out;
    
  }
  .box img {
    width: 100%;
    height: 100%;
    border: none;
    object-fit: cover;
    border-radius: 30px;
  }
  @media (max-width: 900px){
    .box{
      width: 40%;
      height: 70vh;
      border-radius: 30px;
      transition: .3s;
      flex: 0 0 auto; /* Prevent box from shrinking or growing */
    }
    .row{
      margin-left: 70px;

      padding-right: 0px;
    }
  }
  @media (max-width: 500px){
       
      }
      @media (max-width: 640px){
        .box{
      width: 60%;
      height: 65vh;
      }
      .row{
      margin-left: 50px;
      gap: 15px;
    }
    }
  
      @media (max-width: 400px){
         .container {
          margin-top: 60px;
        }.box{
      width: 85%;
      height: 65vh;
      }
      .row{
      margin-left: 50px;
    }
      }
</style>
