<template>
  <div>
    <h1>姓名：{{info.name}}</h1>
    <h2>年龄：{{info.age}}</h2>
    <h2>兴趣：{{info.interest}}</h2>
    <p><nuxt-link to='/'>Home</nuxt-link></p>
  </div>

</template>

<script>

  export default {
    name: "index",
    async asyncData (context) {//请求
      let {data} = await context.$axios({
        method: 'get',
        url: 'https://api.myjson.com/bins/1dkbio'
      })
      return  { info: data};
    }
  }
</script>

<style scoped>

</style>
