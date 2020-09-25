<template>
  <div>
    <b-container fluid class="bv-row mb-4">
      <input class="key mr-3" type="text"  v-model="keyword" /> 
      <button class="search"  @click="searchData()"
      >  Search Music  </button>

    </b-container>

    <b-container fluid class="bv-row">
      <b-row align-h="around mr-4 ml-4">
        <b-card
          v-for="data in resultData"
          :key="data.trackId"
          :title="data.trackName"
          :img-src="data.artworkUrl60"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem"
          class="mb-2"
        >
          <audio controls>
            <source :src="data.previewUrl" type="audio/mpeg" />
          </audio>
          <b-button :href="data.trackViewUrl" variant="dark"
            >Go preview</b-button >
        </b-card>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Axios from "axios";
export default {
  data() {
    return {
      resultData: null,
      keyword: "",
    };
  },
  methods: {
    searchData() {
      console.log("searchData");
      Axios.get("https://itunes.apple.com/search?term=" + this.keyword + "")
        .then((response) => {
          this.resultData = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>
<style>
  .key{
    width: 700px;
    height: 50px;
    font: 2em sans-serif;
    color: #47acff;
    border: 2px solid #11df89;
    box-shadow: none;
    border-radius: 24px;
  }
  .search{
    height: 50px;
    font: 2em sans-serif;
    color: rgb(194, 111, 3);
    border: 2px solid #e6217c;
    box-shadow: none;
    border-radius: 24px;
    
  }

</style>