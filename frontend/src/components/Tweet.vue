<template>
  <div class="tweet">
    <div>
      <strong>{{ tweet.auteur.prenom }} {{ tweet.auteur.nom }}</strong> <span class="handle">@{{ tweet.auteur.handle }}</span>
    </div>
    <div>
      {{ tweet.contenu }}
    </div>
    <div>
      <ul>
        <li><icon name="reply"/></li>
        <li><icon name="retweet"/></li>
        <li><icon name="heart"/></li>
        <li><icon name="envelope"/></li>
      </ul>
    </div>
  </div>
</template>

<script>
import 'vue-awesome/icons'
import Icon from 'vue-awesome/components/Icon'
export default {
  components: {Icon},
  name: 'tweet',
  props: ['tweet']
}
</script>

<style scoped>
  li {
   display: inline-block;
  }

  a {
   color: #42b983;
  }

  span.handle {
   color: gray;
  }
</style>
