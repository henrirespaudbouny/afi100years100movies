<template>
  <div id="progressBar" v-scroll="handleProgressBar">
    <div id="progression"></div>
  </div>
</template>

<script>
export default {
  name: 'progressBar',
  methods: {
    handleProgressBar () {
      var element = document.getElementById('progression')
      var currentPosition = parseInt(document.getElementById('board').style.left)
      var screenWidth = window.innerWidth
      var boardWidth = document.getElementById('board').offsetWidth - 100
      console.log(parseInt(document.getElementById('board').style.left))
      element.style.width = 100 * currentPosition / (boardWidth - screenWidth) + '%'
    }
  },
  mounted () {
    this.handleProgressBar()
  }
}
</script>

<style>
  #progressBar{
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 8px;
    background-color: #000;
  }

  #progression{
    height: inherit;
    background-color: #fff;
    transition: width 1s cubic-bezier(.39,.575,.565,1)
  }
</style>
