<template>
   <div>
      Parameters:
      <div v-for="item in item.Parameter" class="code" :key="item.$.Name">{{ item.$.Name }}</div>Return type:
      <div v-for="item in item.ReturnType" class="code" :key="item.$.Type">{{ item.$.Type }}</div>
   </div>
</template>

<script>
export default {
   props: ["item"]
};
</script>

<style>
</style>
