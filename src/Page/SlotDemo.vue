<template>
  <div>
    <h2>这里是子组件，下面是一个插槽</h2>
    <slot name="header"></slot>
    <slot name="main"></slot>
    <slot name="footer"></slot>

    <slot :user="user">
      {{ user.lastName }}
    </slot>
  </div>
</template>

<script>
    export default {
      data(){
          return{
              user:{
                  firstName:"wong",
                  lastName:"feelone"
              }
          }
      }
    };
</script>

<style scoped>

</style>