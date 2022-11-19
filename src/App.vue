<template>
  <div>
    Dynamic client only value: <strong>{{ dynamicValue }}</strong>
  </div>
  <div>
    <Suspense timeout="0">
      <template #default>
        <Content />
      </template>
      <template #fallback>
        <div>
          Content loading...
        </div>
      </template>
    </Suspense>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import Content from './Content.vue'

export default defineComponent({
  name: 'App',
  components: {
    Content,
  },
  setup() {
    const dynamicValue = ref('none');
    setTimeout(() => {
      dynamicValue.value = 'value';
    }, 500);

    return {
      dynamicValue,
    };
  }
})
</script>
