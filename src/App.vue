<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  created() {
    const api = `${process.env.APIPATH}/api/${process.env.CUSTOMPATH}/products`;
    fetch(api)
      .then(res => res.json())
      .then(data => {
        console.log(data);
      });
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
