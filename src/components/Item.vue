<template>
    <li>
        <div class='item-wrapper'>
            <Link 
                v-if="item.type === 'link'"
                :name='item.name'
                :class='{"chosen": chosen}'
                @chooseItem='chooseItem'
            />
            <File
                v-else-if="item.type === 'file'"
                :name="item.name"
                :class='{"chosen": chosen}'
                @chooseItem='chooseItem'
            />
            <Folder 
                v-else
                :name='item.name'
                @toggleFolder='toggleFolder'
            />
            <b class='path' v-if='opened || chosen'>{{path}}</b>
        </div>
        <ul v-if="opened && item.contents && item.contents.length">
            <Item 
                v-for="(child, subIndex) in item.contents" 
                :key="subIndex" 
                :item="child"
                :path="path + '/' + child.name" 
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
        path: {
            type: String,
            required: true,
        }
    },
    data() {
        return {
            // открыта ли папка
            opened: false,
            // выбран ли файл или ссылка
            chosen: false,
        }
    },
    methods: {
        toggleFolder() {
            this.opened = !this.opened;
        },
        chooseItem() {
            this.chosen = !this.chosen;
        },
    },
};
</script>