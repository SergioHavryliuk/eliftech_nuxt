<template>
  <div>
    <HeaderComponent />
    <h1> Page {{ title }} </h1>
    <p> List Animals 10000</p>
    <ul>
      <li v-for="animal, index in arrayListAnimals" :key="index">
        <template v-if="animal.showId">
          {{ animal.name }}, id- {{ animal.id }}
        </template>
        <div v-else style="color: crimson; font-weight: bold">
          {{ animal.name }}
        </div>
      </li>
    </ul>
    <ul>
      <li v-for="car, index in arrayListCars" v-show="isShowList" :key="index">
        <template v-if="car.showId">
          {{ car.name }}, id- {{ car.id }}
        </template>
        <div v-else style="color: crimson; font-weight: bold">
          {{ car.name }}
        </div>
      </li>
    </ul>
    <button @click="onShowCars">
      Show/Hide cars
    </button>
    <ListComponent />
  </div>
</template>

<script>
import { Vue, Component } from 'nuxt-property-decorator';
import HeaderComponent from '../components/HeaderComponent';
import ListComponent from '../components/ListComponent';

export default @Component({
  components: { HeaderComponent, ListComponent }
})

class Index extends Vue {
  title = 'Home';
  isShowList = false;
  arrayListAnimals = [
    { id: 1, name: 'Cat', showId: true },
    { id: 2, name: 'Dog', showId: true },
    { id: 3, name: 'Elephant', showId: true },
    { id: 4, name: 'Tiger', showId: false },
    { id: 5, name: 'Lion', showId: true },
    { id: 5, name: 'Lion', showId: false }
  ];

  arrayListCars = [
    { id: 1, name: 'Tesla', showId: true },
    { id: 2, name: 'Ferarri', showId: false },
    { id: 3, name: 'BMV', showId: true }
  ];

  onShowCars () {
    this.isShowList = !this.isShowList;
  };
}
</script>
