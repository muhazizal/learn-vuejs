<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Filters & Mixins</h1>
        <p>{{ name | toUppercase | toLowercase }}</p>
        <hr />
        <input type="text" v-model="filteredText" />
        <ul>
          <li v-for="item in filteredItems" :key="item">{{ item }}</li>
        </ul>
        <hr />
        <app-list></app-list>
      </div>
    </div>
  </div>
</template>

<script>
import { itemsMixin } from "./itemsMixin";
import ListVue from "./List.vue";

export default {
  mixins: [itemsMixin],
  data() {
    return {
      name: "Muhammad Aziz"
    };
  },
  components: {
    "app-list": ListVue
  },
  filters: {
    toUppercase(value) {
      return value.toUpperCase();
    }
  },
  created() {
    console.log("Created inside App vue");
  }
};
</script>

<style>
</style>
