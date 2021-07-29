<template>
    <div v-if="details.cod != '404'">
        <div>
            <div v-if="typeof details.main != 'undefined'" class="data">
                <h3>{{ details.name }}</h3>
                <p>Latitude: {{ details.coord.lat }}</p>
                <p>Longitude: {{ details.coord.lon }}</p>
                <p>Pressure: {{ details.main.pressure }}</p>
                <p>Humidity: {{ details.main.humidity }}</p>
                <p>Temp: {{ Math.round((details.main.temp -273.15)*100)/100 }}°c</p>
            </div>
        </div>
    </div>  
    <div v-if="details.cod == '404'" class="notfound">
        <p>City not found</p>
    </div>
    <div v-if="details.cod == '400'" class="notfound">
        <p>City not entered</p>
    </div>
</template>

<script>
    
    export default{
        name: 'Data',
        props:{
            details: {}
        },
        
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');
    .data,.notfound{
        text-align: center;
        font-size: 150%;
        background-color:rgb(204, 156, 226);
        margin: 0% 14% 1% 14%;
        padding: 0.5% 1% 0.5% 1%;
        font-family: 'Montserrat', sans-serif;;
    }
    
</style>