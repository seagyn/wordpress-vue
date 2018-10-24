<template>
    <div class="column is-one-third">
        <div class="box">
            <article class="media">
                <div class="media-left">
                    <figure class="image is-64x64">
                        <img :src="speaker.avatar_urls['96']" :alt="`WordCamp Speaker: ${speaker.title.rendered}`">
                    </figure>
                </div>
                <div class="media-content">
                    <div class="content">
                        <h3 class="is-size-3">{{ speaker.title.rendered }}</h3>
                        <div v-html="speaker.excerpt"></div>
                    </div>
                </div>
            </article>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Speaker',
  props: {
    speaker: Object
  }
}
</script>

<style scoped>

</style>
