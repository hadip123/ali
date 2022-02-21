<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <v-app-bar app color="grey" hide-on-scroll>
      <v-btn
        :style="{ display: searchButtonD }"
        icon
        @click="
          searchDisplay = searchDisplay === 'none' ? 'block' : 'none';
          searchButtonD === 'none' ? 'block' : 'none';
        "
      >
        <v-icon>fa-search</v-icon>
      </v-btn>
      <div class="search">
        <v-text-field
          label="جستجو"
          :style="{ display: searchDisplay }"
          solo
          rounded
          prepend-inner-icon="fa-search"
        >
        
        </v-text-field>
      </div>
      <v-spacer></v-spacer>
      <v-card v-ripple width="20px" height="20px" rounded="pill"> </v-card>
      <div style="width: 10px"></div>
      <div class="text-center">
          <v-menu transition="fab-transition">
      <template v-slot:activator="{ on, attrs }">
        
      <div v-ripple style="display: flex"  v-bind="attrs"
          v-on="on">
        <v-icon color="white">fa-book</v-icon>
        <div style="width: 10px"></div>
        <v-app-bar-title :style="{ color: 'white' }"
          >درباره هنرستان</v-app-bar-title>
      </div>
      </template>
      <v-list>
        <v-list-item
          v-for="n in 5"
          :key="n"
        >
          <v-list-item-title v-text="'Item ' + n"></v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
      <div :style="`width: ${fasele}px`"></div>
     
      <v-card v-ripple width="20px" height="20px" rounded="pill"> </v-card>
      <div v-ripple style="display: flex">
      <div style="width: 10px"></div>
      <v-icon color="white">fa-hammer</v-icon>
      <div style="width: 10px"></div>
      <v-app-bar-title :style="{ color: 'white', fontSize: '21px' }"
        >رشته ها</v-app-bar-title>
      </div>
      <div :style="`width: ${fasele}px`"></div>
      <v-card v-ripple width="20px" height="20px" rounded="pill"> </v-card>
      <div style="width: 10px"></div>
      <div v-ripple style="display: flex">
      <v-icon color="white">fa-cogs</v-icon>
      <div style="width: 10px"></div>
      <v-app-bar-title :style="{ color: 'white', fontSize: '21px' }"
        >خدمات اموزشی</v-app-bar-title
      >
      </div>
    </v-app-bar>
    <v-parallax dark src="../assets/honar.png" height="500">
      <v-row align="center" justify="center">
        <v-col class="text-center" cols="12">
          <h1 class="text-h4 font-weight-thin mb-4">
            هنرستان پسرانه و نمونه امام خمینی(ره)
          </h1>
          <h4 class="subheading">(بجنورد)</h4>
          <h1 class="magi">در مقطع فنی و حرفه ای</h1>
          <h3>شامل رشته های:</h3>
        </v-col>
      </v-row>
    </v-parallax>
    <!-- <SideBar /> -->
    <div class="fc">
      <v-card width="25vw" class="ccc">
        <div class="hadi-icon">
          <v-icon color="black" size="40" class="hadi-school">fa-mosque</v-icon>
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
      <v-card width="25vw" class="ccc">
        <div class="hadi-icon">
          <v-icon color="black" size="40" class="hadi-school">fa-school</v-icon>
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
      <v-card width="25vw" class="ccc">
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
    
  </v-app>
  
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
      searchDisplay: "none",
      searchButtonD: "block",
      fasele: 125
    };
  },
  mounted() {},
  components: {
    SideBar,
  },
});
</script>

<style scoped>
.hadi-icon {
  display: flex;
  justify-content: center;
}
.hadi-school {
  justify-content: center;
  align-items: center;
  width: 80px;
  height: 80px;
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
  box-shadow: 20px 12px 20px 0px  !important;
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
}
.search {
  height: 0px;
  transition: 3s;
  width: 200px !important ;
}
.darbareh {
  height: 3px;
  width: 20px;
}
.subheading{
width: 99%;
}
</style>