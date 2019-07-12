<template>
  <div>    
    <!-- Part 1 -->
    <h1>h1:{{ msg }} (HelloWorld.vue)</h1>
    
    <!-- Part 2 -->
    <p> Question: Do you like spicy food? </p>
    <button type="button" @click="changeState"> {{ Btn }} </button>

    <p v-if="Btn=='Yes'"> Ans: I love spicy food too! </p>
    <p v-else-if="Btn=='No'"> Ans: You are missing out... </p>
    <p v-else> Ans: You don't know? Lets just have Lasagna for lunch! </p>    

    <p>{{ ans }}</p>

    <!-- Part 3 -->
    <h2> Vue for loop </h2>
    <ul v-for="food in foods" :key="food.foodId" >
      <li> Food ID {{food.foodId }} is {{ food.foodName}}</li>
    </ul>

    <!-- Part 4 -->
    <button @click="showForm"> Show Form </button>
    <myForm v-show="Display==true"/>

  </div>
</template>

<script>
import myForm from './Form'

export default {
  name: 'HelloWorld',
  components: {
    'myForm':myForm
  },
  data () {
    return {
      msg: 'Welcome to your first Vue.js App ^_^',
      Btn : 'Yes',
      Display:false, // for myForm,

      foods:[
        {
          foodId : 1,
          foodName : "Nasi Lemak"
        },
        {
          foodId : 2,
          foodName : "Nasi Putih Supertanker"
        },
        {
          foodId : 3,
          foodName : "Lasagna"
        }
      ]
    }
  },
  methods:{
    changeState(){
      if(this.Btn == 'Yes'){
        this.Btn = 'No'
        this.ans = 'Ans2: Fantastic! Lets have Nasi Lemak for lunch!' // Option 2
      }else{
        this.Btn = 'Yes'        
        this.ans = 'Ans2: Then what type of food do you like?' //Option 2
      }
    },
    showForm(){
      this.Display = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
