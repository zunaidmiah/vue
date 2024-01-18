<template>
  <mainHeader></mainHeader>
  <div class="container p-4 m-4">
    <h1>{{ name }}</h1>
        <h2>{{ Age }}</h2>
        <h3>{{ Girlfriend }}</h3>
        <button class="btn btn-secondary m-2" @click="makeLove">Love</button><br>
        <button v-show="showPopupBtn" class="btn btn-info m-2" @click="popupValue">Show Popup</button>
        <Popup v-show="showPopup" @closePopup="popupValueReturn"/>
        <Child1/>
        <Table></Table>
        <Form></Form>
    <Card></Card>
    <Card>
        <h2>Hello From Passing Content</h2>
        <h3>Hello From Another Passing Content</h3>
    </Card>
    <Card>
        <img src="https://picsum.photos/200/300" alt="" height="400" width="600"/>
    </Card>
    



    <!-- Card for Zunaid and Tithy -->
    <Card>
        <template v-slot:card-header>
            <img class="card-img-top" :src="zunaidImage" alt="Card image cap">
        </template>
        <template v-slot:default>
            <div class="card-body">
                <h5 class="card-title">{{ name }}</h5>
                <p class="card-text">{{ zunaidInfo }}</p>
            </div>
        </template>
        <template v-slot:card-footer>
            <div class="card-footer">
                <a :href="zunaidLink" class="btn btn-primary">Go Facebook</a>
            </div>
        </template>
    </Card>


    <Card>
        <template v-slot:card-header>
            <img class="card-img-top" :src="tithyimage" alt="Card image cap">
        </template>
        <template v-slot:default>
            <div class="card-body">
                <h5 class="card-title">{{ Girlfriend }}</h5>
                <p class="card-text">{{ tithyInfo }}</p>
            </div>
        </template>
        <template v-slot:card-footer>
            <div class="card-footer">
                <a :href="tithyLink" class="btn btn-primary">Go Facebook</a>
            </div>
        </template>
    </Card>

    <!-- End card for Zunaid and Tithy section -->

    <!-- multiple dynamic component secrtion -->
    <!-- tab A, tab B and tab C-->
    <teleport to='#another-app'>
      <button class="btn btn-primary mr-1"  @click="activeTab = 'TabA'">Tab A</button>
      <button class="btn btn-primary mr-1"  @click="activeTab = 'TabB'">Tab B</button>
      <button class="btn btn-primary mr-1"  @click="activeTab = 'TabC'">Tab C</button>
      <keep-alive>
        <component :is="activeTab"/>
      </keep-alive>
    </teleport>
    <!-- <TabA v-if="activeTab === 'TabA'"/>
    <TabB v-if="activeTab === 'TabB'"/>
    <TabC v-if="activeTab === 'TabC'"/> -->


    <!-- End multiple dynamic component secrtion -->
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
import TabA from "./Components/layout/TabA.vue";
import TabB from "./Components/layout/TabB.vue";
import TabC from "./Components/layout/TabC.vue";
export default {
  data() {
    return {
      name: "Zunaid Miah",
      Age: 25,
      Girlfriend: "Tithy",
      showPopup: false,
      showPopupBtn: true,
      zunaidImage:'https://scontent.fdac7-1.fna.fbcdn.net/v/t39.30808-6/318456299_3300766590182779_1141951878137864247_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=efb6e6&_nc_eui2=AeF8c3gSWcjakXIznNxznWMhN3KwUIao48Y3crBQhqjjxiEJHRMQ_uJzqfXrTQA6w-IdXHvcq6NPF1dbbEia1Yaw&_nc_ohc=v4Lnz9FvKVIAX-OsFkx&_nc_ht=scontent.fdac7-1.fna&oh=00_AfB6xVtvOxOMoaj11siBbS8lLlJgB0zmyXaDSca2_N2Rwg&oe=65A9C113',
      tithyimage:'https://scontent.fdac7-1.fna.fbcdn.net/v/t39.30808-6/400446033_302609915982303_2934473984931277004_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=efb6e6&_nc_eui2=AeGT3ZAo4Rzftg1iZIaGJ5WMHsbdF4xqEiMext0XjGoSI8GZNNfmFXxogkXBVT0Eupu0JvbqAHkeSd3CqHuMqMn-&_nc_ohc=lA6C7DS7ZhYAX8z2mmt&_nc_ht=scontent.fdac7-1.fna&oh=00_AfDPzJjRvOmGF4Ok4bLEm3NS2CZVU2oJm4hgrXLJQSIhqg&oe=65A98221',
      zunaidLink: 'https://www.facebook.com/zunaidmiah1',
      zunaidInfo: 'Hi, This is Zunaid Miah. He is a Software Engineer and having 3 Years+ experience to work on this field. Curenntly He is doing a full time job on a Company.',
      tithyInfo: 'Hi, This is Samima Akter Tithy. She is a Software Engineer and having 1 Years+ experience to work on this field. Curenntly She is learning and make her expert onn that field.',
      tithyLink: 'https://www.facebook.com/samimaaktertithy789',
      activeTab: 'TabA'
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
    TabA,
    TabB,
    TabC
  },

  provide() {
    return {
      userName: this.name,
      Age: this.Age,
    };
  },
};
</script>
