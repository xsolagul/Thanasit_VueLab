<template>
  <div class="grid grid-cols-2 gap-4 border-black">
    <div class="ml-10 mr-0">
      <h1>Manufacturer</h1>
      <ul
        class="border border-black"
        v-for="manufacture in manufacturer"
        :key="manufacture.id"
      >
        <li>
          <button v-on:click="changeManufacturerId(manufacture.id)">
            <img :src="manufacture.Logo" width="100" />
          </button>
        </li>
      </ul>
    </div>
    <div>
      <slot :factId="currentManufactID"></slot>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'manufacturer',
  data() {
    return {
      currentManufactID: 0,
      manufacturer: [
        { id: 1, Title: 'Asus' },
        { id: 2, Title: 'Dell' },
      ],
    };
  },
  watch: {
    manufactureId: function (newId, oldId) {
      console.log(newId, '|', oldId);
    },
  },
  created() {
    this.getManufacturer();
  },
  methods: {
    changeManufacturerId(id) {
      this.currentManufactID = id;
    },
    async getManufacturer() {
      // axios.get('https://demo.yume-dev.me/manufacturers').then((res) => {
      //   console.log(res);
      // });
      const res = await axios.get('https://demo.yume-dev.me/manufacturers');
      console.log(res.data);
      this.manufacturer = res.data;
    },
  },
};
</script>

<style></style>
