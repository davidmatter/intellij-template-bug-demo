<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    {{ a }}
    {{ b.c }}
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "@vue/composition-api";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

export default defineComponent({
  name: "Home",
  components: {
    HelloWorld,
  },
  setup() {
    return {
      a: ref(3),
      b: computed(() => {
        return {
          c: 2
        }
      })
    }
  }
});
</script>
