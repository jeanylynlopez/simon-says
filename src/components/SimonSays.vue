<template>
  <div class="container">

    <!-- the four buttons -->
    <!-- <div v-for="(button, index) in buttons" 
      :key="index"
      :click="userInput(index)"
      :class="`button ${button}`"></div> -->
    <section>
      <div class="button green" @click="userInput(1)"></div>
      <div class="button red" @click="userInput(3)"></div>
    </section>
    <section>
      <div class="button yellow" @click="userInput(2)"></div>
      <div class="button blue" @click="userInput(4)"></div>
    </section>
  </div>
</template>

<script>

// NOTES
// [X] We need to randomize the buttons that simon chooses 
// [?] Should the buttons be produced as a v-for from an array or object in data 
// [ ] Store those randomized buttons into a variable simonPicks in data
// [ ] Show the user which button Simon decided on 
// [ ] Let the user click the button 
// [ ] When it is clicked the function will add to a userPicks data variable 
// [ ] This needs to be reset every time 
// [ ] Compare what Simon picks and what the user picks 
// [ ] If user gets it wrong, console.log wrong 
// [ ] If user gets it right add to the array 

// QUESTIONS
// How do you repeat the process over and over again? 
//

export default {
  name: 'SimonSays',
  props: {
    msg: String
  }, 
  data: function(){
    return {
      buttons: ["green", "red", "yellow", "blue"],
      simonPicks: "",
      userPicks: ""
    }
  },
  created: function() {
    let min = Math.ceil(1);
    let max = Math.floor(5);
    let randomNum = Math.floor(Math.random() * (max - min)) + min;
    this.simonPicks = this.simonPicks + randomNum;
    console.log("simpon picks", this.simonPicks)
  },
  methods: {
    userInput: function(userPick){
  
      this.userPicks = this.userPicks + userPick;
      console.log(this.userPicks)

      if (this.simonPicks === this.userPicks) {
        console.log("simon", this.simonPicks, "user", this.userPicks)
        console.log("good job")
      } else if (this.simonPicks !== this.userPicks) {
        console.log("simon", this.simonPicks, "user", this.userPicks)
        console.log("bad job")
      }
    }
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
