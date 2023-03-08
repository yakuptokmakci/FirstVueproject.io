<template>
  <div class="block" v-if="showBlock" @click="stoptimer" >
    click me
  </div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return {
            showBlock:false,
            timer:null,
            reactiontime:0,
        
        }
    },
    mounted(){
        console.log("component mounted")
        setTimeout(()=>{
            this.showBlock=true
            console.log(this.delay)
            this.starttimer()
        },this.delay)
    },
    methods:{
        starttimer(){
            this.timer=setInterval(()=> {
                this.reactiontime +=10
            },10)
        },
        stoptimer(){
            clearInterval(this.timer)
            console.log(this.reactiontime)
            this.$emit('end',this.reactiontime)
        }
    }
}
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color:white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>