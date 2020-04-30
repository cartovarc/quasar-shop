<template>
  <q-page class="flex full-width my-class">
    <q-parallax class="my-parallax" :height="150">
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

    <q-separator />
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      slide: 1
    };
  }
};
</script>

<style scoped>
.my-parallax {
  width: 100%;
  min-height: 250px;
}
</style>
