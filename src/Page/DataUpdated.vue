<template>
  <div>
      使用的数据UsedData:{{data1}}<br>
      <button @click="handleChangeData">change data button</button>
      没有使用的数据NotUseData:data2 ,
      数据data2没有挂载在页面上因此不会触发组件更新
    obj: {{obj}}
  </div>
</template>

<script>
export default {
    data(){
        return{
            data1:"123",
            data2:"",
            obj:{}
        }
    },
    updated(){
        console.log("updated...")
    },
    methods:{
        handleChangeData(){
            this.data2 = Date.now();
            this.obj.number = 123;
        }
    }
}
</script>

<style>

</style>