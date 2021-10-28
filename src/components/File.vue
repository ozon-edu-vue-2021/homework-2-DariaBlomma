<template>
    <small  class="sub-item file" @click='$emit("chooseItem")'><b>{{ name }}</b></small>
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
};
</script>