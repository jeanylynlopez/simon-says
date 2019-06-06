<template>
  <div class="container">

    <!-- the four buttons -->
    <div v-for="(button, index) in buttons" 
      :key="index"
      :class="`button ${button}`"></div>

  </div>
</template>

<script>

// NOTES
// We need to randomize the buttons that simon chooses 
// Should the buttons be produced as a v-for from an array or object in data 
// Store those randomized buttons into a variable in data
// Show the user which buttons 
// Let the user click the button 
// On click on each of the buttons 
// when it is clicked the function will add to a data variable 
// 

export default {
  name: 'SimonSays',
  props: {
    msg: String
  }, 
  data: function(){
    return {
      buttons: ["green", "red", "yellow", "blue"],
      simonPicks: [],
      userPicks: []
    }
  },
  created: function() {
    let min = Math.ceil(1);
    let max = Math.floor(5);
    let randomNum = Math.floor(Math.random() * (max - min)) + min;
    this.simonPicks.push(randomNum);
    console.log(this.simonPicks)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

  @import "@/styles/_variables.scss";

  .container {
    display: flex;
    justify-content: center;
  }
  
  // button styles
  .button {
    width: 200px;
    height: 200px;
    margin: 10px 5px;
    // background: black;
  }

  .green {
    background-color: $green;
  }

  .red {
    background-color: $red;
  }

  .yellow {
    background-color: $yellow;
  }

  .blue {
    background-color: $blue;
  }

</style>
