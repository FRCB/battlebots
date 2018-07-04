<template>
    <div>
        <p class='color'>
            Author: {{postProp.author}}
        </p>
        <p>{{postProp.post}}</p>
        <hr>
  </div>
</template>

<script>
export default {
  props: ["postProp"]
};
</script>

<style scoped>
</style>
