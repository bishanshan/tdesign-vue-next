<template>
  <div style="width: 100%">
    <t-tag-input v-model="tags" placeholder="最多只能输入 3 个标签" :max="3" @enter="onEnter" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import { MessagePlugin } from 'tdesign-vue-next';

export default defineComponent({
  name: 'TTagInputMax',
  setup() {
    const tags = ref([]);
    const onEnter = (value, { inputValue }) => {
      if (value.length >= 3 && inputValue) {
        MessagePlugin.warning('最多只能输入 3 个标签!');
      }
    };
    return { tags, onEnter };
  },
});
</script>
