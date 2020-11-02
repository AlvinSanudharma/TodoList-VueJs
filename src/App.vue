<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div class="container">
      <div class="row header p-3 mb-4">
        <div class="col-lg-12 text-center">
          <div class="header-title">
            <a href="#">
              <img
                src="./assets/logo.png"
                alt=""
                width="50px"
                height="50px"
              />Apa Yang Saya Lakukan Hari Ini?</a
            >
          </div>
        </div>
      </div>
      <div class="row content">
        <div class="col-lg-12">
          <div class="homework">
            <div class="row">
              <div
                class="tasks col-lg-12 mb-3 text-left"
                v-for="myWork in work"
                :key="myWork.id"
              >
                <div class="form-check">
                  <input
                    class="form-check-input"
                    type="checkbox"
                    id="defaultCheck1"
                    v-model="myWork.isDone"
                  />
                  <label
                    class="form-check-label item"
                    for="defaultCheck1"
                    v-bind:class="{ completed: myWork.isDone }"
                  >
                    {{ myWork.name }}
                  </label>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import "bootstrap/dist/css/bootstrap.css";

export default {
  name: "App",
  data: function() {
    return {
      work: [
        {
          id: 1,
          name: "Makan",
          isDone: false,
        },
        {
          id: 2,
          name: "Main Game",
          isDone: false,
        },
        {
          id: 3,
          name: "Belajar",
          isDone: false,
        },
        {
          id: 4,
          name: "Istirahat",
          isDone: false,
        },
      ],
    };
  },
  components: {
    // HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* .header {
  background-color: #1abc9c;
} */
.header-title a {
  text-decoration: none;
  color: #000000;
}
.tasks .item {
  font-size: 16px;
}
.completed {
  text-decoration: line-through;
}
</style>
