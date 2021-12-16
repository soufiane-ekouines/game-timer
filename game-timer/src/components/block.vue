<template>
        <div class="block" v-if="showblock" @click="stop">
            click me
        </div>  
    
</template>
<script>
export default {
    props:['delay'],
    data() {
        return {
            showblock:false,
            time:null,
            reaction:0
        }
    },
    mounted() {
        setTimeout(()=>{
            this.showblock=true
            this.start()
        },this.delay)
    },
    methods: {
        start(){
                this.time=setInterval(() => {
                    this.reaction+=10
                }, 10);
        },
        stop()
        {
            clearInterval(this.time)
            this.$emit('end',this.reaction)
            

        }
    },
   
}
</script>
<style>
.block{
    width: 400px;
    border-radius: 20px;
    background-color: rgb(8, 97, 97);
    color:azure;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>