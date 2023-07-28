<template>
    <div class="cat">

      <div class="cont">
        <img  v-if="isVisible" src="../assets/cat.png" :style="imdStyles" :class="imgFilters" alt="" srcset="">
        <h2>Фильтры</h2>
        <button  @click="imgFilters.sepia = !imgFilters.sepia" >Сепия</button>
        <button  @click="imgFilters.border = !imgFilters.border">Рамка</button>
        <button  @click="imgFilters.boxShadow = !imgFilters.boxShadow">Тень</button>
        
        <h2>размер</h2>
        <p>Ширина {{ currentWidth }}</p>
        <input v-on:input="currentWidth = $event.target.value" type="range" :max="640" >
        <p>Высота {{ currentHeight }}</p>
        <input v-on:input="currentHeight = $event.target.value" type="range" :max="480">

        <h2>Угол поворта {{ corner }}</h2>
        <input v-on:input="corner = $event.target.value" type="range" :max="360">


        <button @click = "isVisible = !isVisible">Спрятать</button>


      </div>

    </div>
</template>

<script>
export default {
  name: 'catStyle',
  data(){
    return{
      isVisible : true,
      currentWidth:640,
      currentHeight:480,
      corner:0,
      imgFilters:{
        sepia:false,
        border:false,
        boxShadow: false,
      }
    }
  },
  computed:{
    imdStyles(){
      return{
      width :`${this.currentWidth}px`,
      height :`${this.currentHeight}px`,
      transform:`rotate(${this.corner}deg)`,
      }
    },  
  }
}
</script>

<style scoped>
  img{
    width: 30%;
    transition: all 0.45s;
    float: left;
    margin-right: 20px;
  }

  .sepia{
    filter: sepia(1);
  }
  .border{
    border: 1px black solid;
    border-radius: 24px;
  }
  .boxShadow{
    box-shadow: 4px 4px 100px 1px black ;
  }

</style>
