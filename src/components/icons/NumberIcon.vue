<script setup>
const props = defineProps({ keyName: String });

function getColorScheme(number) {
    if (number == 0) {
        return "color0";
    }
    if (number <= 3) {
        return "color123";
    }
    if (number <= 6) {
        return "color456";
    }
    return "color789";
}
</script>

<template>
    <div class="number" :class="getColorScheme(+keyName)">
        {{ keyName }}
    </div>
</template>

<style>
.color123 {
    --color: #94d3dd;
    --background-color: #397e93;
}
.color456 {
    --color: #f3ee6c;
    --background-color: #97973b;
}
.color789 {
    --color: #f09393;
    --background-color: #a93938;
}
.color0 {
    --color: #f2f2f1;
    --background-color: #434445;
}
.number {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    border-radius: 100%;
    background-color: var(--background-color);
    color: var(--color);
    font-size: 28px;
    font-weight: bold;
    border: 4px solid var(--color);
    width: 48px;
    height: 48px;
    box-sizing: border-box;
}
</style>
