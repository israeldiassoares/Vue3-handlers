<template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    {{ query }}
    <button @click="reset">Reset</button>
    <search-results :query="query" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { ref } from "vue";
import SearchResults from "./SearchResults.vue";
export default defineComponent({
  components: {
    SearchResults,
  },
  name: "HelloWorld",
  setup() {
    const query = ref("");
    const reset = (event: any): void => {
      query.value = ""; //clears the query
    };
    console.log("query", query);
    return {
      query,
      reset,
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
