<template>
    <ul>
        <Item 
            :item="json"
            :path="json.name"
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
<style> 
    .item-wrapper {
        display: flex;
        flex-direction: column;
        max-width: fit-content;
    }

    .path {
        font-size: 16px;
    }

    .sub-item {
        width: fit-content;
    }

    .directory {
        background-color: rgb(211, 211, 169);
    }

    .file {
        background-color: rgb(169, 205, 211);
    }     
    
    .link {
        color: rgb(83, 69, 129);
    }

    .directory:hover {
        opacity: 0.8;
    }

    .file:hover {
        background-color: rgb(139, 180, 187);
    }

    .link:hover {
        color: rgb(40, 30, 71);
    }
    
    .chosen {
        opacity: 0.5;
    }
</style>