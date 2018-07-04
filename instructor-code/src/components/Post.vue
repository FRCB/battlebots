<template>
    <div>
      <p class='color'>
          Author: {{postProp.author}}
      <p>
      <p>{{postProp.post}}</p>
      <hr>
    </div>
</template>

<script>
export default {
  props: ['postProp', 'myName']
};
</script>

<style scoped>
</style>