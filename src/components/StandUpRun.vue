<template>
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li
        v-for="(item, index) in cards"
        :key="item.title"
        data-target="#carouselExampleIndicators"
        :data-slide-to="index"
        :class="item.IsActive ? 'active' : ''"
      ></li>
    </ol>
    <div class="carousel-inner">
      <div
        v-for="card in cards"
        :key="card.title"
        :class="card.IsActive ? 'carousel-item active' : 'carousel-item'"
      >
        <stand-up-page 
        :title="card.title" 
        :desc="card.desc"
        :pic="card.pic"
        ></stand-up-page>
      </div>
    </div>
    <a
      class="carousel-control-prev"
      role="button"
      data-slide="prev"
      v-on:click="prev()"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      role="button"
      data-slide="next"
      v-on:click="next()"
    >
      <span class="carousel-control-next-icon arr" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
import standUpPage from "./StandUpRunSinglePage";
export default {
  components: {
    standUpPage,
  },
  name: "StandUpRun",
  mounted() {
    //document.body.className = "block";
    // console.log(this.cards[this.index])
    this.cards[this.index].IsActive = true;
  },
  methods: {
    next() {
      if (this.cards.length > this.index + 1) {
        this.cards[this.index].IsActive = false;
        this.index++;
        this.cards[this.index].IsActive = true;
      }
    },
    prev() {
      if (this.index - 1 >= 0) {
        this.cards[this.index].IsActive = false;
        this.index--;
        this.cards[this.index].IsActive = true;
      }
    },
  },
  data() {
    return {
      index: 0,
      cards: [
        {
          title: "הארי בין",
          desc:
            "111 This is a wider card with supporting text below as natural lead-in to additional content. This content is a little bit longer.",
          IsActive: false,
          pic: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQbsgqE3iXr_UTBpkO-16MBn16IS4B6_091lQ&usqp=CAU",
        },
        {
          title: "איינשטיין",
          desc: "222",
          IsActive: false,
          pic: "https://fsa.zobj.net/crop.php?r=66O_BRSSDL6VP5p0LoMxtknHG_iFKR1KjflTjMs84tcpjNOTD4MDhEWQljHNi7CKeboLAo7yBetkjHEFuehgsbjdYulRVsDZa-AH5SAixzz-Y17XjSVUKmhfCheLpRko9I51EK4oPDHlCbz2",
        },
        {
          title: "תינוקי חמודי",
          desc: "222",
          IsActive: false,
          pic: "https://www.dailymoss.com/wp-content/uploads/2019/08/funny-profile-pic33.jpg",
        },
      ]
    };
  },
};
</script>
<style scoped>
#carouselExampleIndicators {
  position: fixed;
  outline: 9999px solid rgba(0, 0, 0, 0.5);
  width: 90% !important;
  height: 90% !important;
  top: 50px;
  right: 50px;
  background-color: #17a2b8;
}
.arr {
}
</style>