<template>
  <div class="hero-body">
    <div class="container">
      <div class="principal-title">
        <h1 v-if="!view" class="principal-title-dot title is-1">{{titleText}}</h1>
        <h1 v-else class="principal-title-text title is-1" >{{title}}</h1>
        <h2 v-if="view" class="principal-title-subtitle subtitle">
          Uma impressora de Braille de baixo custo, acessivel a todos!
        </h2>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Header",
  data() {
    return {
      title: 'Projeto Print-Dots',
      titleText: '',
      index: 0,
      view: false
    }
  },
  created() {
    this.callToAddTitlle()
  },

  methods: {
    callToAddTitlle() {
      setInterval(() => {
        this.teleType()
      }, 200)
    },

    teleType() {
      let bTitle = "⠏⠗⠕⠚⠑⠞⠕⠀⠏⠗⠊⠝⠞⠤⠙⠕⠞⠎"
      bTitle = bTitle.split("")

      if (!(this.index > bTitle.length - 1)) {
        this.titleText += bTitle[this.index]
        this.index++
      }
      if(this.index >=18) {
        setTimeout(() => {
          this.view = true
        }, 1800);
      }
      return
    }
  }
}
</script>
<style>
.principal-title {
  text-align: center;
  color: black;
  font-weight: bold;
}

.title.is-1 {
  font-size: 4rem;
}

.principal-title-dot {
  animation: fade-out ease-out;
  animation-duration: .3s;
  animation-delay: 5.16s;
}

.principal-title-text {
  animation: fade-in ease-in;
  animation-duration: 1.8s;
}

.principal-title .principal-title-subtitle {
  animation: fade-in;
  animation-duration: 3s;
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }
  25% {
    opacity: 0.2;
  }
  50% {
    opacity: 0.5;
  }
  75% {
    opacity: 0.75;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fade-out {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    opacity: 0;
  }
}
</style>
