<template>
    <div id="app">
        <Header/>
        <b-container>
          <Input :addListItem="addListItem"/>
          <List :todolist="list" :markAsComplete="markAsComplete"/>
        </b-container>
    </div>
</template>

<script>
import Header from './components/Header';
import Input from './components/Input';
import List from './components/List';

export default {
  name: 'app',
  components: {
   Header, 
   Input, 
   List
  }, 
  data(){
    return {
      list : []
    }
  }, 
  methods : {
    addListItem(input){
      this.list.push({key : this.list.length + 1, details : input, completed : false});
    }, 
    markAsComplete(val){

      this.list = this.list.map(item => {

        if(item.key == val){
            item.completed = true
        }

        return item;
      });

    }
  }
}
</script>

<style>
    h1{
      color:yellowgreen;
    }
</style>
