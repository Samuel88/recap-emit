<script>
export default {
    emits: ['notifyRemove'],
    props: {
        notifies: {
            type: Object,
            required: true,
        }
    },
    data() {
        return {
        }
    }
}
</script>

<template>
    <div v-for="(notify, idx) in notifies" :key="idx" @click="$emit('notifyRemove', idx)">
        {{ notify }}
    </div>
</template>