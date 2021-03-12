<script>
export default {
  name: 'BmiCalculator',
  
  data() {
    return {
      mass: '',
      height: '',
      feet: '',
      inc: '',
      result: '',

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
      if(this.metric.select){
        console.log(this.metric.mass)
        this.result = "Normal"
      }else{
        console.log(this.us.mass)
      }
    },

    selectMetric() {
      this.metric.select = !this.metric.select
      this.us.select = false
      this.result = ''
    },

    selectUs() {
      this.us.select = !this.us.select
      this.metric.select = false
      this.result = ''
    },
  }
}
</script>

<template>
  <section class="container">
    <div class="options">
      <button @click="selectMetric">Metric</button>
      <button @click="selectUs">US/UK Units</button>
    </div>
    

    <form v-if="metric.select">
      <label>Weight ( kg )</label>
      <input type="number" v-model="mass" :placeholder="metric.mass">
      <label>Height ( cm )</label>
      <input type="number" v-model="height" :placeholder="metric.height">
      <button @click.prevent="calculateBmi">Calculate</button>
    </form>

    <form v-if="us.select">
      <label>Weight ( pound )</label>
      <input type="number" v-model="mass" :placeholder="us.mass">
      <label>Height ( feet.inc )</label>
      <input type="number" v-model="feet" placeholder="feet">
      <input type="number" v-model="inc" placeholder="inc">
      <button @click.prevent="calculateBmi">Calculate</button>
    </form>
    
    <h1> {{ result }}</h1>
  </section>
</template>


<style scoped>
html,* {
  font-size: x-large;
}

.container {
  display: flex;
  width: 60vh;
  margin: 0 auto;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 10vh;
  border-radius: 2vh;
  background: rgb(233,121,127);
background: linear-gradient(119deg, rgba(233,121,127,0.19371498599439774) 31%, rgba(191,90,193,0.16850490196078427) 70%);
}

.options {
  margin: 0 auto;
  width: 50vh;
  display: flex;
  justify-content: space-around;
}

button{
  height: 10vh;
  width: 18vh;
  border-radius: 1vh;
  font-size: 3vh;
  font-weight: 400;
}

button:focus {
  color: rgb(0, 255, 149);
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 5vh;
}
</style>
