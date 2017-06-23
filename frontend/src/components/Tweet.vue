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
        <li><icon class="button" name="reply"/></li>
        <li>
          <a @click="retweet(tweet.id)">
            <span> {{tweet.retweeters.length}} </span>
            <icon class ="button" name="retweet"/>
          </a>
        </li>
        <li><icon class ="button" name="heart"/></li>
        <li><icon class ="button" name="envelope"/></li>
      </ul>
    </div>
  </div>
</template>

<script>

import 'vue-awesome/icons'
import Icon from 'vue-awesome/components/Icon'
import moment from 'moment'

export default {
  created () {
    moment.locale('fr')
  },
  name: 'tweet',
  props: ['tweet'],
  components: {Icon},
  methods: {
    moment: function (date) {
      return moment(date)
    },
    retweet: function (id) {
      var data = new FormData()
      data.append('utilisateur', 'olivvvvv')
      data.append('tweet', id)
      this.$http.post('http://localhost:8080/retweet', data, {responseType: 'text'}).then(response => {
      })
    }
  }
}
</script>

<style scoped>

  li{
   display: inline-block;
  }

  a {
   color: #42b983;
  }

  span.handle {
   color: gray;
  }
</style>
