<template>
  <div class="container">

    <!-- the four buttons -->
    <!-- <div v-for="(button, index) in buttons" 
      :key="index"
      :click="userInput(index)"
      :class="`button ${button}`"></div> -->
    <section>
      <div class="button green" @click="userInput(1)" ref="one"></div>
      <div class="button red" @click="userInput(3)" ref="three"></div>
    </section>
    <section>
      <div class="button yellow" @click="userInput(2)" ref="two"></div>
      <div class="button blue" @click="userInput(4)" ref="four"></div>
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
// How to wait for user to give the same number of values as the length of what simpon picks 

export default {
  name: 'SimonSays',
  props: {
    msg: String
  }, 
  data: function(){
    return {
      simonPicksArray: [],
      userPicksArray: [],
    }
  },
  created: function() {
    // create random number on first load and push it to simonPicksArray
    let min = Math.ceil(1);
    let max = Math.floor(5);
    let randomNum = Math.floor(Math.random() * (max - min)) + min;
    this.simonPicksArray.push(randomNum);
    console.log("simon's first number", this.simonPicksArray);

    
  },
  methods: {
    userInput: function(userPick){
      // get random number
      let min = Math.ceil(1);
      let max = Math.floor(5);
      let randomNum = Math.floor(Math.random() * (max - min)) + min;

      // push userPick to array 
      this.userPicksArray.push(userPick);
      // this.userCount = this.userCount + 1;

      
      // loop through array, if the item in simponPicksArray is the same as item in userPicksArray, then push another random number to simon array and clear user array 
       for (let i = 0; i < this.userPicksArray.length; i++){
        if (this.simonPicksArray[i] === this.userPicksArray[i]){
          this.userPicksArray = [];
          this.simonPicksArray.push(randomNum);
          console.log("good");
          console.log("simon", this.simonPicksArray, "user", this.userPicksArray);
        } else {
          console.log("bad");
        }
      }


      // for (let i = 0; i < this.userPicksArray.length; i++){
      //   if (this.simonPicksArray[i] === this.userPicksArray[i]){
      //     this.userPicksArray = [];
      //     this.simonPicksArray.push(randomNum);
      //     console.log("good");
      //     console.log("simon", this.simonPicksArray, "user", this.userPicksArray);
      //   } else {
      //     console.log("bad");
      //   }
      // }

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
