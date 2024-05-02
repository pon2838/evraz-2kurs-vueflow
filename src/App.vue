<script setup>
import { ref } from 'vue';
import {
    VueFlow,
    useVueFlow,
} from '@vue-flow/core';

const initialNodes = ref([
    {
        id:       '1',
        position: { x: 50, y: 50 },
        label:    'Node 1',
    },
]);
const { addNodes, removeNodes } = useVueFlow();

function generateRandomNode() {
    return {
        id:       Math.random().toString(),
        position: { x: Math.random() * 500, y: Math.random() * 500 },
        label:    'Random Node',
    };
}

function onAddNode() {
    // add a single node to the graph
    addNodes(generateRandomNode());
}

function onAddNodes() {
    // add multiple nodes to the graph
    addNodes(Array.from({ length: 10 }, generateRandomNode));
}

// remove a single node from the graph
function onRemoveNode() {
    removeNodes('1')
}

// remove multiple nodes from the graph
function onRemoveNodes() {
    removeNodes(['1', '2'])
}
</script>

<template>
    <VueFlow :nodes="initialNodes"/>
    
    <button
        type="button"
        @click="onAddNode"
    >Add a node
    </button>
    <button
        type="button"
        @click="onAddNodes"
    >Add multiple nodes
    </button>
    <button
        type="button"
        @click="onRemoveNode"
    >Remove a node
    </button>
</template>
