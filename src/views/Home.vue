<template>
  <div>
    <h1>{{ title }}</h1>
    <h1>Home Page ( Welcome to World !! )</h1>
    <input type="text" v-model="input1" />
    <button type="button" @click="getData">{{ button1 }}</button>
    <button type="button" @click="setData">{{ button2 }}</button>

    <select class="form-control" v-model="region" @change="changeRegion">
      <option :key="i" :value="d.k" v-for="(d,i) in options">{{d.t}}</option>
    </select>


    <table class="table table-bordered" v-if="tableShow">
      <tr :key="i" v-for="(d,i) in options">
        <td>{{d.k}}</td>
        <td>{{d.t}}</td>
      </tr>
    </table>
  </div>
</template>
<script>
const log = console.log;
export default {
  data() {
    return {
      title: "홈 페이지 ... ",
      input1: "text box ... ",
      button1: "GET",
      button2: "SET",
      options: [
        { k: "S", t: "Seoul" },
        { k: "J", t: "Jeju" },
        { k: "K", t: "Kwangju" },
      ],
      region: "K",
      tableShow: false
    };
  },
  watch: {
    input1() {
      log(this.input1);
    },
  },
  methods: {
    getData() {
      alert(this.input1);
    },
    setData() {
      this.input1 = " input sample value ... ";
    },
    changeRegion() {
      if (this.region === "K") {
        this.tableShow = true;
      } else {
        this.tableShow = false;
      }
    }
  },
  beforeCreate() {
    // log("beforeCreate");
  },
  created() {
    // log("created");
  },
  beforeMount() {
    // log("beforeMount");
  },
  mounted() {
    // log("mounted");
  },
  beforeUpdate() {
    // log("beforeUpdate");
  },
  updated() {
    // log("updated");
  },
  beforeDesploy() {
    // 출력 데이더는 확인이 불가
    // log("beforeDesploy");
  },
  desployed() {
    // 출력 데이더는 확인이 불가
    // log("desployed");
  },
};
</script>