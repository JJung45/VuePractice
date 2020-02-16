<template>
    <div>
        {{msg}}
    </div>
</template>

<script>
    import EventBus from '../main';
    export default  {
        data(){
            return {
                msg: '',
                count: 0,
            }
        },
        created() {
            EventBus.$on('push-msg', (payload) => {
                this.msg = payload;
                this.count++;
            })
        }
    }
</script>