<template>
  <div class="q-ma-none" style="max-width: 350px">
    <div class="text-h5 text-weight-bolder q-mb-xs">Maquillaje</div>
    <q-list class="rounded-borders q-mr-md">
      <q-separator class="q-mb-md" />

      <q-expansion-item icon="perm_identity">
        <template v-slot:header>
          <q-avatar class="q-mr-lg" size="md">
            <img
              src="https://i.pinimg.com/236x/81/a4/34/81a434c7b1898a78d455c76aa112a94e.jpg"
            />
          </q-avatar>
          <span class="text-subtitle1 q-mt-xs">Ojos</span>
          <q-space />
        </template>
        <q-list class="rounded-borders" style="max-width: 350px">
          <q-item class="q-ml-lg" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img
                  src="https://therealflappers.files.wordpress.com/2016/02/maquillar-tus-ojos-rimel.jpg"
                />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label lines="1">Pestañina</q-item-label>
            </q-item-section>
          </q-item>

          <q-item class="q-ml-lg" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img
                  src="https://i.pinimg.com/564x/97/03/de/9703de9314752df0e23f2ae5f20d0a4e.jpg"
                />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label lines="1">Sombras</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-expansion-item>
      <q-expansion-item expand-separator icon="perm_identity">
        <template v-slot:header>
          <q-avatar class="q-mr-lg" size="md">
            <img
              src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR3hxDPgcIgLH3iU7wz731thyrk-GREJ7N3Ls7ArUyk70bwo1Vi&usqp=CAU"
            />
          </q-avatar>
          <span class="text-subtitle1 q-mt-xs">Labios</span>
          <q-space />
        </template>
        <q-list class="rounded-borders" style="max-width: 350px">
          <q-item class="q-ml-lg" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img
                  src="https://i.pinimg.com/474x/a9/ff/a3/a9ffa3d481821e8de1ffa8837ebd5cad.jpg"
                />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label lines="1">Labiales</q-item-label>
            </q-item-section>
          </q-item>

          <q-item class="q-ml-lg" clickable v-ripple>
            <q-item-section avatar>
              <q-avatar size="md">
                <img
                  src="https://4.bp.blogspot.com/-jEG7GVaGBV8/VAXCnVyh1sI/AAAAAAAAAY4/MJ8VYkQqasI/s1600/cyzone-brillos-labiales-hermosos-varios-colores-tb-lancome-58-MLA4642491415_072013-O.jpg"
                />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label lines="1">Brillos</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-expansion-item>
    </q-list>
  </div>
</template>

<script>
export default {};
</script>

<style lang="sass" scoped>
.q-item__section column q-focusable relative-position cursor-pointer q-item__section--side justify-center
    padding-right: 0 !important
    padding-left: 0 !important
</style>
