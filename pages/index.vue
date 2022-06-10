<template>
  <div>
    <HeaderComponent></HeaderComponent>
    <h1> Page {{title}} </h1>
    <p> List Animals </p>
    <ul>
      <li v-for="animal, index in arrayListAnimals" :key="index">
        <template v-if="animal.showId" >
          {{animal.name}}, id- {{animal.id}}
        </template>
        <div v-else style="color: crimson; font-weight: bold">
          {{animal.name}}
        </div>
      </li>
    </ul>
    <ul>
      <li v-show="isShowList" v-for="car, index in arrayListCars" :key="index">
        <template v-if="car.showId" >
          {{car.name}}, id- {{car.id}}
        </template>
        <div v-else style="color: crimson; font-weight: bold">
          {{car.name}}
        </div>
      </li>
    </ul>
    <button @click="onShowCars">Show/Hide cars</button>
    <ListComponent></ListComponent>
  </div>
</template>

<script>
  import Component, {namespace} from 'nuxt-class-component';
  import {Vue, Prop} from "vue-property-decorator";

  export default @Component({
    components: {  },
  })

  class Index extends Vue {
    title = 'Home';
    isShowList = false;
    arrayListAnimals = [
      {id: 1, name: 'Cat', showId: true},
      {id: 2, name: 'Dog', showId: true},
      {id: 3, name: 'Elephant', showId: true},
      {id: 4, name: 'Tiger', showId: false},
      {id: 5, name: 'Lion', showId: true},
      {id: 5, name: 'Lion', showId: false}
    ];
    arrayListCars = [
      {id: 1, name: 'Tesla', showId: true},
      {id: 2, name: 'Ferarri', showId: false},
      {id: 3, name: 'BMV', showId: true},
    ];
    onShowCars(){
      this.isShowList = !this.isShowList;
    };
  }
</script>
