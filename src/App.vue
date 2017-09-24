<template>
  <div id="app">
    <h1> Superhero Story</h1>
      <div id= "data">
       <div><label>Villian's Name:</label><input type="text" required v-model.lazy= "villian" placeholder="Enter Villian"></div>
       <div><label>Day of trouble:</label><input type="text" required v-model.lazy= "day" placeholder= "Enter Day"></div>
        <div><label>Villian's Age:</label><input type="text" required v-model.lazy= "age" placeholder= "Enter Age"></div>
        <div><label>Villian's Power:</label><input type="text" required v-model.lazy= "power" placeholder= "Enter Power"></div>
        <button type="submit" v-on:click= "action">Submit</button>
        <p> {{ output }} </p>
        <p> {{ output2 }} </p>
      </div>
    
  </div>
</template>

<script>
export default {
  
  data() {
    return {

      villian:"",
      day:"",
      age: "",
      power: "",
      output:"",
      output2:"",
      superHero:
               [
                 {"Name":"Batman", 
                  "Age": 30, 
                  "Power": "useless",
                  "Day":"Monday"},

                 {"Name":"Superman", 
                  "Age": 25, 
                  "Power": "strength",
                  "Day":"Tuesday"},
                  
                 {"Name":"Wonderwoman", 
                  "Age": 24, 
                  "Power": "strength",
                  "Day": "Wednesday"},
                  
                 {"Name":"Yoda",
                  "Age": 100, 
                  "Power": "earth",
                  "Day": "Thursday"},
                 
                 {"Name":"Naruto", 
                  "Age": 15, 
                  "Power": "fire",
                  "Day": "Friday"},
                 
                 {"Name":"Thor", 
                  "Age": 30, 
                  "Power": "strength",
                  "Day": "Saturday"},
                 
                 {"Name":"Storm", 
                  "Age": 30, 
                  "Power": "ice", 
                  "Day": "Sunday"}
                ]   
            }  
      },
  
  methods: {
    action: function(){
            this.superHero.forEach((element) => {
            if(element.Day == this.day)
            this.output = element.Name + " fights " + this.villian;
            this.winner(element);

            });
          
          },
    winner: function(element){
            this.superHero.forEach((element) =>{
              if(element.Power == "useless"){
              this.output2 = this.villian + " wins. " + element.Name + " sucks.";
              }

            else if(element.Power == "fire" && this.power == "ice")
              this.output2= this.villian + " loses. " + element.Name + " is awesome because fire always trumps ice!";

            else if(element.Power == "earth")
              this.output2= this.villian + " always loses. " + element.Name + " always wins 'cause he is the greatest!";

            else if(element.Age < this.age)
              this.output2= this.villian + " loses. " + element.Name + " is strong and youthful.";
            
            else
            this.output2= this.villian + " wins. " + element.Name + " is weak and old.";
            
            
        });  
     } 

  }  
}
</script>

<style>

h1{
  text-align:center;
  left:30%;
  font-family:'Nunito SemiBold'
}

#data{
  ;
  position:absolute;
  top:40%;
  left:50%;
  margin-top:-30px;  
  margin-left:-600px;
}

input[type=text] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
    border: 2px solid;
    border-radius: 4px;
}
</style>
