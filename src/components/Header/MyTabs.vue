<template>
  <div class="text-subtitle1 text-weight-medium absolute-center">
    <q-tabs v-model="tab" shrink stretch>
      <q-tab
        v-for="(tab, id) in tabs"
        v-bind:key="id"
        :id="id"
        :name="id"
        :label="tab.label"
      >
        <q-resize-observer @resize="onResizeTab" />

        <q-popup-proxy
          @hide="unselectTab(id)"
          :target="'#' + id"
          ref="popup"
          :offset="offset"
          transition-show="flip-up"
        >
          <q-banner :ref="id" class="q-pa-none q-ma-none">
            <q-item
              v-for="(subcategorie, key) in tab.subcategories"
              v-bind:key="key"
              clickable
              v-ripple
            >
              <q-item-section avatar>
                <q-avatar>
                  <img :src="subcategorie.imgUrl" />
                </q-avatar>
              </q-item-section>
              <q-item-section>{{ subcategorie.label }}</q-item-section>
            </q-item>
            <q-resize-observer @resize="onResizeBanner" />
          </q-banner>
        </q-popup-proxy>
      </q-tab>
    </q-tabs>
  </div>
</template>

<script>
export default {
  computed: {
    offset() {
      let xOffset = (this.bannerWidth - this.tabWidth - 32) / 2; // include margin width
      let yOffset = 10;
      return [xOffset, yOffset];
    }
  },
  data() {
    return {
      bannerWidth: 0,
      tabWidth: 0,
      tab: "",
      tabs: {
        makeup: {
          label: "Maquillaje",
          subcategories: {
            eyes: {
              label: "Ojos",
              imgUrl:
                "https://i.pinimg.com/236x/81/a4/34/81a434c7b1898a78d455c76aa112a94e.jpg"
            },
            mouth: {
              label: "Labios",
              imgUrl:
                "https://media-esp-buyviu-com.s3.amazonaws.com/products/f37ba7428ef0863a44bb606467ec8e70-belboon-dressin-spain_thumb.png"
            }
          }
        },
        skin_care: {
          label: "Cuidado piel",
          subcategories: {
            treatments: {
              label: "Tratamientos",
              imgUrl:
                "https://braziliankeratin.com/marcia-teixeira-keratin-treatment/wp-content/uploads/2015/09/facial-care.jpg"
            },
            mask: {
              label: "Mascarillas",
              imgUrl:
                "https://previews.123rf.com/images/subbotina/subbotina1704/subbotina170400069/77096078-mujer-del-balneario-que-aplica-la-m%C3%A1scara-facial-retrato-de-detalle-de-la-bella-joven-con-una-toalla-e.jpg"
            }
          }
        },
        hair: {
          label: "Cabello",
          subcategories: {
            shampoos_acconditionators: {
              label: "Shampoos y acondicionadores",
              imgUrl:
                "https://i.ebayimg.com/thumbs/images/g/dVAAAOSwRDReTDbr/s-l96.jpg"
            },
            styling: {
              label: "Tintes de colores",
              imgUrl:
                "https://i.pinimg.com/originals/8e/21/72/8e21720dfb01fe1fde031cbe284accd4.jpg"
            }
          }
        }
      }
    };
  },
  methods: {
    unselectTab(tabUnselected) {
      let t = this;
      setTimeout(function() {
        if (t.tab == tabUnselected) {
          t.tab = "";
        }
      }, 100);
    },
    onResizeBanner(size) {
      this.bannerWidth = size.width;
    },
    onResizeTab(size) {
      this.tabWidth = size.width;
    }
  }
};
</script>
