<template>
  <div v-if="error">
   {{ error }}
  </div>
  <Suspense v-else>
    <template #default>
      <LifeCycle />
    </template>
    <template #fallback>
      <div>Loading...</div>
    </template>
  </Suspense>
</template>

<script>
import {
  ref, onMounted, onUpdated, onUnmounted, onBeforeMount, onBeforeUnmount,
  onErrorCaptured, onRenderTracked, onRenderTriggered,
} from 'vue';

import LifeCycle from '../../components/lesson-1/LifeCycle.vue';

export default {
  components: { LifeCycle },
  setup() {
    const error = ref(null);
    /*
      beforeCreate -> use setup()
      created -> use setup()
      beforeMount -> onBeforeMount
      mounted -> onMounted
      beforeUpdate -> onBeforeUpdate
      updated -> onUpdated
      beforeUnmount -> onBeforeUnmount
      unmounted -> onUnmounted
      errorCaptured -> onErrorCaptured
      renderTracked -> onRenderTracked
      renderTriggered -> onRenderTriggered
    */
    console.log('beforeCreate & Created');

    onBeforeMount(() => {
      console.log('onBeforeMount!');
    });
    onMounted(() => {
      console.log('mounted!');
    });
    onUpdated(() => {
      console.log('updated!');
    });
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount!');
    });
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount!');
    });
    onUnmounted(() => {
      console.log('unmounted!');
    });
    onErrorCaptured((e) => {
      console.log('onErrorCaptured!');
      error.value = e;
      return true;
    });
    onRenderTracked(() => {
      console.log('onRenderTracked!');
    });
    onRenderTriggered(() => {
      console.log('onRenderTriggered!');
    });
    return { error };
  },

};
</script>

<style>

</style>
