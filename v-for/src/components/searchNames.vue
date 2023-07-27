<template>
  
  {{ blablabla() }}
  <h2  >Поиск имен</h2>
  <br>
  <input v-on:input="serchNames($event.target.value)" type="text" placeholder="имя">

  {{ showMainString }}
  {{ showLength }}
  <br>
  <ul>
    <li v-for="item in namesToShoe" :key="item">
      {{ item }}
    </li>
  </ul>



</template>

<script>
export default {
  name: 'searchNames',
  data(){
    return{
      namesToShoe:[],
      names:[
        {fName:'Петя'},
        {fName:'Вова'},
        {fName:'Коля'},
        {fName:'Петя'},
        {fName:'Рома'},
        {fName:'Вова'},
      ],
      totalnames:0,
      sameNames:0,
    }
    
  },

  computed:{
    showMainString(){
      return `Всего имен: ${this.totalnames}. Совпадений : ${this.sameNames}`
    },
    
  },
  methods:{
      blablabla(){
        this.totalnames = this.names.length;
      },
      serchNames(name){
        this.namesToShoe.length = 0;
        this.sameNames =0;
        for(let x of this.names){
          if(x.fName.toLocaleUpperCase() == name.toLocaleUpperCase()) {
            this.namesToShoe.push(x.fName);
            this.sameNames++;
          }
        }
        console.log(JSON.stringify( this.namesToShoe));
    }
  }
  
}
</script>


<style scoped>



</style>
