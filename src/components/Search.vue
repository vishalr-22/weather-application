<template>
    <div class="search1">
        <input @keypress="fetch" type="text" v-model="query" placeholder="Search By City Name">
    </div>
    
</template>

<script>
    
    export default{
        name: 'Search',
        data(){
            return{
                api_key: 'e88bb5b9c2248c8ba0d247b0dda5eb96',
                url_base: 'https://api.openweathermap.org/data/2.5/',
                query: '',
                weather: {}
            }
        },
        methods:{
            fetch(e){
                if (e.key == "Enter") {
                    fetch(`${this.url_base}weather?q=${this.query}&appid=${this.api_key}`)
                    .then(res => {
                        return res.json();
                    }).then(this.setResults);
                    
                }
            },
            setResults (results) {
                this.weather = results;
                console.log(this.weather)
                this.$emit('weather', this.weather)
            },
        }
        
    }
</script>

<style scoped>
    .search1{
        text-align: center;
    }
    input{
        margin: 0% 5% 3% 5%;
        height: 40px;
        width: 600px;
        font-size: 120%;
        padding: 2%;
    }
</style>