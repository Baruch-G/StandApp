<template>
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li
        v-for="(item, index) in members"
        :key="item.id"
        data-target="#carouselExampleIndicators"
        :data-slide-to="index"
        :class="index == active ? 'active' : ''"
      ></li>
    </ol>
    <!-- <div class="carousel-inner">
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
    </div> -->
    <div class="carousel-inner">
      <div
        v-for="(member, index) in members"
        :key="member.id"
        :class="index == active ? 'carousel-item active' : 'carousel-item'"
      >
        <stand-up-page
          :title="member.user.name"
          :desc="member.user.name"
          :pic="member.user.img"
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
    this.members[this.active].IsActive = true;
  },
  methods: {
    next() {
      if (this.members.length > this.active + 1) {
        this.members[this.active].IsActive = false;
        this.active++;
        this.members[this.active].IsActive = true;
      }
    },
    prev() {
      if (this.active - 1 >= 0) {
        this.members[this.active].IsActive = false;
        this.active--;
        this.members[this.active].IsActive = true;
      }
    },
  },
  data() {
    return {
      active: 0,
      cards: [
        {
          title: "הארי בין",
          desc:
            "111 This is a wider card with supporting text below as natural lead-in to additional content. This content is a little bit longer.",
          IsActive: false,
          pic:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQbsgqE3iXr_UTBpkO-16MBn16IS4B6_091lQ&usqp=CAU",
        },
        {
          title: "איינשטיין",
          desc: "222",
          IsActive: false,
          pic:
            "https://fsa.zobj.net/crop.php?r=66O_BRSSDL6VP5p0LoMxtknHG_iFKR1KjflTjMs84tcpjNOTD4MDhEWQljHNi7CKeboLAo7yBetkjHEFuehgsbjdYulRVsDZa-AH5SAixzz-Y17XjSVUKmhfCheLpRko9I51EK4oPDHlCbz2",
        },
        {
          title: "תינוקי חמודי",
          desc: "222",
          IsActive: false,
          pic:
            "https://www.dailymoss.com/wp-content/uploads/2019/08/funny-profile-pic33.jpg",
        },
      ],
      members: [
        {
          id: 2113,
          user: {
            id: 322,
            name: "ברוך",
            img: "Baruch",
            lastName: "Ginzburg",
            address: "",
            phoneNumber: 100,
            // imagin there is match more fields in user object
          },
          // I think it will be correct to create tasks and sub tasks
          //so the parrent task will be connected to JIRA
          preTasks: [
            {
              id: 889,
              taskText: "תורנות רסר",
            },
            {
              id: 8089,
              taskText: "לירות בדולב",
            },
          ],
          // empty for now because i want to insert the new task in th GUI later
          newTasks: [],
        },
        {
          id: 2115433,
          user: {
            id: 32342,
            name: "שקד",
            img: "Shaked",
            lastName: "Sibony",
            address: "",
            phoneNumber: 1020,
            // imagin there is match more fields in user object
          },
          // I think it will be correct to create tasks and sub tasks
          //so the parrent task will be connected to JIRA
          preTasks: [
            {
              id: 884569,
              taskText: "תורנות רסר",
            },
            {
              id: 8082739,
              taskText: "לירות בדולב",
            },
          ],
          // empty for now because i want to insert the new task in th GUI later
          newTasks: [],
        },
        {
          id: 2118,
          user: {
            id: 32,
            name: "דולב",
            img: "Dolev",
            lastName: "Bastiker",
            address: "",
            phoneNumber: 100,
            // imagin there is match more fields in user object
          },
          preTasks: [
            {
              id: 8432,
              taskText: "להרביץ לברוך",
            },
            {
              id: 84329,
              taskText: "ליצור חלון",
            },
          ],
          // empty for now because i want to insert the new task in th GUI later
          newTasks: [],
        },
      ],
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