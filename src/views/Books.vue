<template>
  <div class="list-row">
<h1> Bookshop Books</h1>
<div style="overflow-x:auto;">
<table id="table">
    <tr>
    <th>Microservice Name</th>
    <th>CPU</th>
    <th>Memory</th>
    <th>Root Cause</th>
  </tr>
    <tr v-for="microservice in microservices" v-bind:key="microservice.microservice_name">
        <td>{{ microservice.microservice_name }}</td>
        <td>{{ microservice.cpu }}</td>
        <td>{{ microservice.memory }}</td>
        <td>{{ microservice.root_cause }}</td>

    </tr>
    </table>
    </div>
  </div>
</template>

<script>

import axios from 'axios';
export default {
     
    name: "microservice",
    mounted: function () {
      this.getmicroservice()
      console.log('mounted: got here')
    },
    data: function () {
      return {
        message: 'Microservice List Row',
        microservices: []
      }
    },
    methods: {
  getmicroservice: function () {
    var self = this
    const url = 'https://rootcausemicroservice.azurewebsites.net/dbconfig/bookshop-books'
    axios.get(url, {
      dataType: 'json',
      headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json'
      },
      mode: 'no-cors',
      credentials: 'include'
    })
    .then(function (response) {
      console.log(JSON.stringify(response.data))
      self.microservices = response.data
    })
    .catch(function (error) {
      console.log(error)
    })
  }
}
}
</script>
<style>
#table {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

#table td, #table th {
  border: 1px solid #ddd;
  padding: 8px;
}

#table tr:nth-child(even){background-color: #f2f2f2;}

#table tr:hover {background-color: #ddd;}

#table th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #4352b9;
  color: white;
}
</style>