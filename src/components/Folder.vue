<template>
    <span 
        class="directory" 
        @click='$emit("toggleFolder")'
    >
    {{ name }}
    </span>
</template>
<script>
export default {
    name: 'Folder',
    props: {
        name: {
            type:  String,
            required: true,
        },
    },
};
</script>