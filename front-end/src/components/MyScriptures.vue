<template>
  <div>
    <h1>All Ponderize Scriptures</h1>
    <router-link v-for="scripture in scriptures" :key="scripture._id" :to="'/focus/' + scripture._id" class="flex-parent">
      <PreviewCard :scripture="scripture" class="flex-child" />
    </router-link>
    <p v-if="scriptures.length === 0">You don't have any scriptures to ponderize.  
      <router-link to="/add">Add</router-link> one now!
    </p>
  </div>
</template>

<script>
  import PreviewCard from './PreviewCard.vue';
  import axios from 'axios';

  export default {
    name: 'MyScriptures',
    components: {
        PreviewCard
    },
    created() {
      this.getScriptures();
    },
    methods: {
      async getScriptures() {
        try {
          const response = await axios.get("/api/scriptures");
          this.$root.$data.scriptures = response.data;
        } catch (error) {
          console.log(error);
        }
      }
    },
    computed: {
      scriptures() {
        return this.$root.$data.scriptures;
      }
    }
  }
</script>