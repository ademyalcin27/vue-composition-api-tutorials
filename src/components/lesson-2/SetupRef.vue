<template>
  <div ref="element">{{text}}</div>
  <button @click="changeText">Tıkla</button>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const text = ref('izleveogren');
    const element = ref(null);
    const changeText = () => {
      console.log(text);
      text.value = 'izle ve ogren Vue Js';
      element.value.classList.add('bold');
    };
    return {
      text,
      changeText,
      element,
    };
  },
};
</script>

<style>

</style>
