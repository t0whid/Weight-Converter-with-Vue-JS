<template>
  <div>
    <form>
      <label>Weight in KG : </label>
      <input v-model.number="weightInKg" />
    </form>
    <p v-if="this.weightInKg !==''">Weight in Pounds: {{ weightInLb }}</p>

    <hr>

    <form>
      <label>Temperature in Celcius : </label>
      <input v-model.number="tempCelcius" />
    </form>
    <p v-if="this.tempCelcius !==''">Temperature in Kelvin: {{tempKelvin}}</p>
    <p v-if="this.tempCelcius !==''">Temperature in Farenheit: {{tempFarenheit}}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      weightInKg: '',
      tempCelcius: '',
    };
  },
  computed: {
    weightInLb() {
      return this.weightInKg * 2.205;
      
    },
    tempKelvin () {
      return this.tempCelcius + 273.15;
    },
    tempFarenheit() {
      return ( this.tempCelcius* 9/5 + 32);
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
