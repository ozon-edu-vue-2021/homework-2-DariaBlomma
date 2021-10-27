<template>
    <ul>
        <Item 
            :item="json"
        />
    </ul>
</template>
<script>
import json from '/public/static/node_modules.json';
import Item from '@/components/Item.vue';

export default {
    name: 'List',
    components: {
        Item,
    },  
    data() {
        return {
            json,
        }
    },
};
</script>