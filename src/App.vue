<template>
  <v-app>
    <v-app-bar app color="primary" hide-on-scroll>
      <v-btn
        :style="{ display: searchButtonD }"
        icon
        @click="
          searchDisplay = searchDisplay === 'none' ? 'block' : 'none';
          searchButtonD === 'none' ? 'block' : 'none';
        "
      >
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <div class="search">
        <v-autocomplete
          label="جستجو"
          dense
          :style="{ display: searchDisplay, marginTop: '-18px' }"
          solo
          :items="items"
          rounded
          prepend-inner-icon="mdi-magnify"
        >
        </v-autocomplete>

      </div>
       <div class="text-center">
            <v-btn text style="display: flex" @click="goToLogin">
              <v-icon class="sabt-nam" color="white">mdi-home </v-icon>
              <p
                :style="{ color: 'white', fontSize: '15px', marginTop: '13px',margin:'0px 10px 0px 0px' }"
              >
               ورود/ثبت نام
              </p>
            </v-btn>
      </div>
      <div class="text-center" style="margin: 0px 50px 0px 0px">
        <link rel="stylesheet" href="http://isffaza.ir/TOUR360/49-SHOMALI-emam/index.html">
           <a href="http://isffaza.ir/TOUR360/49-SHOMALI-emam/index.html">

            <v-btn text style="display: flex" v-bind="attrs" v-on="on">
              <v-icon class="sabt-nam" color="white">mdi-account </v-icon>
              <p
                :style="{ color: 'white', fontSize: '15px', marginTop: '13px',margin:'0px 10px 0px 0px' }"
              >
               بازدید انلاین
              </p>
            </v-btn>
           </a>
      </div>
      <v-spacer></v-spacer>
      <div class="text-center">
        <v-menu transition="fab-transition">
          <template v-slot:activator="{ on, attrs }">
            <div v-ripple style="display: flex" v-bind="attrs" v-on="on">
              <v-icon color="white">mdi-book</v-icon>
              <p
                :style="{ color: 'white', fontSize: '15px', marginTop: '13px' }"
              >
                درباره هنرستان
              </p>
            </div>
          </template>
          <v-list>
            <v-list-item v-for="n in 5" :key="n">
              <v-list-item-title v-text="'Item ' + n"></v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </div>
      <div :style="{ width: `${fasele}px` }"></div>
      <div v-ripple style="display: flex">
        <v-icon color="white">mdi-hammer-screwdriver</v-icon>
        <p
          :style="{ color: 'white', fontSize: '15px', marginTop: '13px' }"
          class="daus"
        >
          رشته ها
        </p>
      </div>
      <div :style="{ width: `${fasele}px` }"></div>
      <div v-ripple style="display: flex">
        <v-icon color="white">mdi-cogs</v-icon>
        <p :style="{ color: 'white', fontSize: '15px', marginTop: '13px' }">
          خدمات اموزشی
        </p>
      </div>
    </v-app-bar>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  data: () => ({
    items: [
        "رشته شبکه و نرم افزار",
        "رشته برق",
        "رشته تاسیسات",
        "رشته تربیت بدنی",
        "رشته ساختمان",
      ],
      sItems: [""],
      searchText: "",
      searchDisplay: "none",
      searchButtonD: "block",
      fasele: 125,
  }),
  methods: {
    changeS(v: any) {
      console.log(v);

      this.sItems = this.items.filter((item) => item.includes(v.target.value));
    },
    goToLogin() {
      this.$router.push('/login')
    }
  },
  mounted() {
    this.sItems = this.items;
  },
});
</script>

<style>
@font-face {
  font-family: "Iran sans";
  src: url("./assets/IRANsans.ttf");
}
* {
  font-family: "Iran sans";
}
.hadi-icon {
  display: flex;
  justify-content: center;
  align-items: center;
}
.hadi-school {
  justify-content: center;
  align-items: center;
  height: 80px;
  width: 80px;
  background: white;
  border-radius: 90px;
  box-shadow: 2px 2px 4px #8d8888;
}

.ccc {
  background: #f7f7f7 !important;
  margin: 19px !important;
  border-radius: 10px !important;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.ccc:hover {
  background: white !important;
  box-shadow: 2px 4px 4px 0px !important;
  transition: 0.5s !important;
}
.fucking-building {
  text-align: center !important;
  direction: rtl !important;
}
.fbi {
  display: flex;
  flex-direction: row;
}
.fc {
  display: flex;
  justify-content: center;
  box-shadow: 0px 0px 0px 0px;
}
.search {
  height: 0px;
  transition: 3s;
}
.darbareh {
  height: 3px;
}
.subheading {
}
.icons {
  display: flex;
  flex-direction: row;
}
.kosghol {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.host {
  justify-content: center;
}
.fill-height {
  margin: 2px 2px 0px 0px;
}
.hover:fill-height {
  margin: 5px 4px 0px 0px;
}
.daus-ali {
  position: absolute;
  color: white;
  font-size: 40px;
}
.kos-nane:hover {
  transition-duration: 0.4s;
  box-shadow: 1px 0px 10px 0px !important;
}
.kos-nane1 {
  width: 255px;
  height: 255px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;

}
.kos-nane1:hover {
  transition-duration: 0.4s;
  box-shadow: 2px 0px 10px 0px !important;
}
.sabt-nam{
  margin: 0px 20px 0px 0px;
}
</style>