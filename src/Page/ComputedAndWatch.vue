<template>
  <div>
    使用computed:{{reverseMessage}}<br>
    使用methods:{{handleReverse()}}<br>
    <button @click="()=>$forceUpdate()">$uppdated data</button>
    <input type="text" v-model="message"><br>
    ================================================================
    <br>
    computed VS watch<br>
    <!-- 使用computed: 😄
     {{computedName}}😄<br> -->
    firstName:<input v-model="firstName"/><br>
    lastName:<input v-model="lastName"/><br>
    使用watch:😄
     {{fullName}}😄<br>
    firstName:<input v-model="firstName"/><br>
    lastName:<input v-model="lastName"/><br>
  </div>
</template>

<script>
export default {
    data(){
        return{
            message:"hello vue",
            fullName:"",
            firstName:"",
            lastName:"",
        }
    },
    computed: {
        reverseMessage(){
            return this.message.split("").reverse().join("");
        },
        computedName(){
            return this.firstName+this.lastName;
        }
    },
    watch:{
        firstName(value){
                // this.fullName = this.lastName + value;
            clearTimeout(this.setTimoutFirstName);
            this.setTimoutFirstName = setTimeout(()=>{
                this.fullName = this.lastName + value;
            },500);
        },
        lastName(value){
            this.fullName = this.firstName + value;
        },
    },
    methods:{
        handleReverse(){
            return this.message.split("").reverse().join("");
        }
    }
}
</script>