<template>
  <div>
    <div class="row text-weight-bolder q-mb-lg my-container">
      <q-breadcrumbs style="align-self: left;">
        <q-breadcrumbs-el label="Inicio" icon="home" />
        <q-breadcrumbs-el label="Labios" />
      </q-breadcrumbs>
    </div>
    <div class="row my-container">
      <div class="col-md-4 col-xs-12" style="overflow: auto;">
        <left-menu v-if="this.$q.screen.gt.sm" />
      </div>

      <div
        class="col-md-8 col-xs-12 q-pa-sm q-ma-none"
        style="overflow: auto;min-height: 600px;"
      >
        <template>
          <div class="text-center col-12 q-ma-none">
            <span class="text-h4 text-weight-bolder">Pestañina</span>
          </div>

          <q-bar
            class="text-subtitle1 bg-grey-2 q-mt-md q-mb-md q-pl-xl"
            style="height: 40px;"
          >
            <q-space />
            Sort by
          </q-bar>
          <div class="row flex flex-center q-gutter-md">
            <product-card v-for="card in 4" v-bind:key="card" />
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slide: 1
    };
  },
  components: {
    "left-menu": require("src/components/Store/LeftMenu.vue").default,
    "product-card": require("src/components/Store/ProductCard.vue").default
  }
};
</script>

<style lang="sass" scoped>
.my-bar
  background-color: #ff6666

.my-container
  @media (min-width: $breakpoint-sm-min)
    margin-left: 180px
    margin-right: 180px
    margin-top: 10px
  @media (max-width: $breakpoint-sm-max)
    margin-left: 0px
    margin-right: 0px
    margin-top: 10px
</style>
