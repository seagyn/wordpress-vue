<template>
    <div class="sponsors">
        <div class="columns">
            <div class="column">
                <h1 class="is-size-1">Sponsors</h1>
            </div>
            <div class="column has-text-right">
                <a class="button is-info" v-on:click="filterSponsors('all')">All</a>
                <a class="button is-info" v-for="sponsorLevel in sponsorLevels" v-bind:key="sponsorLevel.id" v-on:click="filterSponsors(sponsorLevel.id)">{{sponsorLevel.name}}</a>
            </div>
        </div>
        <div class="columns is-multiline">
            <div class="column is-one-quarter" v-for="sponsor in filteredSponsors" v-bind:key="sponsor.id">
                <img :src="sponsor._embedded['wp:featuredmedia'][0].source_url" :alt="`Sponsor: ${sponsor.title.rendered}`">
                <h3 class="is-size-3">{{sponsor.title.rendered}}</h3>
            </div>
        </div>
    </div>
</template>

<script>
  import axios from 'axios'
  export default {
    component: 'Sponsors',
    data: function () {
      return {
        sponsors: [],
        sponsorLevels: [],
        currentSponsorLevel: 'all'
      }
    },
    computed: {
      filteredSponsors: {
        get: function () {
          return this.sponsors.filter(sponsor => {
            if (this.currentSponsorLevel === 'all') {
              return sponsor
            } else {
              return sponsor.sponsor_level.includes(this.currentSponsorLevel) && sponsor
            }
          })
        },
        set: function (sponsorLevel) {
          this.currentSponsorLevel = sponsorLevel
        }
      }
    },
    methods: {
      filterSponsors: function (sponsorLevel) {
        this.filteredSponsors = sponsorLevel
      }
    },
    created: function () {
      axios.get('https://2018.johannesburg.wordcamp.org/wp-json/wp/v2/sponsors?order=asc&orderby=title&per_page=20&_embed')
        .then(response => {
          this.sponsors = response.data
        })
      axios.get('https://2018.johannesburg.wordcamp.org/wp-json/wp/v2/sponsor_level?order=desc')
        .then(response => {
          this.sponsorLevels = response.data
        })
    }
  }
</script>
