<template>
  <div id="app">
    <input type="text" v-model="text" placeholder="Text">
    <button @click="generatePDF">Generate PDF</button>
  </div>
</template>

<script>
import jspdf from "jspdf";
// import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  data() {
    return {
      text: null
    };
  },
  methods: {
    generatePDF() {
      const doc = new jspdf();
      doc.text(this.text, 15, 5);
      doc.text("KOP", 15, 10);

      doc.save("test.pdf");
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
