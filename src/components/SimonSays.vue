<template>
  <div class="container">
    <section>
      <div class="button green">Green</div>
      <div class="button red">Red</div>
    </section>  
    <section>
      <div class="button yellow">Yellow</div>
      <div class="button blue">Blue</div>
    </section>
  </div>
</template>

<script>

// NOTES
// We need to randomize the buttons that simon chooses 
// Store those randomized buttons into a variable in data
// Show the user which buttons 
// on click on each of the buttons 
// when it is clicked the function will add to a data variable 
// 

export default {
  name: 'SimonSays',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

  @import "@/styles/_variables.scss";

  .container {
    display: flex;
    margin: 0 auto;
    justify-content: center;
  }
  
  // button styles
  .button {
    width: 200px;
    height: 200px;
    margin: 10px 5px;
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
