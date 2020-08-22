<template>
    <div>
        <h1>Beers</h1>
        <ul v-if="allBeers && allBeers.length">
            <li v-for="beer of allBeers" v-bind:key="beer.id">
                <router-link id = "a" :to="{path: '/' + beer.id}">
                <p>{{beer.name}}</p>
                <img :src="beer.image_url" width="100" height="300">
                </router-link>
            </li>
        </ul>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name: "BeerData",
    data()
    {
        return {
            allBeers: [],
            errors: []
        }
    },
    created() 
    {
        axios.get('https://api.punkapi.com/v2/beers')
        .then(res => {
            this.allBeers = res.data
            // console.log(this.allBeers)
        })
        .catch(e => {
            this.errors.push(e)
        })
    }

}
</script>

<style scoped>
ul {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    flex-wrap: wrap;
}

#a {
    display: block;
}

li {
    margin-top: 5%;
    padding-top: 1%;
    padding-bottom: 1%;
    flex-basis: 25%;
    list-style-type:none;
    border: 1px solid grey;
    border-radius: 25px;
}

li:hover {
    background-color: rgb(206, 205, 205);
}


</style>