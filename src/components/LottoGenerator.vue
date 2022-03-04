<template>
  <div class="container">
      <img src="../assets/pcso.png" alt="pcso-logo">
      <h1>My Lotto Generator</h1>
  </div>
  <button @click="generate()">Generate Numbers</button>
  <div class="container">
      <div class="output" v-for="digit in randomDigits" :key="digit">
          {{ digit }}
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        generate(){

            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41)) + 1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
        }
    }

}
</script>

<style scope>
.container{
    display: flex;
    align-items: center;
    justify-content: center;
    
}
img {
 height: 60px;
 padding: 5px;
}

button{
    margin-bottom: 10px;
}

.output {
    padding: 5px;
    font-weight: bold;
}
</style>