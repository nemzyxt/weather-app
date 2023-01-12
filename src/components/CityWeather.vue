<template>
    <input type="text" v-model="city" placeholder="Enter city ..." />
    &nbsp;
    &nbsp;
    &nbsp;
    <button v-on:click="findWeather">Go</button>
    <div v-if="info_available" class="weather">
        <label>{{ this.city }}</label>
        <WeatherItem :item="this.items[0]" :detail="this.temp" />
        <WeatherItem :item="this.items[1]" :detail="this.humidity" />
        <WeatherItem :item="this.items[2]" :detail="this.pressure" />
    </div>
</template>

<script>
import axios from 'axios'
import WeatherItem from './WeatherItem'

export default {
    name: 'CityWeather',
    components: {
        WeatherItem,
    },
    data() {
        return {
            info_available: false,
            BASE_URL: "https://api.openweathermap.org/data/2.5/weather?",
            API_KEY: "11ccc85d3db11be8d387f84e41cc5820",
            city: '',
            items: ["Temperature (F)", "Humidity (%)", "Pressure (hPa)"],
            temp: '',
            humidity: '',
            pressure: ''
        }
    },
    methods: {
        async findWeather() {
            if(this.city == "") {
                alert("Enter the City Name")
                return
            }
            const URL = this.BASE_URL + "q=" + this.city + "&appid=" + this.API_KEY
            const response = await axios.get(URL)
            if(response.status != 200) {
                alert("Some error occurred")
            }
            const main = response.data.main
            this.temp = main.temp
            this.humidity = main.humidity
            this.pressure = main.pressure
            this.info_available = true
        }
    }
}

</script>

<style>

input {
    width: 310px;
    height: 40px;
    text-align: center;
    font-size: 125%;
}

button {
    height: 45px;
    font-size: 125%;
    padding-right: 15px;
    padding-left: 15px;
    color: white;
    background-color: green;
    border: none;
}

.weather {
    margin-top: 35px;
}

.weather label {
    font-size: 150%;
    margin-right: auto;
    margin-left: auto;
    color: green;
    text-decoration: overline underline;
}

</style>