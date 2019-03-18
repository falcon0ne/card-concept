<template>
  <div id="app">
    <div class="card-container">
      <card class="card-item" :offer="offers[0]" />
      <card class="card-item" :offer="offers[3]" />
      <card class="card-item middle" :offer="offers[1]" />
      <card class="card-item big" :offer="offers[2]" />
    </div>
  </div>
</template>

<script>
import Card from './components/Card.vue'

const offers = [{
  name: 'Golden Gate',
  region: 'San Francisco | USA',
  price: 120,
  image: 'golden-gate.jpg'
}, {
  name: 'My Beach Resort',
  region: 'Mallorca | Spain',
  price: 99,
  image: 'malle.jpg'
}, {
  name: 'Miami Beach Club',
  region: 'Florida | USA',
  price: 299,
  image: 'landscape.jpg'
}, {
  name: 'Burj Al Arab',
  region: 'Jumeirah Beach | Dubai',
  price: 190,
  image: 'burj-al-arab.jpg'
}]

export default {
  name: 'app',
  components: {
    Card
  },
  data() {
    return {
      offers
    }
  },
  created() {
    document.title = 'Card Concept | Agentur-VIDA'
  }
}
</script>

<style lang="scss">
$main-font: 'Avenir', Helvetica, Arial, sans-serif;

body,
html {
  background: #f6f6f7;
  font-family: $main-font;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
  margin: 0;
  padding: 0;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;

  *,
  *:before,
  *:after {
    box-sizing: border-box;
  }
}

button,
input[type=button],
input[type=submit],
select {
  appearance: none;
  background: none;
  border: none;
  border-radius: 0;
  font-family: $main-font;
  font-size: 16px;
  line-height: 1;
}

h1, h2, h3, h4 {
  font-family: $main-font;
  line-height: 1.6;
  margin: 0;
  padding: 0;
}

#app {
  align-items: center;
  display: flex;
  min-height: 100vh;
  justify-content: center;
  width: 100%;
}

.card {
  &-container {
    display: grid;
    grid-template-columns: 245px 245px 1fr;
    grid-gap: 20px;
    max-width: 1000px;
    justify-items: center;
    width: 100%;
  }

  &-item {
    &.middle,
    &.big {
      width: 100%;
    }

    &.big {
      grid-column: 1 / 4;
      min-height: 475px;
    }
  }
}

.button {
  background: #ffc900;
  cursor: pointer;
  position: relative;

  &:before {
    content: ' ';
    display: block;
    padding-bottom: 100%;
  }

  svg {
    left: 50%;
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
    transition: transform 0.4s cubic-bezier(0.075, 0.82, 0.165, 1);
  }

  &:hover svg {
    transform: translate(-35%, -50%);
  }

  &.round {
    border-radius: 50%;
    height: 34px;
    margin-left: 12px;
    width: 34px;
  }
}
</style>
