<template>
    <li>
        <Link 
            v-if="item.type === 'link'"
            :name='item.name'
        />
        <File
            v-else-if="item.type === 'file'"
            :name="item.name"
        />
        <Folder 
            v-else
            :name='item.name'
            @toggleFolder='toggleFolder'
        />

        <ul v-if="opened && item.contents && item.contents.length">
            <Item 
                v-for="(child, subIndex) in item.contents" 
                :item="child"
                :key="subIndex"
                :parentItem="item.name"  
            />
        </ul>
    </li>
</template>

<script>
import File from '@/components/File.vue';
import Link from '@/components/Link.vue';
import Folder from '@/components/Folder.vue';

export default {
    name: 'Item',
    components: {
        File,
        Link,
        Folder,
    },
    props: {
        item: {
            type: Object,
            required: true
        },
        index: {
            type: Number,
            required: false
        },
        parentItem: {
            required: false,
            default: '',
        },
    },
    data() {
        return {
            opened: false,
        }
    },
    methods: {
        toggleFolder() {
            this.opened = !this.opened;
        },
    },
};
</script>