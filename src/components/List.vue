<template>
    <div>
        <b-list-group class="mt-5">
            <b-list-group-item v-for="item in todolist" :key="item.key">
             <ListItem :listitem="item" :mac="markAsComplete"/>
            </b-list-group-item>
        </b-list-group>
    </div>
</template>
<script>
import ListItem from './ListItem';

export default {
    components : {
        ListItem
    }, 
    props : ['todolist', 'markAsComplete']
}
</script>

<style scoped>
li {
    list-style:none;
}
</style>