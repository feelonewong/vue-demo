<template>
  <div>
    <h3>事件DEMO</h3>
    {{name || "==="}}
    <input :value="name" @change="handleChange">
  </div>
</template>

<script>
    export default {
        props: {
            name: String
        },
        methods:{
            handleChange(e){
                this.$emit("change", e.target.value)
            }
        }
    };
</script>

<style scoped>

</style>