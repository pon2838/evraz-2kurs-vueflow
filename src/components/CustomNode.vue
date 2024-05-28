<script setup>
import { Position, Handle } from '@vue-flow/core'
import { DefineProps } from '@vue/runtime-core'
import { ref } from 'vue';

// props were passed from the slot using `v-bind="customNodeProps"`
const props = defineProps(['label'])

const inputValue = ref('')
</script>

<template>
    <!--<div>-->
    <!--    <Handle type="target" :position="Position.Top" />-->
    <!--    <div>{{ label }}</div>-->
    <!--    <Handle type="source" :position="Position.Bottom" />-->
    <!--</div>-->
    <div class="custom-node-container">
        <input class="nodrag" v-model="inputValue" />
    </div>
</template>
