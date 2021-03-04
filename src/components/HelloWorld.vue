<template>
  <div class="hello">
    <PropsDemo 
      :post="post"
      :propsString="propsString"
      :props-change="handlePropsChange"
    ></PropsDemo>
  </div>
</template>

<script>
import PropsDemo from "../Page/PropsDemo";
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      post:{
        id:1,
        title:" my name is feelonewong"
      },
      propsString:"success",
      list:["a","b","c"]
    }
  },
  methods:{
    handlePropsChange(value){
      
      // this.$nextTick( function(){
      //   if(value==="warning"){
      //   this.propsString = "success"
      //   }
      // })
      if(value=="warning"){
        this.propsString = "warning";
      }
      if(value=="success"){
        this.propsString = "success";
      }
    }
  },
  components:{
    PropsDemo
  }
}
</script>
