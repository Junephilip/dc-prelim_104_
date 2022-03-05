<template>
  <div class="container">
      <img src="../assets/pcso-logo.png" alt="logo">
      <h1>My Lotto Generator</h1>
  </div>
  <button @click="generateNumber()">Generate Number</button>
  <div class="container">
      <div class="results" v-for="result in resultsArray" :key="result">
          {{ result }}
      </div>
  </div>
</template>

<script>
export default {
    data(){
        resultsArray: []
    },
    methods: {
        generateNumber(){
            while(this.resultsArray.length < 6){
                let rand = Math.floor(Math.random() * 41)+1;
                if(!this.resultsArray.includes(rand)){
                    this.resultsArray.push(rand);
                }
            }
        }
    }
}
</script>

<style>

</style>