<template>
  <div id="app">
    <div class='timetable-container'>
      <h5>
        <strong>Calling at:</strong>
      </h5>
      <vue-train-timetable
        :timetable="list"
        :maximum_display='maximum_display'
        :minimum_display='minimum_display'
        :direction='direction'
        :position="position"/>
    </div>
    <div class='timetable-control'>
      <div class='form-control'>
        <label>position</label>
        <input type="number" step='1' v-model="position">
      </div>
      <div class='form-control'>
        <label>minimum_display</label>
        <input type="number" step='1' v-model="minimum_display">
      </div>

      <div class='form-control'>
        <label>maximum_display</label>
        <input type="number" step='1' v-model="maximum_display">
      </div>

      <div class='form-control'>
        <input type="radio" value="horizontal" v-model="direction">
        <label>horizontal</label>
        <input type="radio" value="vertical" v-model="direction">
        <label>vertical</label>
      </div>

    </div>
  </div>
</template>

<script>
import VueTrainTimetable from "../src/train_time_table.vue";

export default {
  components: {
    VueTrainTimetable
  },
  computed: {
    containerWidth() {
      // return this.direction == "horizontal" ? "500px" : "200px";
    }
  },
  data() {
    return {
      // sub_title: "1st train"
      maximum_display: 11,
      minimum_display: 2,
      position: 0,
      direction: "vertical",
      list: [
        {
          name: "London St Pancras International"
        },
        {
          name: "London Bridge"
        },
        {
          name: "Norwood Junction"
        },
        {
          name: "East Croydon"
        },
        {
          name: "Coulsdon South"
        },
        {
          name: "Merstham"
        },
        {
          name: "Redhill"
        },
        {
          name: "Gatwick Airport",
          icon: "airport"
        },
        {
          name: "Three Bridges"
        },
        {
          name: "Crawley"
        },
        {
          name: "Ifield"
        },
        {
          name: "Faygate"
        },
        {
          name: "Littlehaven"
        },
        {
          name: "Horsham"
        }
      ]
    };
  }
};
</script>

<style>
html {
  background-color: black;
  font-family: Arial, Helvetica, sans-serif;
}
.timetable-container {
  width: 300px;
  height: 300px;
  margin: 0px auto 100px;
}
.timetable-control {
  color: #fff;
  width: 300px;
  margin: 0px auto;
}
.form-control input {
  border-radius: 3px;
  outline: none;
  border: 1px solid #ddd;
  padding: 5px 3px;
  font-size: 14px;
}

.form-control {
  margin: 15px 0;
}

h5 {
  color: #fff;
  margin: 10px 0 0;
}
</style>
