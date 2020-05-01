<template>
  <q-layout view="lHr lpr lFr">
    <q-header class="bg-white text-black" bordered>
      <q-bar dark class="my-bar text-white q-pa-md">
        <div class="col text-center text-weight-medium text-overline">
          100% AUTENTICA
        </div>
      </q-bar>
      <q-toolbar class=" q-pa-md">
        <q-btn
          flat
          dense
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-btn v-if="!this.$q.screen.gt.sm" flat dense icon="o_search" />

        <q-img
          v-if="this.$q.screen.gt.sm"
          class="q-ml-md"
          :src="logoSrc"
          spinner-color="white"
          style="width: 140px; max-width: 150px"
        />

        <q-toolbar-title :class="{ 'text-center': !this.$q.screen.gt.sm }">
          <my-tabs v-if="this.$q.screen.gt.sm" />
          <q-img
            v-if="!this.$q.screen.gt.sm"
            class="q-ml-md"
            :src="logoSrc"
            spinner-color="white"
            style="width: 140px; max-width: 150px"
          />
        </q-toolbar-title>

        <q-btn v-if="this.$q.screen.gt.sm" flat dense icon="o_search" />
        <q-btn v-if="this.$q.screen.gt.sm" flat dense icon="o_account_circle">
        </q-btn>
        <q-btn flat dense icon="favorite_border">
          <q-badge color="red" floating>1</q-badge>
        </q-btn>
        <q-btn
          @click="rightDrawerOpen = !rightDrawerOpen"
          flat
          icon="o_shopping_cart"
        >
          <q-badge color="red" floating>4</q-badge>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      behavior="mobile"
      content-class="bg-grey-1"
    >
    </q-drawer>

    <q-drawer
      bordered
      content-class="bg-grey-1"
      v-model="rightDrawerOpen"
      behavior="mobile"
      side="right"
    >
      <right-drawer-content @hideCart="rightDrawerOpen = false">
      </right-drawer-content>
    </q-drawer>

    <q-page-container class="my-container">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink";

export default {
  name: "MainLayout",

  components: {
    "my-tabs": require("src/components/Header/MyTabs.vue").default,
    "right-drawer-content": require("src/components/RightDrawerContent.vue")
      .default
  },

  computed: {
    logoSrc() {
      if (this.$q.screen.gt.md) {
        return "statics/logos/rosaM.png";
      } else {
        return "statics/logos/rosaXS.png";
      }
    }
  },

  data() {
    return {
      leftDrawerOpen: false,
      rightDrawerOpen: false
    };
  }
};
</script>

<style lang="sass" scoped>
.my-bar
  background-color: #ff6666

.my-container
  @media (min-width: $breakpoint-sm-min)
    margin-left: 80px
    margin-right: 80px
    margin-top: 10px
  @media (max-width: $breakpoint-sm-max)
    margin-left: 10px
    margin-right: 10px
    margin-top: 10px
</style>
