<template>
    <div class='item-wrapper'>
        <a href='#' :class="['link', {'chosen': chosen}]" @click.prevent='chooseItem'>{{ name }}</a>
    </div>
</template>
<script>
export default {
    name: 'Link',
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