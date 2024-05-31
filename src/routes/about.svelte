<script>

</script>
<section class="about" id="about">
    <div class="container">
        
        <div class="row">
            <div class="col">
                <img src="/images/studio.jpg" alt="studio img">
                
            </div>
            <div class="coll">
                <h1>About Us</h1>
                <p>crown weddiing films is an innovative and highly personalised professional wedding videography company based in chester but covering all of the uk and destination weddings. with the aim of producing beautiful, individually crafted wedding films.</p>
            </div>
        </div>
    </div>
   
</section>
<style>
    .container {
        color: black;
        height: 100vh;
        background-color: rgb(238, 238, 238);
    }
    .container h1 {
        font-size: 20px;
        margin-top: 150px;
    }
    .container .row {
        display: flex;
        justify-content: space-between;
    }
    .col{
        margin-top: 200px;
    }
    .container .coll p{ 
        margin-top: 20px;
        color: rgb(0, 0, 0);padding-left: 10px;
        text-shadow: 0 0 10px rgb(255, 255, 255);
        text-transform: capitalize;
        font-size: 25px;
        font-weight: 400;
    }
    .container .col img {
        position: relative;
        width: 90%;
    }
    .coll{
        position: absolute;
        display: grid;
        place-items: center;
        place-content: center;
        text-align: center;
        place-self: center;
        width: 380px;
        margin-top: 100px;
        left: 77%;
        height: 96vh;
        background-color: rgb(238, 238, 238);
    }
    .container-2 .row h1 {
        font-size: 30px;
        margin-bottom: -20px;
    }
    .container-2 .row p{
        font-size: 18px;
        color: rgb(0, 0, 0);
    }
    @media (max-width: 1224px){
       
    }
    @media (max-width: 1024px){
        .container .col img{
            width: 88%;
            margin-bottom: 20px;
        }
        .container .col p{ 
        width: 500px;
        font-size: 23px;
        }
        .container{
        margin-top: 100px;
        }
    }
    @media (max-width: 900px){
        .container .col p{ 
        width: 500px;
        font-size: 20px;
        }
    }
    @media (max-width: 500px){
        
        .container .col p{
            width: 100%;
            font-size: 18px;
            display: -webkit-box;
            -webkit-box-orient: vertical;
            -webkit-line-clamp: 2;
        }
    }
    @media (max-width: 640px){
        .container .col p{
            width: 60%;
            backdrop-filter: blur(5px);
            margin-top: -30px;
        }
        .container{
            padding-left: 40px;
            padding-right: 40px;
        }
        .container .col img{
            width: 100%;
        }
        .container h1{
            top: -30px;
            font-size: 40px;
        }
    }

    @media (max-width: 400px){
        .container .col p{
            width: 80%;
            backdrop-filter: blur(5px);
            margin-top: -30px;
        }
        .container{
            padding-left: 20px;
            padding-right: 20px;
        }
        .container .col img{
            width: 100%;
        }
        .container h1{
            top: -30px;
            font-size: 40px;
        }
    }
</style>