<template>
  <div class="hello">
    <a href="#" @click.prevent="signout">登出</a>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    signout() {
      const api = `${process.env.APIPATH}/logout`;
      this.axios.post(api).then((response) => {
          console.log('data', response.data);
          if(response.data.success) {
              this.$router.push('/login');
          }
      });
    }
  },
}
</script>
<style scoped>
</style>
