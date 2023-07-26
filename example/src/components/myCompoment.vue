<template>
    <div class="root">
        

        <button  v-on:click="minus" >-</button>
        <input  v-model="inputValue" type="number" max="10" min="1">
        <button  v-on:click="plus" >+</button>




        <!-- <input type="text" placeholder="Ваше имя" @input="getNameValue($event.target.value)">
        <input type="text" placeholder="Ваша фамилия" @input="getLNameValue($event.target.value)">
        <input type="text" placeholder="Ваш возраст" @input="getAgeValue($event.target.value)">


        <h2>Меня зовут:{{ firstName }}</h2>
        <h2>Моя фамилия:{{ lastName }}</h2>
        <h2>Мне:{{ age }}</h2> -->



    </div>
</template>


<script>
export default {
    name:'MyCompoment',
    data() {
        return{
            // firstName:'',
            // lastName:'',
            // age:'',
            inputValue:1,
        }
    },
    methods:{
        // getNameValue(event){this.firstName = event},
        // getLNameValue(event){this.lastName = event},
        // getAgeValue(event){this.age = event},

        minus(){
            if(this.inputValue<2) return;
            this.inputValue -= 1;
        },
        plus(){
            if(this.inputValue>9) return;
            this.inputValue +=1;
        },
    }
    
}


</script>