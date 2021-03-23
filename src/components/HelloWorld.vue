<template>
  <div>
    <h2>Filter Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <br />
    {{ query }}
    <br />
    <button @click="reset">Reset</button>
    <search-results :query="query" />
  </div>
</template>

<script>
import { ref } from 'vue';
import SearchResults from './SearchResults.vue';
export default {
  components: {
    SearchResults
  },
  setup() {
    const query = ref('');

    const reset = (evt) => {
      query.value = ''; // clears the query
    };

    return {
      query,
      reset
    };
  }
};
</script>
