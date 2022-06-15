<template>
 
  <div class="backdrop" @click="closeModal">
    <div class="modal">
      <div v-if="!boot.name">
        <h1>{{ title }}</h1>
        <img v-bind:src="image" />
        <button class="mint" @click="mint">MINT</button>
      </div>
      <div v-else>
        <h1>{{ boot.name }}</h1>
        <img v-bind:src="boot.image"/>
        <p>{{ boot.status }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MyModal",
  data() {
    return {
      title: "Mystery Box",
      image:
        "https://www.clipartkey.com/mpngs/m/326-3261988_lament-configuration-sticker-sun-flower-clipart-in-black.png",
      boot: {},
      boots: [
        {
          image: "https://hypesneakrs.com/Grid-9.jpg",
          name: "HypeSneakr 1/30",
          status: "Gold",
        },
        {
          image: "https://hypesneakrs.com/Grid-8.jpg",
          name: "HypeSneakr 2/30",
          status: "Silver",
        },
        {
          image: "https://hypesneakrs.com/Grid-7.jpg",
          name: "HypeSneakr 3/30",
          status: "Bronse",
        },
        {
          image: "https://hypesneakrs.com/Grid-6.jpg",
          name: "HypeSneakr 4/30",
          status: "Gold",
        },
      ],
    };
  },
  methods: {
    mint() {
      let bootRan = this.boots[Math.floor(Math.random() * this.boots.length)];
      this.boot = bootRan;
    },
    closeModal() {
      this.$emit('close')
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  text-align: center;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}

.mint {
  width: 100%;
  height: 30px;
  border: black solid 1px;
  margin-top: 10px;
}

.modal>h1 {
  color: rgb(78, 177, 78);
  border: none;
  padding: 0;
}

.modal>div>img {
  width: 100%;
  height: 100%;
}

.backdrop {
  margin-left: -186px;
  top: 0;
  position: absolute;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
</style>
