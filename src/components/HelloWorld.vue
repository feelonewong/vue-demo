<template>
  <div class="hello">
    <PropsDemo 
      :post="post"
      :propsString="propsString"
      :props-change="handlePropsChange"
    ></PropsDemo>
    <hr>
    <Event
       :name="eventName"
       @change="handleEventChange"/>
    <hr>
    <SlotDemo>
      <template v-slot:footer>
        第3个插槽是尾部
      </template>
      <template v-slot:header>
        第1个插槽是头部
      </template>
      <template v-slot:header>
        第2个插槽是中间
      </template>

      <template v-slot:default="slotProps">
        {{ slotProps.user.firstName }}=={{slotProps.user.lastName}}
      </template>
    </SlotDemo>
    <hr>
    传统写法
    <DoubleData
      :phone-info="phoneInfo"
      @change="value=>{phoneInfo = value}"
    />
    语法糖
    <DoubleData
            v-model="phoneInfo"
    />
    PhoneInfo:{{phoneInfo.code +"===" + phoneInfo.number }}
  </div>
</template>

<script>
import PropsDemo from "../Page/PropsDemo";
import Event from "../Page/Event";
import SlotDemo from "../Page/SlotDemo";
import DoubleData from "../Page/doubleData";
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
      list:["a","b","c"],
      eventName:"",
      phoneInfo:{
          code: Date.now(),
          number: ""
      }
    }
  },
  methods:{
    handlePropsChange(value){
      if(value=="warning"){
        this.propsString = "warning";
      }
      if(value=="success"){
        this.propsString = "success";
      }
    },
    handleEventChange(value){
        this.eventName = value;

    }
  },
  components:{
    PropsDemo,
    Event,
    SlotDemo,
    DoubleData
  }
}
</script>
