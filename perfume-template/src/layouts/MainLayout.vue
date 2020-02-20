<template>
<q-layout view="lHh Lpr lFf">
  <q-header>
    <q-toolbar>
      <div class="col">
        <div class="text-secondary row-space-between">
          <div class="row">
            <q-icon name='email' class="q-pl-sm" />
            <div class="q-pl-sm Lacquer-font">
              mail@gmail.com
            </div>
            <q-icon name='phone' class="q-pl-lg" />
            <div class="q-pl-sm Lacquer-font">
              +989123456789
            </div>
          </div>

          <div class="row-reverse">

            <div class="q-pr-lg Lacquer-font">
              {{cart}}
            </div>
            <q-icon name='shopping_cart' class="q-pr-lg q-pt-sm" />
          </div>
        </div>



        <q-separator spaced class="separator" />
        <div class="center text-secondary q-pt-xl q-pb-xl">
          <q-btn flat class="heli-font text-h4" style="color: secondary" label="Home" />
          <q-btn flat class='heli-font text-h4' style="color: secondary" label="Blog" />
          <div class="text-h1 quentin-font q-pl-lg q-pr-lg">
            Perfume
          </div>
          <q-btn flat class='heli-font text-h4' style="color: secondary" label="Shop" />
          <q-btn flat class='heli-font text-h4' style="color: secondary" label="About" />

        </div>
      </div>


    </q-toolbar>
  </q-header>



  <q-page-container>
    <div class="q-pa-md q-pt-xl q-pt-xl q-pt-xl">
      <q-carousel animated v-model="slide" arrows navigation infinite>
        <q-carousel-slide :name="1" img-src="https://www.amouage.com/media/newhomepages/_LoveMimosa_Web_Landscape-2.png" />
        <q-carousel-slide :name="2" img-src="https://www.amouage.com/media/newhomepages/_LoveMimosa_Web_Landscape-2.png" />
        <q-carousel-slide :name="3" img-src="https://www.amouage.com/media/newhomepages/_LoveMimosa_Web_Landscape-2.png" />
        <q-carousel-slide :name="4" img-src="https://www.amouage.com/media/newhomepages/_LoveMimosa_Web_Landscape-2.png" />
      </q-carousel>
    </div>
    <div class="row-wrap">
      <div class="q-pa-xl" v-for="item in items">
        <q-card class="my-card" flat>
          <q-img src="../assets/tomf.jpg" />

          <q-card-section>
            <div class="text-overline text-orange-9">Overline</div>
            <div class="text-h5 q-mt-sm q-mb-xs">Title</div>
            <div class="text-caption text-secondary">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </div>
          </q-card-section>

          <q-card-actions>
            <q-btn flat color="secondary" label="Add to cart" />

            <q-space />

            <q-btn color="grey" round flat dense :icon="item.expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'" @click="item.expanded = !item.expanded" />
          </q-card-actions>

          <q-slide-transition>
            <div v-show="item.expanded">
              <q-separator />
              <q-card-section class="text-subitle2">
                {{ item.lorem }}
              </q-card-section>
            </div>
          </q-slide-transition>
        </q-card>
      </div>

    </div>
  </q-page-container>
</q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data() {
    return {
      cart: 0,
      slide: 1,
      items: [{
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          expanded: false,
          lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
      ]

    }
  }
}
</script>
<style lang="scss">
.shopping_cart {}
.separator {
    width: 600%;
}
.center {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    flex: 1 100%;
}
.col {
    display: flex;
    flex-flow: column;
}
.row {
    display: flex;
    flex-flow: row;
}
.row-reverse {
    display: flex;
    flex-flow: row-reverse;
}
.row-space-between {
    display: flex;
    justify-content: space-between;
}
.my-card {
    width: 100%;
    max-width: 350px;
}
.row-wrap {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}
</style>
