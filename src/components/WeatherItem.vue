<template>
    <div class="item">
        <header>{{ item }}</header>
        <body>{{ detail }}</body>
    </div>
</template>

<script>

export default {
    name: 'WeatherItem',
    props: [
        'item', 
        'detail'
    ]
}

</script>

<style>

.item {
    width: 340px;
    margin-right: auto;
    margin-left: auto;
    margin-top: 20px;
    border: 1px solid blue;
}

header, body {
    height: 40px;
    font-size: 125%;
}

header {
    padding-top: 10px;
    color: white;
    background-color: blue;
}

body {
    color: blue;
    height: 25px;
}

</style>