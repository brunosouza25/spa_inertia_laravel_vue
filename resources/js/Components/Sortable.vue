<script setup>
import { computed } from "vue";

const props = defineProps({
    name: {
        type: String,
        required: true
    },
    label: {
        type: String,
        required: true
    },
})

const sortClass = computed(() => {
    let sortBy = "name"
    let sortDir = sortBy.charAt(0)
    let sortClass = ""

    if (sortBy.replace(/^\-+/, "") === props.name) {
        sortClass = sortDir === '-' ? 'desc' : 'asc'
    }

    return sortClass
})
</script>

<template>
    <a href="#" class="sortable" :class="sortClass">{{ props.label }}</a>
</template>
