<template>
  <div class="speakers">
    <div class="columns">
      <div class="column">
        <h1 class="is-size-1">Speakers</h1>
      </div>
      <div class="column has-text-right">
        <a class="button is-info" v-on:click="toggleOrder">Toggle Order</a>
      </div>
    </div>
    <div class="columns is-multiline">
      <Speaker v-for="speaker in speakers" v-bind:key="speaker.id" v-bind:speaker="speaker" />
    </div>
  </div>
</template>

<script>
import Speaker from '../components/Speaker'
import axios from 'axios'
export default {
  name: 'Speakers',
  components: { Speaker },
  methods: {
    toggleOrder: function () {
      return this.speakers.reverse()
    }
  },
  data: function () {
    return {
      speakers: []
    }
  },
  created: function () {
    axios.get('https://2018.johannesburg.wordcamp.org/wp-json/wp/v2/speakers?per_page=30&orderby=title&order=desc')
      .then(response => {
        this.speakers = response.data
      })
  }
}
</script>
