<template>
  <div>
    <div class="metabar">
      <img class="logo" src="@/assets/mIcon.svg" alt="Mastery" />
      <div class="button-set">
        <a href="#" class="sign-in">
          Sign in
        </a>
        <a href="#" class="started">
          Get started
        </a>
      </div>
    </div>
    <div class="header">
      <div class="big-logo"></div>
      <div class="navbar">
        <div class="search">
          <img src="@/assets/search.svg" class="search-icon" @click="start" />
          <input
            type="text"
            class="search-input"
            placeholder="Search Vue Mastery"
            :class="{ 'search-start': toggle }"
          />
          <a href="#" class="twitter" title="Visit “Vue Mastery” on Twitter">
            <img src="@/assets/twitter.svg" />
          </a>
          <a href="#" class="facebook" title="Visit “Vue Mastery” on Facebook">
            <img src="@/assets/facebook.svg" />
          </a>
        </div>
        <a href="#" class="follow">
          Follow
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "TheHeader",
  data() {
      return{
           toggle: false,
      }
  },
  methods: {
    start() {
      this.toggle = !this.toggle;
    },
  }
};
</script>
<style lang="scss">
$color-green: #42b983;
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
</style>