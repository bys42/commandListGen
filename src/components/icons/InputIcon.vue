<script setup>
import NumberIcon from "./NumberIcon.vue";
import ArrowDown from "./ArrowDown.vue";
import ArrowLeft from "./ArrowLeft.vue";
import ArrowRight from "./ArrowRight.vue";
import ArrowUp from "./ArrowUp.vue";
const props = defineProps({ keyName: String });
const IconMap = {
    "^": ArrowUp,
    "_": ArrowDown,
    "<": ArrowLeft,
    ">": ArrowRight,
    "0": NumberIcon,
    "1": NumberIcon,
    "2": NumberIcon,
    "3": NumberIcon,
    "4": NumberIcon,
    "5": NumberIcon,
    "6": NumberIcon,
    "7": NumberIcon,
    "8": NumberIcon,
    "9": NumberIcon,
};
</script>

<template>
    <component :is="IconMap[keyName]" :keyName="keyName"></component>
</template>

<style>
svg,
.number {
    margin: 0 6px;
}
</style>
