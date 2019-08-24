<template>
    <div>
        <b-input-group class="mt-5">
            <b-form-input v-model="userInput" @keyup="checkIfCharsExist" @keypress.enter="addItem"></b-form-input>
            <b-input-group-append>
                <b-button variant="primary" @click="addItem" :disabled="buttonDisabled">Add</b-button>
            </b-input-group-append>
        </b-input-group>
    </div>
</template>

<script>
export default {
    data(){
        return {
            userInput : '', 
            buttonDisabled : true
        }
    }, 
    props : {
        addListItem : Function
    },
    methods : {
        addItem(){
            this.addListItem(this.userInput);
            this.userInput = '';
            this.buttonDisabled = true;
        }, 
        checkIfCharsExist(){
            if(!this.userInput.length){
                return this.buttonDisabled = true;
            }

            this.buttonDisabled = false;
        }
    }
}
</script>