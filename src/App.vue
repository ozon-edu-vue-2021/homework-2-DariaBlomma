<template>
  <div id="app">
    <List />
  </div>
</template>

<script>
import List from '@/components/List.vue';

export default {
  name: 'App',
  components: { 
    List,
  },
}
</script>

<style> 
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

    .path {
      font-size: 16px;
    }

    .item-wrapper {
      display: flex;
      flex-direction: column;
      max-width: fit-content;
    }
</style>
