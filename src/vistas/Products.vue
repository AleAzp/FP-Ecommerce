<template>
    <div>
        <div class="relative mx-6">
            <img class="hidden sm:flex rounded-lg" :src="banner2" alt="banner" />
            <img class="sm:hidden rounded-lg" :src="banner3" alt="banner" />
            <div class="flex flex-col absolute inset-0 items-center justify-center ">
            <Countdown></Countdown>
            </div>
        </div> 
    </div>
    <SearchBar></SearchBar>
    <div class="flex flex-col justify-between items-top gap-4 sm:gap-0 sm:mb-4">
        <NavCategories></NavCategories>
        <Filter :products="productStore.products" class="sm:absolute z-10 sm:right-0 mx-6 sm:mr-12 md:mr-24"></Filter>
    </div>
    
    <router-view></router-view>

</template>

<script>
import bannersv2 from '../assets/bannersv2.png';
import bannersv1 from '../assets/bannersv1.png';
import SearchBar from "../components/SearchBar.vue";
import Countdown from "../components/Countdown.vue";
import NavCategories from '../components/NavCategories.vue';
import AllProducts from './AllProducts.vue';
import MenCothing from './MenCothing.vue';
import WomanClothing from './WomanClothing.vue';
import Jewelery from './Jewelery.vue';
import Electronics from './Electronics.vue';
import Filter from '../components/Filter.vue';
import { useProductsAllStore} from '../stores/productStore';
import ProductCard from '../components/ProductCard.vue';
import SearchResults from './SearchResults.vue';

export default {
    name : "Products",
    components: {
    SearchBar, Countdown, NavCategories, AllProducts, Jewelery, WomanClothing, MenCothing, Filter, Electronics, ProductCard, SearchResults
  },
    data(){
        return {
            banner2: bannersv1,
            banner3: bannersv2,
        }
    },
    computed:{
        productStore(){
            return useProductsAllStore();
        },},}
</script>

<style>
    
</style>
