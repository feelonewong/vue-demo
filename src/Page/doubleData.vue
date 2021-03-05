<template>
  <div>
    <input type="text" @change="handleChange">
  </div>
</template>

<script>
    export default {
        model:{
            prop:"phoneInfo", //默认是value
            event: "change" //默认是input事件
        },
        props: {
          phoneInfo: {
              type:Object
          }
        },
        data(){
            return {

            }
        },
        methods:{
            handleChange(e){
                console.log(e.target.value);
                let data = {
                    code: Date.now(),
                    number: e.target.value
                }
                this.$emit("change",data);
            }
        }
    };
</script>

<style scoped>

</style>