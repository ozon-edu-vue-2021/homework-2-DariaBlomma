<template>
    <small  :class="['file', {'chosen': chosen}]" @click.prevent='chooseItem'><b>{{ name }}</b></small>
</template>
<script>
export default {
    name: 'File',
    props: {
        name: {
            type:  String,
            required: true,
        },
    },
    data() {
        return {
            chosen: false,
        }
    },
    methods: {
        chooseItem() {
            this.chosen = !this.chosen;
        },
    },
};
</script>