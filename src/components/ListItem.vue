<template>
    <span>
        <input @click="markAsComplete" type="checkbox" :value="listitem.key" v-if="!listitem.completed"/> <span :class="{strike : listitem.completed}">{{listitem.details}}</span>
    </span>
</template>
<script>
export default {
    props : ['listitem','mac'], 
    methods : {
        markAsComplete(event){
            this.mac(event.target.value);
        }
    }
}
</script>

<style scoped>

    .strike{
        text-decoration:line-through;
    }

</style>