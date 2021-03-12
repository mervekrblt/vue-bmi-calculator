<script>
export default {
  name: 'BmiCalculator',
  
  data() {
    return {
      mass: '',
      height: '',
      feet:'',
      inc:'',

      metric: {
        mass: 'kg',
        height: 'cm',
        select: false
      },

      us: {
        mass: 'pound',
        height: 'feet',
        select: false
      },
    }
  },

  methods: {
    calculateBmi() {
      console.log(this.mass, this.height)
    },

    selectMetric() {
      this.metric.select = !this.metric.select
      this.us.select = false
    },

    selectUs() {
      this.us.select = !this.us.select
      this.metric.select = false
    },
  }
}
</script>

<template>
  <section>
    <div>
      <button @click="selectMetric">Metric</button>
      <button @click="selectUs">US/UK Units</button>
    </div>
    

    <form v-if="metric.select">
      <input type="number" v-model="mass" :placeholder="metric.mass">
      <input type="number" v-model="height" :placeholder="metric.height">
      <button @click.prevent="calculateBmi">Calculate</button>
    </form>

    <form v-if="us.select">
      <h1>merve</h1>
      <input type="number" v-model="mass" :placeholder="us.mass">
      <input type="number" v-model="feet" placeholder="feet">
      <input type="number" v-model="inc" placeholder="inc">
      <button @click.prevent="calculateBmi">Calculate</button>
    </form>
    
  </section>
</template>


<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
