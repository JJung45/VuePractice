<template>
    <div>
        <h2>{{header}}</h2>
    </div>
</template>
<script>
    import { bus } from '../main';
    export default {
        name: 'Test2',
        props: {
            header:{
                type: String
            }
        },
        created (){
            bus.$on('changeIt', (data) => {
                this.header = data;
            })
        }
    }
</script>