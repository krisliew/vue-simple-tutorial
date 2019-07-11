<template>
    <!-- Part 6 -->
    <form v-on:submit.prevent="formSubmit">
        <h1>h1: This form is a Child Component (Form.vue) </h1>

        <input type="text" v-model="formInput">
        <p> {{ formInput }}</p>

        <button type="submit">Submit</button>
        <p id="errorMsg"> {{ ErrorMsg }}</p>      
    </form>
</template>

<script>

export default {
  name: 'myForm',
  data () {
    return {
      formInput:'',
      ErrorMsg:''
    }
  },
  methods:{
    formSubmit(){
        if(this.formInput.length < 1){
            this.ErrorMsg = 'You have clicked the malfunctioned submit button!'
        }else{
            this.ErrorMsg = ''
            //Can add a post method here
        }     
    }
  }
}
</script>

<style scoped>
h1{
    font-size:14px;
}
#errorMsg{
    color:red;
    font-weight: 300;
    font-size:13px;
}
</style>
