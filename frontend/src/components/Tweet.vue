<template>
  <div>
    {{tweet.auteur}} : {{tweet.contenu}}
  </div>
</template>

<script>

  export default {
    name: 'tweet',
    props: ['tweet']
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

li.button {
 display: inline-block;
}

a {
 color: #42b983;
}

span.handle {
 color: gray;
}

</style>

