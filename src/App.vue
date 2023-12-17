<script setup>
import Command from "./components/Command.vue";

const commandList = [
    {
        command: "^_<>1234567890",
        message: "Test Message 1",
    },
    {
        command: "^^__<><>0",
        message: "Test Message 2",
        subCommand: [
            { command: "<>3", message: "Test Message 3" },
            { command: "_^6", message: "Test Message 4" },
        ],
    },
];
</script>

<template>
    <div class="container">
        <Command
            v-for="{ command, message, subCommand } in commandList"
            :command="command"
            :message="message"
            :subCommand="subCommand"
        />
    </div>
</template>

<style>
.container {
    display: flex;
    flex-direction: column;
    padding-left: 20px;
}
</style>
