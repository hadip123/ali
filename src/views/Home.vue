
<template>
  <div :style="{ background: $vuetify.theme.themes.dark.background }">
    
    <v-carousel class="duas-caro" cycle interval="4000" height="550">
      <v-carousel-item v-for="(slide, i) in slides" :key="i">
        <v-sheet color="primary" height="100%">
          <v-row class="fill-height" align="center" justify="center">
            <v-img :src="slide.image"></v-img>
            <p class="daus-ali">{{slide.text}}</p>

          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
    <!-- <SideBar /> -->
    <div style="height: 20px"></div>
    <div class="fc">
      <v-card width="20vw" class="kos-nane">
        <div class="hadi-icon">
          <v-icon color="black" size="40" class="hadi-school"
            >mdi-mosque</v-icon
          >
        </div>
        <v-card-title dir="rtl" class="fucking-building">
          امکانات رفاهی
        </v-card-title>

        <v-card-text>
          <div v-for="(fbi, i) in fuckingBuildingItems" :key="i">
            <div class="fbi">
              <p style="flex: 1">{{ fbi.text }}</p>
              <p
                style="
                  flex: 1;
                  text-align: left;
                  font-style: italic;
                  color: grey;
                "
              >
                {{ fbi.value }}
              </p>
            </div>
            <v-divider></v-divider>
          </div>
        </v-card-text>
      </v-card>
      <div class="" style="width: 40px"></div>
      <v-card width="20vw" class="kos-nane">
        <div class="hadi-icon">
          <v-icon color="black" size="40" class="hadi-school"
            >mdi-town-hall</v-icon
          >
        </div>
        <v-card-title dir="rtl" class="fucking-building">
          ساختمان
        </v-card-title>

        <v-card-text>
          <div v-for="(fbi, i) in fuckingBuildingItems" :key="i">
            <div class="fbi">
              <p style="flex: 1">{{ fbi.text }}</p>
              <p
                style="
                  flex: 1;
                  text-align: left;
                  font-style: italic;
                  color: grey;
                "
              >
                {{ fbi.value }}
              </p>
            </div>
            <v-divider></v-divider>
          </div>
        </v-card-text>
      </v-card>
      <div style="width: 40px"></div>
      <v-card width="20vw" class="kos-nane">
        <div class="hadi-icon">
          <v-icon color="black" size="40" class="hadi-school"
            >mdi-chair-school</v-icon
          >
        </div>
        <v-card-title dir="rtl" class="fucking-building">
          تجهیزات اموزشی
        </v-card-title>

        <v-card-text>
          <div v-for="(fbi, i) in fuckingBuildingItems" :key="i">
            <div class="fbi">
              <p style="flex: 1">{{ fbi.text }}</p>
              <p
                style="
                  flex: 1;
                  text-align: left;
                  font-style: italic;
                  color: grey;
                "
              >
                {{ fbi.value }}
              </p>
            </div>
            <v-divider></v-divider>
          </div>
        </v-card-text>
      </v-card>
    </div>

    <div></div>
    <div class="kargah">
      <v-card-title dir="rtl" class="host"> کارگاه ها </v-card-title>
      <v-divider style="width:80%; margin-right: 10%;"></v-divider>
      <v-container>
        <v-row justify="center">
          <v-col v-for="(kargah, i) in kargahHa" :key="i" cols="3">
            <v-card class="kos-nane1">
              <v-card-title>
                {{ kargah.name }}
              </v-card-title>

              <v-icon size="80">{{ kargah.icon }}</v-icon>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <v-footer color="" padless>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link }}
        </v-btn>
        <v-col class="primary py-4 text-center white--text kosghol" cols="12">
          {{ new Date().getFullYear() }} — سپاس<strong> </strong>
          <p>تمام حقوق معنوی و مادی این سایت محفوظ است</p>
          <div class="icons">
            <v-icon color="white">mdi-instagram</v-icon>
            <v-icon color="white">mdi-facebook</v-icon>
            <v-icon color="white">mdi-whatsapp</v-icon>
          </div>
        </v-col>
      </v-row>
    </v-footer>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import SideBar from "../components/SideBar.vue";
export default Vue.extend({
  name: "Home",
  data() {
    return {
      fuckingBuildingItems: [
        { text: "مساحت زمین", value: "گزارش نشده" },
        { text: "مساحت زمین", value: "گزارش نشده" },
        { text: "مساحت زمین", value: "گزارش نشده" },
        { text: "مساحت زمین", value: "گزارش نشده" },
        { text: "مساحت زمین", value: "گزارش نشده" },
        { text: "مساحت زمین", value: "گزارش نشده" },
      ],
      slides: [
        {image: "https://i.picsum.photos/id/234/1280/720.jpg?grayscale&hmac=tfzSeY7Z1E4qhxDwrSCfhcAhYnvP2Frl99e1j4DASOM", text: 'هنرستان نمونه دولتی امام خمینی (ره)'},
        {image: 'https://picsum.photos/1280/720?grayscale?random=4', text: 'شهرستان بجنورد'},
        {image: 'https://picsum.photos/1280/720?grayscale?random=3', text: 'در مقطع فنی و حرفه ای'},
        {image: 'https://picsum.photos/1280/720?grayscale?random=2', text: 'با امکانات ایده عال'},
      ],
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
      
      kargahHa: [
        { name: "آزمایشگاه فیزیک", icon: "mdi-atom" },
        { name: "آزمایشگاه شیمی", icon: "mdi-filter" },
        { name: "آزمایشگاه زیست شناسی", icon: "mdi-bacteria-outline" },
        { name: "کارگاه رایانه", icon: "mdi-laptop" },
        { name: "کارگاه هنر های تجسمی", icon: "mdi-fountain-pen" },
        { name: "کارگاه حرفه و فن", icon: "mdi-tools" },
        { name: "سالن مطالعه", icon: "mdi-book-open-variant" },
        { name: "واحد مشاوره", icon: "mdi-human-male-board-poll" },
      ],
    };
  },
  methods: {
    changeS(v: any) {
      console.log(v);

      this.sItems = this.items.filter((item) => item.includes(v.target.value));
    },
  },
  mounted() {
    this.sItems = this.items;
  },
  components: {
    SideBar,
    SheetFooter: {
      functional: true,

      render(h: any, { children }: any) {
        return h(
          "v-sheet",
          {
            staticClass: "mt-auto align-center justify-center d-flex px-2",
            props: {
              color: "rgba(0, 0, 0, .36)",
              dark: true,
              height: 50,
            },
          },
          children
        );
      },
    },
  },
});
</script>

<style scoped lang="scss">
@font-face {
  font-family: "Iran sans";
  src: url("../assets/IRANsans.ttf");
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
