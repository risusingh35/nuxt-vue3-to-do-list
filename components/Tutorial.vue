<template>
  <div>
    <h1>Hi! Welcome to TO-DO-List by Risu Singh</h1>
    <h1 class="head">
      Add Your City Name:
      <form @submit.prevent="addCity">
        <input v-model="newCityName" placeholder="Type Favorite City Name" />
        <button class="addbtn" type="submit">ADD City</button>
      </form>
    </h1>

    <h3>Total Added City in the List is {{ cityCount }}</h3>
    <div>
      <h2 v-for="(city, index) in myCityName" :key="city.name">
        <li class="item">
          {{ city.name }}
          <button class="xbtn" @click="removeCity(index)">X</button>
        </li>
      </h2>
    </div>
  </div>
</template>
<script>
export default {
  computed: {
    cityCount() {
      return this.myCityName.length + " City";
    },
  },

  methods: {
    addCity() {
      if (this.newCityName !== "") {
        // use unshift for adding at top or push for bottom
        this.myCityName.unshift({ name: this.newCityName });
        this.newCityName = "";
      } else {
        alert("Please add CIty Name First");
      }
    },
    removeCity(index) {
      // console.log(index);
      // this.myCityName.pop({name:this.newCityName});
      this.myCityName.splice(index, 1);
    },
  },
  data() {
    return {
      newCityName: "",
      // msg:"Hi msg",
      myCityName: [
        { name: "Paris" },
        { name: "Sinapore" },
        { name: "New Your" },
        { name: "Los Angeles" },
        { name: "Hong Kong" },
      ],
    };
  },
};
</script>

<style>
.xbtn {
  position: absolute;
  right: 1%;
  box-shadow: rgba(255, 255, 255, 0.35) 0px 5px 15px;
  border-radius: 50%;
  padding: 5px;
  border: none;
  background-color: #845EC2;
}
.item {
  background-repeat: no-repeat;
  background-image: linear-gradient(
    to left top,
    #d16ba5,
    #c777b9,
    #ba83ca,
    #aa8fd8,
    #9a9ae1,
    #8aa7ec,
    #79b3f4,
    #69bff8,
    #52cffe,
    #41dfff,
    #46eefa,
    #5ffbf1
  );
  padding: 15px 30px;
  border-radius: 10px;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px,
    rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
  position: relative;
  padding: 15px 0px 15px 10px;
}

input {
  margin: 0 0 0 50px;
}
input:focus {
  background-color: burlywood;
}
.addbtn:hover {
  background-color: chartreuse;
}
.addbtn {
  margin: 0 0 0 15px;
}

input,
.addbtn {
  padding: 15px;
  outline: none;
  border-radius: 10px;
  border: none;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px,
    rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
}
h1 {
  padding: 5%;
  border-radius: 10px;
  border: none;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px,
    rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
  color: #845EC2;
}
h1.head {
  display: flex;
  background-color: #845EC2;
  color: aqua;
  border-radius: 10px;
  border: none;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px,
    rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
  padding: 5%;
}
</style>
