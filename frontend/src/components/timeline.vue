<template>
  <div class="timeline">
    <h1>{{msg}}</h1>
    <ul>
           <li v-for="tweet in tweets">
                {{ tweet.auteur}} : {{ tweet.contenu}}
           </li>
    </ul>


   </div>
</template>

<script>
var tweet1 = {auteur: 'one punch', contenu: 'blabla bla'}
var tweet2 = {auteur: 'Pauloooo', contenu: 'blobloblo'}
var tweet3 = {auteur: 'Oliv', contenu: 'bliblibli'}


export default {
  name: 'timeline',
  data () {
    return {
      tweets: [tweet1, tweet2, tweet3]
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
