<template>
    <a href='#' class="sub-item link" @click.prevent='$emit("chooseItem")'>{{ name }}</a>
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
};
</script>