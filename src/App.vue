<template>
  <div id="app">
    <md-card>
      <md-card-media-cover md-solid>
       <md-card-media md-ratio="1:1">
          <img src="https://vuematerial.io/assets/examples/card-sky.jpg" alt="Skyscraper" height="100">
        </md-card-media>
        <md-card-area>
          <md-card-header>
            <span class="md-title">Solid background</span>
            <span class="md-subhead">1/1 image</span>
          </md-card-header>

          <md-card-actions>
            <md-button class="md-icon-button">
              <md-icon>favorite</md-icon>
            </md-button>

            <md-button class="md-icon-button">
              <md-icon>share</md-icon>
            </md-button>
          </md-card-actions>
        </md-card-area>
      </md-card-media-cover>
    </md-card>


    <md-card>
      <md-card-header>
        <div class="md-title">
          Material Design With vuejs2 
        </div>
        <div class="md-subhead">
          by CodingTher
        </div>
      </md-card-header>
      
      <md-card-content>
        <md-button class="md-raised md-primary" v-on:click="fillTable()">Fill Table</md-button>
        <md-button class="md-raised md-primary" v-on:click="clearTable()">Clear Table</md-button>

      </md-card-content>
      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>First name</md-table-head>
            <md-table-head>Last name</md-table-head>
            <md-table-head>Email</md-table-head>
          </md-table-row>
        </md-table-header>
        <md-table-body>
          <md-table-row v-for="contact in contacts" v-bind:key="contact.firstname">
            <md-table-cell>{{contact.firstname}}</md-table-cell>
            <md-table-cell>{{contact.lastname}}</md-table-cell>
            <md-table-cell>{{contact.email}}</md-table-cell>
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>    
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  data: function() {
    return {
      contacts: []
    }
  },
  methods: {
    fillTable: function() {
      this.contacts.push({firstname: 'Leo', lastname:'min', email: 'mail@mail.com'});
      this.contacts.push({firstname: 'Leo', lastname:'min', email: 'mail@mail.com'});
      this.contacts.push({firstname: 'Leo', lastname:'min', email: 'mail@mail.com'});
    },
    clearTable: function () {
      this.contacts.splice(0, this.contacts.length);
    }
  }

}
</script>

<style>
.md-card {
  margin-top: 20px;
}

#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right:30px;
}
</style>
