<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <TheCard v-for="(item,key) in list" :item="item" :key="key">
      <img :src="item.src" alt>
    </TheCard>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import TheCard from "@/components/TheCard";
import "@/assets/reset.css";

export default {
  name: "home",
  data() {
    return {
      list: [
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg"
        }
      ]
    };
  },
  components: {
    HelloWorld,
    TheCard
  }
};
</script>
