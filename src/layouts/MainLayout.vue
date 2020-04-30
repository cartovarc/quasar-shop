<template>
  <q-layout view="lHr lpr lFr">
    <q-header class="text-black" bordered>
      <q-bar dark class="my-bar text-white q-pa-md">
        <div class="col text-center text-weight-medium text-overline">
          100% AUTENTICA
        </div>
      </q-bar>
      <q-toolbar class="q-pa-md">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-btn v-if="!this.$q.screen.gt.sm" flat round dense icon="o_search" />

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

        <q-btn v-if="this.$q.screen.gt.sm" flat round dense icon="o_search" />
        <q-btn
          v-if="this.$q.screen.gt.sm"
          flat
          round
          dense
          icon="o_account_circle"
        />
        <q-btn flat round dense icon="favorite_border" />
        <q-btn class="q-mr-md" flat round icon="o_shopping_cart">
          <q-badge color="red" floating>10</q-badge>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink";

export default {
  name: "MainLayout",

  components: {
    EssentialLink,
    "my-tabs": require("src/components/Header/MyTabs.vue").default
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
      essentialLinks: [
        {
          title: "Docs",
          caption: "quasar.dev",
          icon: "school",
          link: "https://quasar.dev"
        },
        {
          title: "Github",
          caption: "github.com/quasarframework",
          icon: "code",
          link: "https://github.com/quasarframework"
        },
        {
          title: "Discord Chat Channel",
          caption: "chat.quasar.dev",
          icon: "chat",
          link: "https://chat.quasar.dev"
        },
        {
          title: "Forum",
          caption: "forum.quasar.dev",
          icon: "record_voice_over",
          link: "https://forum.quasar.dev"
        },
        {
          title: "Twitter",
          caption: "@quasarframework",
          icon: "rss_feed",
          link: "https://twitter.quasar.dev"
        },
        {
          title: "Facebook",
          caption: "@QuasarFramework",
          icon: "public",
          link: "https://facebook.quasar.dev"
        },
        {
          title: "Quasar Awesome",
          caption: "Community Quasar projects",
          icon: "favorite",
          link: "https://awesome.quasar.dev"
        }
      ]
    };
  }
};
</script>

<style scoped>
.my-bar {
  background-color: #ff6666;
}
</style>
