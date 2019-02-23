<template>
  <div class="home">
    <div class="metabar">
      <img class="logo" src="..\assets\mIcon.svg" alt="Mastery">
      <div class="buttonset">
        <a href="#" class="signIn">Sign in</a>
        <a href="#" class="started">Get started</a>
      </div>
    </div>
    <div class="header">
      <div class="big-logo"></div>
      <div class="navbar">
        <div class="search">
          <img src="img/search.svg" class="search-icon" @click="start">
          <input
            type="text"
            class="search-input"
            placeholder="Search Vue Mastery"
            :class="{ 'search-start' : toggle }"
          >
          <a href="#" class="twitter" title="Visit “Vue Mastery” on Twitter">
            <img src="img/twitter.svg">
          </a>
          <a href="#" class="faceBook" title="Visit “Vue Mastery” on Facebook">
            <img src="img/facebook.svg">
          </a>
        </div>
        <a href="#" class="follow">Follow</a>
      </div>
      <hr>
    </div>
    <div class="big-content">
      <div class="nuxtImg"></div>
      <div class="bigContent">
        <h3 class="bigContent-title">7 Problems you can avoid by using Nuxt.js for your ne...</h3>
        <p class="bigContent-p">
          Vue.js is a great choice as a framework for your application. But, there
          are a
          few concerns you’ll
          likely run into.
        </p>
      </div>
    </div>
    <div class="content">
      <TheCard v-for="(item,key) in list" :item="item" :key="key" class="card">
        <template #cardHeader>
          <img :src="item.src" alt>
        </template>
        <template #cardBody>
          <div>
            <h4 class="card-title">{{ item.title }}</h4>
            <p>{{ item.content }}</p>
          </div>
        </template>
        <template #cardFoot>
          <div class="tooltip-hover">
            <div class="tooltip-position">
              <TheTooltip class="tooltip">
                <template #tooltip-author>
                  <div>{{ item.name }}</div>
                </template>
                <template #tooltip-img>
                  <div>
                    <img :src="item.personFace" class="person-face">
                  </div>
                </template>
                <template #tooltip-fan>
                  <div>Followed by {{ item.fan }} people</div>
                </template>
                <template #tooltip-button>
                  <div>
                    <a href="#" class="follow-button">Follow</a>
                  </div>
                </template>
              </TheTooltip>
            </div>
            <div class="auother">
              <img :src="item.personFace" class="person-face">
              <div class="auother-introduce">
                <h5 class="auother-name">{{ item.name }}</h5>
                <p>{{ item.time }}</p>
              </div>
            </div>
          </div>
        </template>
      </TheCard>
    </div>
  </div>
</template>
   
<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import TheCard from "@/components/TheCard";
import TheTooltip from "@/components/TheTooltip";
import "@/assets/reset.css";

export default {
  name: "home",
  data() {
    return {
      toggle: false,
      list: [
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title:
            "7 Problems you can avoid by using Nuxt.js for your next Vue app",
          content:
            "Vue.js is a great choice as a framework for your application. But, there are a few concerns you’ll likely run into.",
          personFace:
            "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
          name: "Gregg Pollack",
          time: "Jan 29",
          fan: 123
        }
      ]
    };
  },
  methods: {
    start() {
      this.toggle = !this.toggle;
    }
  },
  components: {
    HelloWorld,
    TheCard,
    TheTooltip
  }
};
</script>

<style lang="scss">
$color-green: #42b983;
$size-small-title: 26px;
$title-size: 38px;
$hr: rgba(0, 0, 0, 0.1);
.metabar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 15px 0;
}
.logo {
  width: 45px;
  height: 45px;
}
.signIn {
  margin-right: 16px;
  text-decoration: none;
  color: $color-green;
}
.started {
  border: 1px solid $color-green;
  padding: 5px 16px;
  border-radius: 4px;
  text-decoration: none;
  color: $color-green;
}
.header {
  margin-bottom: 5px;
  padding: 0 20px;
}
.bigLogo {
  width: 75%;
  margin: 45px auto;
}
.big-logo {
  width: 100%;
  height: 200px;
  background: url("https://cdn-images-1.medium.com/max/952/1*TvOnUZVlpgu-UCWh2kBFEA@2x.png")
    no-repeat;
  background-size: 75%;
  background-position: center;
}
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.search {
  display: flex;
  align-items: center;
}
.search-input {
  display: none;
  border: none;
  border-bottom: 1px solid $color-green;
}
.search-start {
  display: block;
}
.twitter {
  margin: 0 8px;
}
.follow {
  border: 1px solid $color-green;
  padding: 1px 10px;
  border-radius: 4px;
  text-decoration: none;
  color: $color-green;
}
hr {
  margin: 5px 0;
  border-color: $hr;
}
.nuxtImg {
  background: url("https://cdn-images-1.medium.com/max/1250/1*BkRCeibWDrtp2-K3f28q_g.jpeg");
  width: 655px;
  height: 350px;
  margin: 0 13px;
  background-size: cover;
  background-position: 50% 50%;
}
.big-content {
  display: flex;
  justify-content: space-around;
  margin: 30px 0;
}
.bigContent {
  width: 320px;
}
.bigContent-title {
  line-height: 1.3;
  font-size: $title-size;
  font-family: fantasy;
}
.bigContent-p {
  line-height: 1.2;
}
.home {
  max-width: 1000px;
  margin: 0 auto;
}
.content {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.card {
  width: 315px;
}
.card-title {
  font-size: $size-small-title;
  font-family: "Lucida Grande", "Lucida Sans Unicode", "Lucida Sans", Geneva,
    Arial, sans-serif;
}
.auother {
  display: flex;
}
.auother-introduce {
  margin-left: 10px;
}
.auother-name {
  color: $color-green;
}
.person-face {
  width: 36px;
  height: 36px;
  border-radius: 100%;
}
.tooltip-position {
  position: relative;
  top: -130px;
  right: 70px;
}
.tooltip {
  visibility: hidden;
}
.tooltip-hover:hover .tooltip {
  visibility: visible;
}
.follow-button {
  padding: 0 5px;
  text-decoration: none;
  border-radius: 4px;
  border: 1px solid $color-green;
  color: $color-green;
  font-family: medium-content-sans-serif-font, -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue",
    sans-serif;
}
</style>