<template>
    <div>
        <h1 v-on:click="changeHeader">{{header}}</h1>
        <p>{{ message }}</p>
    </div>
</template>
<script>
    import { bus } from '../main'
    export default {
        name: 'Test',
        data() {
            return {
                message: '안녕하세요 Vue!'
            }
        },
        props: {
            header:{
                type: String
            }
        },
        methods: {
            changeHeader (){
                this.header = "changed header";
                bus.$emit('changeIt', 'changed header');
            }
        }
    }
</script>