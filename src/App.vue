<template>
  <div id="app">
    <div id="minder-container">

    </div>
  </div>
</template>
<script>
// @ is an alias to /src
export default {
  mounted () {
    this.km = new window.kityminder.Minder({
      renderTo: '#minder-container'
    })
    this.km.importJson({
      root: {
        data: {
          text: 'test111'
        },
        children: [
          { data: { text: '新闻\nsrc/module/node.j' } },
          { data: { text: '网页' } },
          { data: { text: '贴吧' } },
          { data: { text: '知道' } },
          { data: { text: '音乐' } },
          {
            data: {
              text: '图片'
            },
            children: [
              {
                data: {
                  text: 'abc'
                }
              }
            ]
          },
          { data: { text: '视频' } },
          { data: { text: '地图' } },
          { data: { text: '百科', expandState: 'collapse' } }
        ]
      },
      template: 'default'
    })

    window.km = this.km
  }
}
</script>
<style lang="stylus" scoped>
#app
  font-family Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  margin-top 10px
  height 800px

#minder-container{
  width 100%
  height 100%
}
</style>
