<template>
  <section id="1">
    <Header />
    <a href="#2" id="scroll"
      ><span
        style="
          position: absolute;
          top: 15%;
          left: 50%;
          width: 24px;
          height: 24px;
          margin-left: -12px;
          border-left: 1px solid #fff;
          border-bottom: 1px solid #fff;
          -webkit-transform: rotate(-45deg);
          transform: rotate(-45deg);
          box-sizing: border-box;
        "
      ></span
      >Scroll Down</a
    >
  </section>

  <section id="2">
    <h3 style="display: flex;align-items: center;
  justify-content: center;">Note: Please First Download - &nbsp;<a href="https://chrome.google.com/webstore/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf" target="_blank"><em>  Allow CORS: Access-Control-Allow-Origin &nbsp; </em></a>to run the root cause of Microservices</h3>
    <div id="nav">
      <div id="link">
        <router-link to="/ui"
          ><button id="link-button">
            Find Root Cause Analysis of Bookshop-ui
          </button></router-link
        >

        <router-link to="/books"
          ><button id="link-button">
            Find Root Cause Analysis of Bookshop-books
          </button></router-link
        >

        <router-link to="/purchases"
          ><button id="link-button">
            Find Root Cause Analysis of Bookshop-purchases
          </button></router-link
        >
      </div>
    </div>
  </section>
  <router-view />
</template>
<script>
import Header from "./components/Header.vue";
export default {
  name: "App",
  components: {
    Header,
  },
};
</script> 
<style scoped>
#scroll {
  padding-top: 60px;
  position: absolute;
  bottom: 15%;
  left: 47%;
  z-index: 2;
  display: inline-block;
  -webkit-transform: translate(0, -50%);
  transform: translate(0, -50%);
  color: #fff;
  font: normal 400 20px/1 "Josefin Sans", sans-serif;
  letter-spacing: 0.1em;
  text-decoration: none;
  transition: opacity 0.3s;
}

#link-button {
  appearance: none;
  height: 70px;
  margin-left: 50px;
  outline: 0;
  background-color: #227fbd;
  border-radius: 25px;
  border: 2px solid black;
  padding: 10px 15px;
  color: white;
  border-radius: 3px;
  width: 250px;
  cursor: pointer;
  font-size: 18px;
  transition-duration: 0.25s;
}
#link {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 25px;
}
@media only screen and (max-width: 600px) {
  #link {
    display: block;
  }
  #scroll {
    margin-top: 20px;
    bottom: 18%;
    left: 30%;
  }
  #link-button{
    margin-top:20px;
    margin-left:25px;
  }
}
</style>