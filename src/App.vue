<template>
  <div id="app">
    <div class="wrapper">
      <app-grid :items="items"/>
    </div>
  </div>
</template>

<script>
import Grid from './components/Grid.vue';

export default {
  name: 'app',
  data() {
    return {
      items: [
        {
          id: 1,
          animal: 'cat',
          description: 'Common, yet regarded by many as the worst house pet.',
          prosncons: ['scratches everything', 'easily lost for days', 'kind of bummer'],
          price: 'free'
        },

        {
          id: 2,
          animal: 'dog',
          description: 'Loving, gentle and caring. Dogs are the best house pet to have and will increase hapiness ten fold.',
          prosncons: ['super fun', 'friends love them', 'plays games', 'not a cat'],
          price: 90
        },

        {
          id: 3,
          animal: 'fish',
          description: 'Cheap n\' easy',
          prosncons: ['eats flakes', 'cop out', 'replaceable'],
          price: 3
        },
      ]
    }
  },

  components: {
    'app-grid': Grid,
  },
};
</script>

<style lang="scss">
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.wrapper {
  max-width: 750px;
  height: 100%;
  margin: auto;
  background-image: linear-gradient(to bottom right, #f6a737, #af64dd);
}
</style>
