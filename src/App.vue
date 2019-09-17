<template>
  <div id="app">
    <Nav />
    <div class="placeholder">
      <h4>Role 101</h4>
      <p>Project title</p>
    </div>
    
      <b-tabs content-class="mt-0">
        <b-tab title="Candidates" active>
          <b-container>
            <Candidates v-bind:candidates="candidates" v-on:clickOnBtn="handleClickOnBtn" />
          </b-container>
        </b-tab>
        <b-tab title="Funnel">
          <b-container>
            <Funnel v-bind:candidates="candidates" />
          </b-container>
        </b-tab>
        <b-tab title="Settings"><p>I'm a settings tab!</p></b-tab>
      </b-tabs>
    
  </div>
</template>

<script>
import Nav from './components/Nav';
import Candidates from './components/Candidates.vue';
import Funnel from './components/Funnel.vue';

export default {
  name: 'app',
  components: {
    Nav,
    Candidates,
    Funnel
  },
  methods: {
    handleClickOnBtn(obj) {
      if (obj.event === 'save') {
        this.candidates.map( candidate => {
          if (candidate.id === obj.id) {
            candidate.saved = true;
          }
        });
      }
      if (obj.event === 'reject') {
        this.candidates.map( candidate => {
          if (candidate.id === obj.id ) {
            candidate.rejected = true;
          }
        })
      }
    }
  },
  data() {
    return {
      candidates: [
        {
          "id": 1,
          "firstname": "Leanne",
          "lastname": "Graham",
          "username": "Bret",
          "email": "Sincere@april.biz",
          "address": {
            "street": "Kulas Light",
            "suite": "Apt. 556",
            "city": "Gwenborough",
            "zipcode": "92998-3874",
            "geo": {
              "lat": "-37.3159",
              "lng": "81.1496"
            }
          },
          "phone": "1-770-736-8031 x56442",
          "website": "hildegard.org",
          "company": {
            "name": "Romaguera-Crona",
            "catchPhrase": "Multi-layered client-server neural-net",
            "bs": "harness real-time e-markets"
          },
          "rejected": false,
          "saved": false,
          "selection": false,
          "backup": false,
          "recos": false
        },
        {
          "id": 2,
          "firstname": "Ervin",
          "lastname": "Howell",
          "username": "Antonette",
          "email": "Shanna@melissa.tv",
          "address": {
            "street": "Victor Plains",
            "suite": "Suite 879",
            "city": "Wisokyburgh",
            "zipcode": "90566-7771",
            "geo": {
              "lat": "-43.9509",
              "lng": "-34.4618"
            }
          },
          "phone": "010-692-6593 x09125",
          "website": "anastasia.net",
          "company": {
            "name": "Deckow-Crist",
            "catchPhrase": "Proactive didactic contingency",
            "bs": "synergize scalable supply-chains"
          },
          "rejected": false,
          "saved": false,
          "selection": false,
          "backup": false,
          "recos": false
        },
        {
          "id": 3,
          "firstname": "Clementine",
          "lastname": "Bauch",
          "username": "Samantha",
          "email": "Nathan@yesenia.net",
          "address": {
            "street": "Douglas Extension",
            "suite": "Suite 847",
            "city": "McKenziehaven",
            "zipcode": "59590-4157",
            "geo": {
              "lat": "-68.6102",
              "lng": "-47.0653"
            }
          },
          "phone": "1-463-123-4447",
          "website": "ramiro.info",
          "company": {
            "name": "Romaguera-Jacobson",
            "catchPhrase": "Face to face bifurcated interface",
            "bs": "e-enable strategic applications"
          },
          "rejected": false,
          "saved": false,
          "selection": false,
          "backup": false,
          "recos": false
        },
        {
          "id": 4,
          "firstname": "Patricia",
          "lastname": "Lebsack",
          "username": "Karianne",
          "email": "Julianne.OConner@kory.org",
          "address": {
            "street": "Hoeger Mall",
            "suite": "Apt. 692",
            "city": "South Elvis",
            "zipcode": "53919-4257",
            "geo": {
              "lat": "29.4572",
              "lng": "-164.2990"
            }
          },
          "phone": "493-170-9623 x156",
          "website": "kale.biz",
          "company": {
            "name": "Robel-Corkery",
            "catchPhrase": "Multi-tiered zero tolerance productivity",
            "bs": "transition cutting-edge web services"
          },
          "rejected": false,
          "saved": false,
          "selection": false,
          "backup": false,
          "recos": false
        },
        {
          "id": 5,
          "firstname": "Chelsey",
          "lastname": "Dietrich",
          "username": "Kamren",
          "email": "Lucio_Hettinger@annie.ca",
          "address": {
            "street": "Skiles Walks",
            "suite": "Suite 351",
            "city": "Roscoeview",
            "zipcode": "33263",
            "geo": {
              "lat": "-31.8129",
              "lng": "62.5342"
            }
          },
          "phone": "(254)954-1289",
          "website": "demarco.info",
          "company": {
            "name": "Keebler LLC",
            "catchPhrase": "User-centric fault-tolerant solution",
            "bs": "revolutionize end-to-end systems"
          },
          "rejected": false,
          "saved": false,
          "selection": false,
          "backup": false,
          "recos": false
        }
      ]
    }
  }
}
</script>

<style>
  .placeholder {
    padding: 15px;
    background-color: #f3f3f3;
  }

  .placeholder h4 {
    margin: 10px 0;
  }

  .placeholder p {
    margin: 10px 0;
  }

  .nav-tabs {
    background-color: #f3f3f3;
  }

  .nav-item a {
    color: #666666;
  }
</style>
