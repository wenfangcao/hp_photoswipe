<template>
  <div>
    <img @click="showPic" :src="src" alt="">
    <Pswp ref="pswp"/>
  </div>
</template>
<script>
import Pswp from './table'

export default {
  components: {
    Pswp
  },
  data () {
    return {
      src: 'http://fed.dev.hzmantu.com/oa-project/25901485a2d3fa65cef84f626615b8bc.png'
    }
  },
  methods: {
    showPic () {
      this.$refs.pswp.show([{src: this.src, w: 400, h: 200}])
    }
}
}
</script>

