<template>
  <p>reaction time : -{{score}} ms</p>
  <p class="rank">{{ rank }}</p>
  <img :src="imgsrc" alt="gelmedi">

</template>

<script>
export default {
    props:['score'],
    data(){
        return{
            rank:null,
            imgsrc:null,
        } 
    },
    mounted(){
        if(this.score<250){
            this.rank="Ayrton Senna"
            this.imgsrc='https://arabam-blog.mncdn.com/wp-content/uploads/2020/10/8a7c22a6882a416b885fb5220f9bfcd8.jpg'
            console.log(this.rank)
            console.log(this.imgsrc)
        }
        else if(this.score<400){
            this.rank="Kimi Räikkönen"
            this.imgsrc='https://imgresizer.eurosport.com/unsafe/1200x0/filters:format(jpeg)/origin-imgresizer.eurosport.com/2015/05/05/1474674-31490622-2560-1440.jpg'
            console.log(this.rank)
            console.log(this.imgsrc)
        }
        else{
            this.rank="Sebastian Vettel"
            this.imgsrc='https://cdn-1.motorsport.com/images/amp/YP3XjA82/s6/sebastian-vettel-ferrari-1.jpg'   
            console.log(this.rank)
            console.log(this.imgsrc)
        }
        
    }

}
</script>

<style>
    .rank{
        font-size: 1.4em;
        color: #0faf87;
        font-weight: bold;
    }
</style>