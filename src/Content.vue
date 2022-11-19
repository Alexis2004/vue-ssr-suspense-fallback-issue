<template>
  <div>
    I'm content!
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Content',
  async setup() {
    await new Promise((resolve) => {
      setTimeout(() => resolve(undefined), 2000);
    });

    return {
    };
  },
});
</script>
