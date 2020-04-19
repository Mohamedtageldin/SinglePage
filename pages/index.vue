<template>
  <div class="container">
      <section>
        <youtube :video-id="videos[0]"></youtube>
        <youtube :video-id="'80LnsHSAfqQ'"></youtube>
        <youtube :video-id="'10wsbG9IsAo'"></youtube>
        <youtube :video-id="videos[1]"></youtube>
        <youtube :video-id="videos[2]"></youtube>
      </section>
  </div>
</template>

<script>
import Vue from 'vue'
import VueYouTubeEmbed from 'vue-youtube-embed'
Vue.use(VueYouTubeEmbed)

export default {
  data(){
    return{
      videos : []
    }
  },created(){
    //Two alternative ways to make the code dynamic
    let video1 ="5dVIlru5LH8"
    let video2 = this.$youtube.getIdFromURL("https://youtu.be/btw3O0zJj-Q")
    let video3 = this.$youtube.getIdFromURL("https://youtu.be/Kqig3RF6hPQ")
    this.videos.push(video1)
    this.videos.push(video2)
    this.videos.push(video3)
  },
    components: {
        Vue, VueYouTubeEmbed
    }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
