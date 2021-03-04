<template>
  <div>
      Post.id:{{post.id}} , Post.title: {{post.title}}<br>
      propsString:{{propsString}}
      <button @click="handleChange">check propsString</button>
  </div>
</template>

<script>
export default {
    props:{
        propsString:{
            type:String
        },
        post:{
            type: Object,
        },
        list:{
            type:Object,
            default:()=>{
                return {
                    message:"hello"
                }
            }
        },
        propsChange:{
            type: Function
        }
    },
    methods:{
        handleChange(){
            console.log('child',this.propsString);
            this.propsChange(this.propsString==="success"?"warning":"success")
        }
    },
    mounted(){
    }
}
</script>

<style>

</style>