<template>
  <div>
    <button @click="upperCaseMessage">To upper case</button>
    <button @click="increment">invrement</button>
    <button @click="incrementVal">invrementVal</button>
    <button @click="incrementRactiveVal">invrementractiveVal</button>
    <h2>{{ message }}</h2>
    <h2>{{ refVal }}</h2>
    <h2>{{ val }}</h2>
    <h2>{{ ractiveVal }}</h2>
  </div>
</template>

<script lang="ts">
import { createComponent, SetupContext } from "@vue/composition-api";

type Props = {
  message: string;
  refVal: number;
  val: number;
  ractiveVal: number;
};

export default createComponent({
  props: {
    message: {
      type: String,
      default: "default value"
    },
    refVal: {
      type: Number,
      default: 0
    },
    val: {
      type: Number,
      default: 0
    },
    ractiveVal: {
      type: Number,
      default: 0
    }
  },
  setup(props: Props, context: SetupContext) {
    const upperCaseMessage = () => {
      context.emit("change-message", props.message.toUpperCase());
    };

    const increment = () => {
      context.emit("change-num", props.refVal + 1);
    };

    const incrementVal = () => {
      context.emit("change-num-val", props.val + 1);
    };

    const incrementRactiveVal = () => {
      context.emit("change-num-reactval", props.ractiveVal + 1);
    };

    return {
      incrementRactiveVal,
      incrementVal,
      upperCaseMessage,
      increment
    };
  }
});
</script>
