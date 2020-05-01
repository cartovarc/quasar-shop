<template>
  <q-card class="my-card">
    <q-img
      src="https://upload.wikimedia.org/wikipedia/commons/9/96/Lapiz_labial.jpg"
    />

    <q-card-section>
      <div class="row no-wrap items-center">
        <div class="col text-h6 ellipsis">
          Labial rojo
        </div>
        <div
          class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
        ></div>
      </div>
    </q-card-section>

    <q-card-section class="q-pt-none">
      <div class="text-subtitle1">
        $5000
      </div>
      <div class="text-caption text-grey">
        Small plates, salads & sandwiches in an intimate setting.
      </div>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  @media (min-width: $breakpoint-sm-min)
    max-width: 250px
  @media (max-width: $breakpoint-sm-max)
    max-width: 150px
</style>
