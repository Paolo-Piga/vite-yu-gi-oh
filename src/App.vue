<script>
  // importo axios
  import axios from 'axios';

  //importo api, Appheader e AppMain
  import { store } from './api';
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';

  // esporto e definisco Appheader e Appmain
  export default{
    components :{
      AppHeader,
      AppMain,
    },

    data(){
      return {
        store,
      }
    },
    // funzione per estrapolare i dati dell'API utilizzando Axios
    methods : {
      GetCardInfo(){
        axios.
        // riporto i dati nell'array
        get(store.apiURL)
        .then(res => {
          console.log(res.data.data);
          store.cardList = res.data.data;
          console.log('store' + store.cardList)
        })
        
      }
    },
    created(){
      
      this.GetCardInfo();
    }
  }

</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss" scoped>

@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;
@use './styles/partials/mixins' as *; 
</style>