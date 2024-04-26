<script>

</script>
<section class="about" id="about">
    <div class="container">
        <h1>About Us</h1>
        <div class="row">
            <div class="col">
                <p>crown weddiing films is an innovative and highly personalised professional wedding videography company based in chester but covering all of the uk and destination weddings. with the aim of producing beautiful, individually crafted wedding films.</p>
            </div>
            <div class="coll">
                <img src="studio.jpeg" alt="studio img">
            </div>
        </div>
    </div>
    <div class="container-2">
        <div class="row">
            <h1>photography</h1>
            <p>lorem ipsum dolor sit amet consectetur quis sit varius conseqat sit et.</p>
        </div>
        <div class="row">
            <h1>video</h1>
            <p>lorem ipsum dolor sit amet consectetur quis sit varius conseqat sit et.</p>
        </div>
        <div class="row">
            <h1>lament albums</h1>
            <p>lorem ipsum dolor sit amet consectetur quis sit varius conseqat sit et.</p>
        </div>
    </div>
</section>
<style>
    .container {
        margin-top: 250px;
        padding-left: 80px;
        padding-right: 80px;
    }
    .container h1 {
        font-size: 55px;
        margin-bottom: 1px;
        position: relative;
        top: 100px;
        z-index: 1;
        line-height: 86px;
        font-weight: 700;
    }
    .container .row {
        display: flex;
        justify-content: space-between;
    }
    .container-2 .row:hover {
        box-shadow:  0 20px 60px 1px rgb(75, 75, 75); 
        scale: 105%;
        transition: .3s;
    }
    .container .col p{ 
        position: absolute;
        margin-top: 120px;
        z-index: 1;
        width: 640px;
        color: rgb(200, 200, 200);
        text-transform: capitalize;
        font-size: 25px;
        font-weight: 400;
    }
    .container .coll img {
        float: right;
        position: relative;
        width: 95%;
    }
    .coll{
        width: 100%;
        height: inherit;
    }
    .container-2 {
        padding-left: 180px; 
        justify-content: space-between;
        padding-right: 180px;
        display: flex;
        flex-wrap: wrap;
        margin-top: 100px;
    }
    .container-2 .row {
        display: grid;
        width: 20%;
        cursor: pointer;
        overflow: hidden;
        justify-content: center;
        text-align: center;
        padding: 5px 15px;
        transition: .5s;
        position: relative;
        border: 1px solid rgb(87, 87, 87);
        text-transform: capitalize;
        height: 230px;
    }
    .container-2 .row h1 {
        font-size: 30px;
        margin-bottom: -20px;
    }
    .container-2 .row p{
        font-size: 18px;
        color: rgb(195, 195, 195);
    }
    @media (max-width: 1224px){
        .container-2{
            padding-left: 80px;
            padding-right: 80px;
            gap: 20px;
        }
        .container-2 .row{
            width: 25%;
        }
    }
    @media (max-width: 1024px){
        .container .coll img{
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
        .container-2 .row {
            width: 25%;
        }
    }
    @media (max-width: 500px){
        .container-2 .row {
            width: 100%;
        }
        .container-2{
            padding-left: 40px;
            padding-right: 40px;
        }
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
        .container .coll img{
            width: 100%;
        }
        .container h1{
            top: -30px;
            font-size: 40px;
        }
        .container-2 .row {
            width: 95%;
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
        .container .coll img{
            width: 100%;
        }
        .container h1{
            top: -30px;
            font-size: 40px;
        }
        .container-2 .row {
            width: 100%;
        }
        .container-2{
            padding-left: 20px;
            padding-right:  20px;
        }
    }
</style>