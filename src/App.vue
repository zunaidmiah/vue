<template>
  <mainHeader></mainHeader>
  <div class="container p-4 m-4">
    <!-- <h1>{{ name }}</h1>
        <h2>{{ Age }}</h2>
        <h3>{{ Girlfriend }}</h3>
        <button class="btn btn-secondary m-2" @click="makeLove">Love</button><br>
        <button v-show="showPopupBtn" class="btn btn-info m-2" @click="popupValue">Show Popup</button>
        <Popup v-show="showPopup" @closePopup="popupValueReturn"/>
        <Child1/>
        <Table></Table>
        <Form></Form> -->
    <Card></Card>
    <Card>
        <h2>Hello From Passing Content</h2>
        <h3>Hello From Another Passing Content</h3>
    </Card>
    <Card>
        <img src="https://picsum.photos/200/300" alt="" height="400" width="600"/>
    </Card>
  </div>
  <mainFooter :name="name"></mainFooter>
</template>

<script>
import Header from "./Components/main/header.vue";
import Footer from "./Components/main/footer.vue";
import Table from "./Components/layout/table.vue";
import Form from "./Components/layout/form.vue";
import Child1 from "./Components/layout/child1.vue";
import Popup from "./Components/layout/Popup.vue";
import Card from "./Components/layout/Card.vue";
export default {
  data() {
    return {
      name: "Zunaid Miah",
      Age: 25,
      Girlfriend: "Tithy",
      showPopup: false,
      showPopupBtn: true,
    };
  },

  methods: {
    makeLove() {
      if (this.name == "Zunaid Miah") {
        this.name = this.name + "+" + this.Girlfriend;
      }
    },
    popupValue() {
      (this.showPopup = true), (this.showPopupBtn = false);
    },
    popupValueReturn(fName, lName) {
      (this.showPopup = false),
        (this.showPopupBtn = true),
        console.log("First name ", fName);
      console.log("Last name ", lName);
    },
  },

  components: {
    mainHeader: Header,
    mainFooter: Footer,
    Table,
    Form,
    Child1,
    Popup,
    Card,
  },

  provide() {
    return {
      userName: this.name,
      Age: this.Age,
    };
  },
};
</script>
