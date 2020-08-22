<template>
    <div>
        <h1>{{singleBeer.name}}</h1>
        <img :src="singleBeer.image_url" width= "100" height="300">
        <p>{{singleBeer.tagline}}</p>
        <p>{{singleBeer.description}}</p>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "singleBeer",
    data()
    {
        return {
            singleBeer: [],
            errors: []
        }
    },
    created() 
    {
        axios.get('https://api.punkapi.com/v2/beers/' + this.$route.params.id)
        .then(res => {
            this.singleBeer = res.data[0]
            console.log(this.singleBeer)
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