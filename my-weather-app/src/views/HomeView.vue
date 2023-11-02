<template>
  <main class="container text-white">
    <div class="pt-4 mb-8 relative">
      <input 
        type="text" 
        v-model="searchQuery"
        placeholder="Search for a city or state" 
        class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-primary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
    </div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      searchQuery: "",
      queryTimeout: null,
    }
  },
  methods:{
    getSearchResults() {
      this.queryTimeout = setTimeout(() => {
        if (this.searchQuery !== "") {
          const result = axios.get(
            `http://api.openweathermap.org/geo/1.0/direct?q=${city_name},${state_code},${country_code}&appid=${API_key}`
          )
        }
      }, 300)
    }
  } 
}
</script>