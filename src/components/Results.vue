<template>
  <h3>Result : {{result}}ms</h3>
  <h2>{{rank}}</h2>
</template>

<script>
export default {
    props: ["result"],
    data(){
        return{
            rank: null,
        }
    },
    mounted(){
        if(this.result<250){
            this.rank = 'Ninja Fingers'
        }else if(this.result<400){
            this.rank = 'Rapid Reflexes'
        }else{
            this.rank = 'Snail Pace...'
        }
    }
}
</script>

<style>

</style>