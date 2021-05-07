<template>
  <div>
      izle ve öğren
      <button @click="onClick">Tıkla</button>
  </div>
</template>

<script>
export default {
  async setup() {
    const user = await getData();
    return { user };
  },
};
</script>

<style>

</style>
