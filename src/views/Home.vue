<template>
  <div class="home">
    <div class="metabar">
      <img 
        class="logo" 
        src="@/assets/mIcon.svg" 
        alt="Mastery"
       />
      <div class="button-set">
        <a 
         href="#" 
         class="sign-in">
          Sign in
        </a>
        <a 
         href="#" 
         class="started"
        >
         Get started
        </a>
      </div>
    </div>
    <div class="header">
      <div class="big-logo"></div>
      <div class="navbar">
        <div class="search">
          <img 
            src="@/assets/search.svg" 
            class="search-icon" 
            @click="start"
           />
          <input
            type="text"
            class="search-input"
            placeholder="Search Vue Mastery"
            :class="{ 'search-start' : toggle }"
           />
          <a 
           href="#" 
           class="twitter" 
           title="Visit “Vue Mastery” on Twitter"
          >
            <img src="@/assets/twitter.svg" />
          </a>
          <a 
           href="#" 
           class="facebook" 
           title="Visit “Vue Mastery” on Facebook"
          >
            <img src="@/assets/facebook.svg" />
          </a>
        </div>
        <a 
         href="#" 
         class="follow"
        >
        Follow
        </a>
      </div>
      <hr>
    </div>
    <div class="big-content">
      <div 
        class="big-content-img" 
        :style="{ backgroundImage: `url('${newData.bigImg}')` }"
      >
      </div>
      <div class="new-content">
        <h3 class="new-content-title">{{newData.bigTitle }}</h3>
        <p class="new-content-paragraph">{{ newData.bigContent }}</p>
        <div class="tooltip-hover">
          <div class="tooltip-position">
            <TheCardTooltip class="tooltip">
              <template #tooltip-author>
                <div>{{ newData.name }}</div>
              </template>
              <template #tooltip-img>
                <div>
                  <img 
                    :src="newData.personFace" 
                    class="person-face"
                   />
                </div>
              </template>
              <template #tooltip-fan>
                <div>Followed by {{ newData.fan }} people</div>
              </template>
              <template #tooltip-button>
                <div>
                  <a 
                   href="#" 
                   class="follow-button" 
                   @click.prevent="increase('newCard',key)"
                  >
                   Follow
                  </a>
                </div>
              </template>
            </TheCardTooltip>
          </div>
          <div class="auother">
            <img 
              :src="newData.personFace" 
              class="person-face"
             />
            <div class="auother-introduce">
              <h5 class="auother-name">{{ newData.name }}</h5>
              <p>{{ newData.time }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="content">
      <TheCard 
        v-for="(item,key) in list" 
        :item="item" :key="key" 
        class="card"
      >
        <template #cardHeader>
          <div 
            class="card-img" 
            :style="{ backgroundImage: `url('${item.src}')` }"
          >
          </div>
        </template>
        <template #cardBody>
          <div>
            <h4 class="card-title">{{ item.title }}</h4>
            <p class="card-paragraph">{{ item.content }}</p>
          </div>
        </template>
        <template #cardFoot>
          <div class="tooltip-hover">
            <div class="tooltip-position">
              <TheCardTooltip class="tooltip">
                <template #tooltip-author>
                  <div>{{ item.name }}</div>
                </template>
                <template #tooltip-img>
                  <div>
                    <img 
                      :src="item.personFace" 
                      class="person-face"
                    >
                  </div>
                </template>
                <template #tooltip-fan>
                  <div>Followed by {{ item.fan }} people</div>
                </template>
                <template #tooltip-button>
                  <div>
                    <a 
                      href="#" 
                      class="follow-button" 
                      @click.prevent="increase('card',key)"
                    >
                      Follow
                    </a>
                  </div>
                </template>
              </TheCardTooltip>
            </div>
            <div class="auother">
              <img 
                :src="item.personFace" 
                class="person-face"
               />
              <div class="auother-introduce">
                <h5 class="auother-name">{{ item.name }}</h5>
                <p>{{ item.time }}</p>
              </div>
            </div>
          </div>
        </template>
      </TheCard>
    </div>
    <hr>
    <div class="footer">
      <a 
      
       href="#" 
       class="footer-link" 
       title="About Vue Mastery"
      >
        About Vue Mastery
      </a>
      <span class="footer-space"></span>
      <a 

       href="#" 
       class="footer-link" 
       title="Latest Stories for Vue Mastery"
      >
        Latest Stories
      </a>
      <span class="footer-space"></span>
      <a

       href="#" 
       class="footer-link" 
       title="Archive for Vue Mastery"
      >
        Archive
      </a>
      <span class="footer-space"></span>
      <a

       href="#" 
       class="footer-link"
      >
        About Medium
      </a>
      <span class="footer-space"></span>
      <a

       href="#" 
       class="footer-link"
      >
        Terms
      </a>
      <span class="footer-space"></span>
      <a 

       href="#" 
       class="footer-link"
      >
        Privacy
      </a>
    </div>
  </div>
</template>
<script>
// @ is an alias to /src
import TheCard from "@/components/TheCard";
import TheCardTooltip from "@/components/TheCardTooltip";

export default {
  name: "home",
  components: {
    TheCard,
    TheCardTooltip
  },
  data() {
    return {
      newData: {
        bigTitle: "Announcing Vue Mastery Free Weekend",
        bigContent:
          "Next weekend (Feb 22–24) all courses on Vue Mastery will be completely free. Reserve your spot for free learning right now.",
        bigImg:
          "https://cdn-images-1.medium.com/max/1250/1*xnHSuu64Q5XKU8Uy5OqQbg.jpeg",
        personFace:
          "https://cdn-images-1.medium.com/fit/c/45/45/0*Ahh8dr_2DEFlPo4b.",
        name: "Gregg Pollack",
        time: "Jan 29",
        fan: 123
      },
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
            "https://cdn-images-1.medium.com/max/500/1*bqG3RoXHBpwyhrb3g2_STQ.jpeg",
          title: "10 Vue.js Pro Tips from  Vue Masters",
          content:
            "If you want to become a master of your craft you’ll need to learn from the best. We’ve gathered ten Pro Tips from six Vue masters…",
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
    },
    increase(status, key) {
      if (status == "card") {
        console.log(this.list.key);
        this.list[key].fan++;
      }
      if (status == "newCard") {
        this.newData.fan++;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
$color-black: rgba(0, 0, 0, 0.15);
$color-gray: rgba(0, 0, 0, 0.54);
$color-green: #42b983;
$color-darkblack: #000;
$size-small-title: 26px;
$size-small-content: 20px;
$size-title: 38px;
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
.sign-in {
  margin-right: 16px;
  text-decoration: none;
  color: $color-green;
}
.started {
  padding: 5px 16px;
  border: 1px solid $color-green;
  border-radius: 4px;
  text-decoration: none;
  color: $color-green;
}
.header {
  padding: 0 20px;
  margin-bottom: 5px;
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
  padding: 1px 10px;
  border: 1px solid $color-green;
  border-radius: 4px;
  text-decoration: none;
  color: $color-green;
}
hr {
  margin: 5px 0;
  border-color: $hr;
}
.big-content-img {
  width: 670px;
  height: 350px;
  border: 1px solid $color-black;
  background-size: cover;
  background-position: 50% 50%;
}
.big-content {
  display: flex;
  justify-content: space-around;
  margin: 30px 0;
}
.new-content {
  max-width: 320px;
}
@media (max-width: 768px) {
  .big-content {
    flex-wrap: wrap;
  }
  .new-content {
    max-width: 768px;
    margin: 20px;
  }
}
.new-content-title {
  line-height: 1.1;
  font-size: $size-title;
  font-family: fantasy;
}
.new-content-paragraph {
  line-height: 1.2;
  font-size: $size-small-content;
  color: $color-gray;
}
.home {
  max-width: 1056px;
  margin: 0 auto;
}
.content {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.card {
  width: 326px;
}
.card-img {
  width: 100%;
  height: 172px;
  border: 1px solid $color-black;
  background-repeat: no-repeat;
  background-position: 50% 50%;
  background-size: cover;
}
.card-title {
  margin: 20px 0;
  line-height: 1.1;
  font-size: $size-small-title;
  font-family: medium-content-sans-serif-font, "Lucida Grande",
    "Lucida Sans Unicode", "Lucida Sans", Geneva, Arial, sans-serif;
}
.card-paragraph {
  margin: 15px 0;
  line-height: 1.2;
  font-size: $size-small-content;
  color: $color-gray;
}
.auother {
  display: flex;
  margin: 35px 0;
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
  top: -150px;
  right: 70px;
}
.tooltip {
  visibility: hidden;
  padding: 20px;
}
.tooltip-hover:hover .tooltip {
  visibility: visible;
}
.follow-button {
  padding: 0 5px;
  border: 1px solid $color-green;
  margin: 0 5px;
  text-decoration: none;
  border-radius: 4px;
  color: $color-green;
  font-family: medium-content-sans-serif-font, -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue",
    sans-serif;
}
.footer {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 50px;
}
.footer-link {
  display: block;
  color: $color-gray;
  text-decoration: none;
}
.footer-space::after {
  content: "\00B7";
  margin: 0 3px;
}
.footer-link:hover {
  color: $color-darkblack;
}
</style>
