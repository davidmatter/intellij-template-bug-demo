<template>
  <div id="app">
    {{ a }}
    {{ b.c }}
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from "@vue/composition-api";

export default defineComponent({
  name: "App",
  setup() {
    return {
      a: ref(3), // works in Template: Ref<UnwrapRef<number>>
      b: computed(() => { // Doesn't workm in Template: ComputedRef<{c: number}>
        return {
          c: 2
        }
      })
    }
  }
});
</script>