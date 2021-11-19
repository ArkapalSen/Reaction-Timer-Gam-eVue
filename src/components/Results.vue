<template>
    <h1>Your score : {{result}}ms</h1>
    <h2 class="rank">You are like {{resultMsg}} </h2>
</template>

<script>
    export default{
        name : 'Results',
        props : ['result'],
        data(){
            return{
                resultMsg : '',
            }
        },
        mounted() {
            this.resultMsg = this.result < 350 ? 'Hare 🐇 You Win 😎' : 'Tortoise 🐢 You Loose 💔'
        },
    }
</script>

<style scoped>
    .rank{
        font-size: 1.4rem;;
        color : #0faf87;
        font-weight: bold;
    }
</style>