<template>
  <div class="container">
    <div class="principal-title">
      {{titleText}}
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
  data() {
    return {
      titleText: '',
      index: 0
    }
  },
  created() {
    this.callToAddTitlle()
  },

  methods: {
    callToAddTitlle() {
      setInterval(() => {
        this.teleType()
      }, 100)
    },

    teleType() {
      let title = "Aqui é um texto muito bacana"
      let bTitle = "⠏⠗⠕⠚⠑⠞⠕⠀⠏⠗⠊⠝⠞⠤⠙⠕⠞⠎"
      bTitle = bTitle.split("")
      title = title.split("")

      if (!(this.index > bTitle.length - 1)) {
        this.titleText += bTitle[this.index]
        this.index++
      }
      return
    }
  }
}
</script>
<style>
.principal-title {
  font-size: 20px;
  color: black;
  font-weight: bold;
}
</style>
