<template>
  <div>
    <h1>Parent</h1>
    <button @click="upperCaseMessage">To upper case</button>
    <button @click="increment">invrement</button>
    <button @click="incrementVal">incrementVal</button>
    <button @click="incrementReactVal">incrementReactVal</button>

    <h2>{{ state.message }}</h2>
    <h2>{{ refVal }}</h2>
    <h2>{{ val }}</h2>
    <h2>{{ state.ractiveVal }}</h2>
    <h1>Child</h1>
    <ChildComponent
      :val="val"
      :refVal="refVal"
      :message="state.message"
      :ractiveVal="state.ractiveVal"
      @change-message="changeMessage"
      @change-num="changeNum"
      @change-num-val="changeNumVal"
      @change-num-reactval="cangeReactiveVal"
    ></ChildComponent>
  </div>
</template>

<script lang="ts">
import ChildComponent from "@/components/ChildComponent.vue";
import { createComponent, reactive, ref } from "@vue/composition-api";

export default createComponent({
  components: {
    ChildComponent
  },
  setup() {
    const state = reactive({
      message: "Hello",
      ractiveVal: 0
    });
    const refVal = ref<number>(0);
    let val = 0;

    const changeMessage = (message: string) => {
      state.message = message;
    };
    const changeNum = (num: number) => {
      refVal.value = num;
    };

    const changeNumVal = (num: number) => {
      val = num;
    };

    const increment = () => {
      refVal.value++;
    };

    const incrementVal = () => {
      val = val + 1;
    };
    const upperCaseMessage = () => {
      state.message = state.message.toUpperCase();
    };

    const incrementReactVal = () => {
      state.ractiveVal = state.ractiveVal + 1;
    };

    const cangeReactiveVal = (num: number) => {
      state.ractiveVal = num;
    };

    return {
      val,
      incrementReactVal,
      cangeReactiveVal,
      changeNumVal,
      refVal,
      state,
      incrementVal,
      changeMessage,
      increment,
      changeNum,
      upperCaseMessage
    };
  }
});
</script>
