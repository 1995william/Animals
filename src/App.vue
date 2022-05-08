<template>
  
  <GlobalTitle :title='LogoName'/>
  
  <ul>
    <!-- V-ForEach -->
   <HomeCard v-for="(el, i) in itens" :key="i" :item="el" />
  </ul>
</template>

<script>
import Axios from "axios";
import  GlobalTitle  from "@/components/Global/GlobalTitle.vue";
import HomeCard from "@/components/Home/HomeCard.vue";

export default {
  name: 'App',
  data(){
    return {
      LogoName: "Animals",
      itens: [],
    };
  },
  components: {
    GlobalTitle,
    HomeCard
},
async created() {
    const { data } = await Axios.get("https://zoo-animal-api.herokuapp.com/animals/rand/10");

    this.itens.push(...data);
  },


};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Sail&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

html,
body,
#app {
  width: 100%;
  height: 100%;
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}

ul {
  width: 80%;
  height: 100%;

  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;

  list-style: none;

  padding-bottom: 10px;
  padding-top: 10px;

  overflow-y: auto;
}

</style>
