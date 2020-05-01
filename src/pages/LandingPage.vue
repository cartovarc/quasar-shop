<template>

  <q-page class="flex  full-width my-class">

    <q-carousel class="full-width q-panel-parent q-carousel--without-padding q-carousel--arrows-horizontal"
      arrows
      animated
      v-model="slide"
      navigation
      infinite
      autoplay
      transition-prev="slide-right"
      transition-next="slide-left"
      height="600px"
    >
      <q-carousel-slide name="first" img-src="https://www.itl.cat/pngfile/big/82-824328_makeup-brushes-wallpapers-hd-makeup-brush-strokes.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">First stop</div>
          <div class="text-subtitle1">Mountains</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="https://wallpaperaccess.com/full/695763.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Second stop</div>
          <div class="text-subtitle1">Famous City</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="third" img-src="https://mocah.org/uploads/posts/503186-makeup-brush.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Third stop</div>
          <div class="text-subtitle1">Famous Bridge</div>
        </div>
      </q-carousel-slide>
  </q-carousel>


    <q-parallax class="my-parallax q-mt-md" :height="150">
      <template v-slot:media>
        <video
          poster="https://cdn.quasar.dev/img/polina.jpg"
          autoplay
          loop
          muted
        >
          <source
            type="video/webm"
            src="https://cdn.quasar.dev/img/polina.webm"
          />
          <source
            type="video/mp4"
            src="https://cdn.quasar.dev/img/polina.mp4"
          />
        </video>
      </template>

      <h3 class="text-white">Video</h3>
    </q-parallax>
 <span class="full-width flex" >
 <q-separator class="my-separator q-mt-md "  inset/>
 </span>
<div class=" q-pa-md row col no-wrap flex-center q-tabs--not-scrollable q-tabs--horizontal  q-gutter-lg">
    

    <q-card class="my-card ">
      <a href="https://www.facebook.com/Forever-Glow-103582311199408/" target="_blank">
      <q-img src="https://www.freepnglogos.com/uploads/facebook-logo-image-0.jpg" >
        <div class="text-subtitle2 absolute-top text-center" >
          FACEBOOK
        </div>
      </q-img>
      </a>
    </q-card>

    <q-card class="my-card ">
      <a href="https://www.instagram.com/foreverglowshop" target="_blank">
      <q-img src="https://www.freepnglogos.com/uploads/instagram-logos-png-images-free-download-2.png">
        <div class="text-subtitle2 absolute-top text-center">
          INSTAGRAM
        </div>
      </q-img>
      </a>
    </q-card>

    <q-card class="my-card ">
      <a href="https://www.tiktok.com/" target="_blank">
      <q-img src="https://logodownload.org/wp-content/uploads/2019/08/tiktok-logo-icon.png">
        <div class="text-subtitle2 absolute-top text-center">
          TIK-TOK
        </div>
      </q-img>
      </a>
    </q-card>

 
  </div>
   <span class="full-width flex">
 <q-separator class="my-separator q-mt-md "  inset/>
 </span>

 <div class=" full-width flex">
    <q-carousel
      v-model="slide2"
      transition-prev="slide-right"
      transition-next="slide-left"
      swipeable
      animated
      control-color="white"
      navigation
      infinite
      autoplay
      arrows
      height="200px"
      class="full-width  q-panel-parent q-carousel--without-padding q-carousel--arrows-horizontal"
    >
      <q-carousel-slide :name="1" class="column no-wrap">
        <div class=" row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://www.frendsbeauty.com/media/brand-full/NYX_Logo.png" />
          <q-img class="rounded-borders col-6 full-height" src="https://www.frendsbeauty.com/media/brand-full/Anastasia-logo-3.png" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="2" class="column no-wrap">
        <div class=" row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://cdn11.bigcommerce.com/s-sq9zkarfah/images/stencil/1280x1280/products/102934/136588/Covergirl-Logo-Decal-Sticker__94687.1510913943.jpg?c=2?imbypass=on" />
          <q-img class="rounded-borders col-6 full-height" src="https://logodix.com/logo/480218.png" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="3" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://www.nicepng.com/png/detail/302-3023688_lancome-logo-transparent-lancome-paris-logo-png.png" />
          <q-img class="rounded-borders col-6 full-height" src="https://mmo.aiircdn.com/65/5e98280089337.jpg" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="4" class="column no-wrap">
        <div class="row fit justify-start items-center q-gutter-xs q-col-gutter no-wrap">
          <q-img class="rounded-borders col-6 full-height" src="https://www.pngitem.com/pimgs/m/212-2126345_garnier-hair-color-logo-hd-png-download.png" />
          <q-img class="rounded-borders col-6 full-height" src="https://www.bne.com.au/sites/default/files/styles/grid_image/public/Benefit_logo.png" />
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>


  </q-page>
</template>

<script>
export default {
  data() {
    return {
      slide: 'first',
      slide2: 1
    }
  }
}
</script>

<style scoped>
.my-parallax {
  width: 100%;
  min-height: 250px;
}

.my-card {
  width: 100%;
  max-width: 350px;
  min-width: 100px;
  
}

.my-separator{
  width: 70%;
  height: 1px;
  color: #f1b1bd;
}
</style>

<style lang="sass" scoped>
.custom-caption
  text-align: center
  padding: 12px
  color: white
  background-color: rgba(0, 0, 0, .3)
</style>
