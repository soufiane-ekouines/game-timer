<template>

        <H1>reaction time:{{scor}}</H1>
        <div class="rank">{{rank}}</div>
    
</template>

<script>
export default {
    props:['scor'],
    data() {
        return {
            rank:""
        }
    },

    mounted() {
        if(this.scor<200)
        {
            this.rank="top Fingers"
        }else if(this.scor<500)
        {
            this.rank="Rapid Reflexes"
        }else
            this.rank="Snail pace...."
    },
}
</script>

<style>
.rank{
    font-size:1.4em;
    color:#0faf87;
    font-weight:bold;
}
</style>