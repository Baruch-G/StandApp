<template>
  <div id="page" class="card mb-3">
    <img :src="pic" alt="Card image cap" />
    <div class="card-body">
      <h5 class="card-title">{{title}}</h5>
      <p class="card-text">
        {{desc}}
      </p>
      <p class="card-text">
        <small class="text-muted">Last updated 3 mins ago</small>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "StandUpRunSinglePage",
  data() {
    return {
      pic1:
        "https://images.auto.co.il/Attachment/Gallery/240316/1606183/DBS%2059%20%286%29.jpg?width=556",
    };
  },
  props : {
    title : String,
    desc : String,
    pic : String
  },
  mounted() {
    //document.body.className = "block";
    // document.body.classList.remove("block");
  },
};
</script>

<style scoped>
img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin-top: -50px;
  position: fixed;
  object-fit: cover;
  box-shadow: 0px 15px 8px -5px rgb(158, 158, 158);
  align-self: center !important;
}

#page {
  height: 100% !important;
  width: 100% !important;
  background-color: #17a2b8;
  
}
.card-body{
  margin-top: 150px;
  height: 100% !important;
  color : white !important;
}
.card-title {
  font-size : 30px !important;
  color : white !important;
}
</style>