<template>
  <div id="app">
    <section class="list">
      <IpsumList
        v-bind:selected="selected"
        v-on:select="updateSelected"
      />
    </section>
    <section class="viewer">
      <IpsumViewer
      :ipsum="selected"
      />
    </section>
  </div>
</template>

<script>
import IpsumList from './components/IpsumList.vue'
import IpsumViewer from './components/IpsumViewer.vue'

export default {
  name: 'app',
  data() {
    return {
      selected:null,
    }
  },
  components: {
    IpsumList,
    IpsumViewer,
  },
  methods: {
    updateSelected(ipsum) {
      this.selected = ipsum;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  display: grid;
  grid-template-rows: 20% 20% 20% 20% 20% ;
  grid-template-columns: 20% 70% 10%;
}

#list {
  width: 300px;
  grid-area: 1 / 1 / 6 / 1;
}

#viewer {
  grid-area: 1 / 2 / 6 / 6;
}

</style>
