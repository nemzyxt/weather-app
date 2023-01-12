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
    margin-top: 30px;
    border: 1px solid blue;
}

.item * {
    height: 45px;
    font-size: 125%;
}

header {
    padding-top: 10px;
    color: white;
    background-color: blue;
}

body {
    color: blue;
    height: 35px;
}

</style>