<template>
  <div class="markdown">
    <div class="sideBar">
      <div class="sideBar__title">makofolio</div>
      <div class="sideBar__sns">Twitter:<a href="">@makoto</a></div>
      <div class="sideBar__sns">GitHub:<a href="">@makoto</a></div>
      <div class="sideBar__sns">Qita:<a href="">@makoto</a></div>
    </div>
    <div class="contents">
      <div v-html="compiledMarkdownText" />
    </div>
  </div>
</template>

<script>
import marked from 'marked'
import md from './portfolio.md'

export default {
  data () {
    return {
      markdownText: md.source    // sourceで Rawデータが取得できます 
    }
  },
  computed: {
    compiledMarkdownText: function () {
      return marked(this.markdownText)    // computedにする必要あるかどうかは知らん
    }
  }
}
</script>

<style lang="scss" scoped>
.markdown {
  display: flex;
  height: 100vh;
}

.sideBar {
  background-color: #6a9fb5;
  width: 18rem;
}

.sideBar__title {
  color: #fff;
  font-size: 40px;
  font-weight: bold;
  padding: 280px 20px 40px 20px;
}

.sideBar__sns {
  font-size: 16px;
  padding-left: 20px;
}

.contents {
  overflow: scroll;
  padding: 10px;
  width: 100%;
}
</style>