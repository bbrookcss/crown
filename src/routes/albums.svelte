<script>
    // @ts-nocheck
    
    import { Lightbox, LightboxGallery, GalleryThumbnail, GalleryImage } from 'svelte-lightbox';
    </script>
    <section>
        <div class="container" id="gallery">
            <div class="box">
                <LightboxGallery>
                    <svelte:fragment slot="thumbnail">
                        <div class="imgs">
                            <GalleryThumbnail>
                                <img src="/images/imges.webp" alt=" SAPMD">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/imges2.webp" alt="">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/2imges.jpg" alt="">
                            </GalleryThumbnail>
                        </div>
                        <div class="imgs">
                            <GalleryThumbnail>
                                <img src="/images/tr.jpg" alt="">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/imges4.webp" alt="">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/a.jpg" alt="">
                            </GalleryThumbnail>
                        </div>
                        <div class="imgs class1">
                            <GalleryThumbnail>
                                <img src="/images/imges6.webp" alt="">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/rt.jpg" alt="">
                            </GalleryThumbnail>
                            <GalleryThumbnail>
                                <img src="/images/d.jpg" alt="">
                            </GalleryThumbnail>
                        </div>
                    </svelte:fragment>
                    <GalleryImage>
                        <img src="/images/imges.webp" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/imges2.webp" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/2imges.jpg" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/tr.jpg" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/imges4.webp" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/a.jpg" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/imges6.webp" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/rt.jpg" alt="">
                    </GalleryImage>
                    <GalleryImage>
                        <img src="/images/d.jpg" alt="">
                    </GalleryImage>
                </LightboxGallery>
            </div>
        </div>
    </section>
    
    <style>
    section {
        background: linear-gradient(to bottom, white 0%, white 5%, rgb(238, 238, 238) 95%, rgb(238, 238, 238) 100%);
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
        margin-top: 200px;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }
    
    .container .box .imgs img:hover {
        scale: 104%;
        transition: 0.5s;
    }
    
    .container .box .imgs {
        display: flex;
        flex-direction: column;
        width: 32.5%;
    }
    
    .container .box .imgs img {
        width: 100%;
        margin-bottom: 15px;
        transition: 0.2s;
        cursor: pointer;
        border-radius: 5px;
        height: auto;
    }
    /* Media queries to adjust layout and visibility on smaller screens */
    @media (max-width: 640px) {
        .class1 img {
            display: none;
        }
        .container {
            padding-left: 10px;
            padding-right: 10px;
        }
        .container .box {
            
            flex-direction: column;
            margin-top: 100px;
        }
        .container .box .imgs {
            width: 100%;
        }
    }
    </style>
    