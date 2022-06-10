<template>
  <div>
    <HeaderComponent />
    <h1> Page Contacts </h1>
    <ArticleComponent />
    <ButtonComponent />
  </div>
</template>

<script>
import { Vue, Component } from 'nuxt-property-decorator';
import HeaderComponent from '../components/HeaderComponent';
import ArticleComponent from '../components/ArticleComponent';
import ButtonComponent from '../components/ButtonComponent';

export default @Component({
  components: { HeaderComponent, ArticleComponent, ButtonComponent }
})

class Contacts extends Vue {}
</script>
