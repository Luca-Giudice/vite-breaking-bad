<script>
import axios from 'axios';
export default {
    name: 'PokemonsList',
    data(){
        return {
            pokemons: []
        }
    },
    created(){
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=20&page=2').then(res=> {
            this.pokemons = res.data.results;
        });
    }
}
</script>
<template>
    <section id="pokemons" class="my-5">
        <div class="row g-4 row-cols-2 row-cols-md-3 row-cols-lg-4">
            <div v-for="pokemon in pokemons.docs" :key="pokemon.docs[id]" class="mb-5">
                {{ pokemon.docs[name] }}
            </div>
        </div>
    </section>
</template>
<style></style>