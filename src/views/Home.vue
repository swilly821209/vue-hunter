<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <TheCard v-for="(item,key) in list" :item="item" :key="key">
      <template #header>
        <img :src="item.src" alt>
      </template>
      <template #body>
        <div>
          <h4>{{ item.title }}</h4>
          <p>{{ item.content }}</p>
        </div>
      </template>
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
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title: "hellow"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title: "hellow"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title: "hellow"
        },
        {
          src:
            "https://cdn-images-1.medium.com/max/500/1*BkRCeibWDrtp2-K3f28q_g.jpeg",
          title: "hellow"
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
