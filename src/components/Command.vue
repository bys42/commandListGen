<script setup>
import InputIcon from "./icons/InputIcon.vue";
defineProps({
    command: String,
    message: String,
    subCommand: Array,
});
</script>

<template>
    <div class="command">
        <div class="message">{{ message }}</div>
        <div class="input">
            <InputIcon v-for="item in command" :keyName="item" />
        </div>
        <template v-if="subCommand">
            <Command
                v-for="{ command, message } in subCommand"
                :command="command"
                :message="message"
            ></Command>
        </template>
    </div>
</template>

<style>
.command {
    display: block;
    margin: 20px 0;
    color: lightgray;
}
.command .command {
    margin-left: 120px;
    position: relative;
}
.message {
    font-size: 36px;
    margin: 10px 0;
}
.input {
    display: flex;
    align-items: center;
}
</style>
