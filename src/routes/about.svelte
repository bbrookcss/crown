<script>
</script>
<section class="about" id="about">
    <div class="container">
        <div class="row">
            <div class="coll">
                <h1>About Us</h1>
                <p>crown weddiing films is an innovative and highly personalised professional wedding videography company based in chester but covering all of the uk and destination weddings. with the aim of producing beautiful, individually crafted wedding films.</p>
            </div>
            <div class="col">
                <img src="/images/studio.jpg" alt="studio img">
            </div>
        </div>
    </div>
</section>
<style>
    .container {
        color: black;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        margin-top: 100px;
        background: linear-gradient(to bottom, white 0%, white 5%, rgb(238, 238, 238) 95%, rgb(238, 238, 238) 100%);


    }
    .container h1 {
        font-size: 20px;
        margin-top: 150px;
    }
    .container .row {
        display: flex;
        justify-content: space-between;
    }
    .container .coll p{ 
        width: 450px;
    }
    .container .col img {
        width: 100%;
    }
    .coll h1 {
        font-size: 50px;
    }
    @media (max-width: 1224px){
       
    }
    @media (max-width: 1024px){
        
    }
    @media (max-width: 900px){
        .container{
            height:auto;
            margin-top: 150px;
        }
        .container h1 {
        margin-top: 50px;
    }
        .container .row {
        display: grid;
        justify-content: center;
        text-align: center;
        align-items: center;
    }
    .col{
        top: 60px;
        position: relative;
    }
    .container .coll p{ 
        width: auto;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    }
    @media (max-width: 500px){
        
    }
    @media (max-width: 640px){
       
    }

    @media (max-width: 400px){
        .container h1 {
        font-size: 40px;
    }
       
    }
</style>