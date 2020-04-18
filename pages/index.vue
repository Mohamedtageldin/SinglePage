<template>
  <div class="container">
    <div id="video">
      <section>
        <youtube :video-id="'zmj3AEmb9Do'"></youtube>
      </section>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import VueYouTubeEmbed from 'vue-youtube-embed'
Vue.use(VueYouTubeEmbed)

const app = new Vue({
  el: '#video',
  render: function(createElement) {
        return createElement(app)
    },
  data: {
    videoId: 'zmj3AEmb9Do'
  },
  methods: {
    ready (event) {
      this.player = event.target
    },
    playing (event) {
      console.log('We Now playing a video')
    }
  }
})
export default {
  //runtimeCompiler: true,
  app,
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
