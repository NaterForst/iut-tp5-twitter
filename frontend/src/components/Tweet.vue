<template>
  <div class="tweet">
    <div>
      <strong>{{ tweet.auteur.prenom }} {{ tweet.auteur.nom }}</strong> <span class="handle">@{{ tweet.auteur.handle }} - {{moment(tweet.date).fromNow()}} </span>
    </div>
    <div>
      {{ tweet.contenu }}
    </div>
    <div>
      <ul>
        <li><icon class ="button" name="reply"/></li>
        <li><icon class ="button" name="retweet"/></li>
        <li><icon class ="button" name="heart"/></li>
        <li><icon class ="button" name="envelope"/></li>
      </ul>
    </div>
  </div>
</template>

<script>
import 'vue-awesome/icons'
import moment from 'moment'
import Icon from 'vue-awesome/components/Icon'
export default {
  components: {Icon},
  name: 'tweet',
  props: ['tweet'],
  methods: {
    moment: function (date) {
      return moment(date)
    }
  },

  created () {
    moment.locale('fr')
  }
}

</script>
</script>

<style scoped>
  li.button{
   display: inline-block;
  }

  a {
   color: #42b983;
  }

  span.handle {
   color: gray;
  }
</style>
