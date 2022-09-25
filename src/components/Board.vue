<template>
    <div>
        Board
        <div v-if="loading">loading board...</div>
        <div v-else>
            <div>bid : {{ bid }}</div>
            <router-link :to="`/b/${bid}/c/1`">Card1</router-link>
            <router-link :to="`/b/${bid}/c/2`">Card2</router-link>
        </div>
        <hr />
        <router-view></router-view>
    </div>
</template>

<script>
export default {
    data() {
        return {
            bid: 0,
            loading: false
        }
    },
   created() {
    this.fetchData()
   },
   methods: {
       fetchData() {
            this.loading = true
            console.log("loading");
            setTimeout(() => {
                this.bid = this.$route.params.bid
                console.log("0.5sec");
                this.loading = false
                console.log("board data 출력");            
            }, 500)
        }
   }
};
</script>

<style>

</style>