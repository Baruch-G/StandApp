<template>
  <div id="team-board" class="about">
    <section id="team" class="pb-5">
      <div class="container">
        <!-- <h2 class="section-title h1">{{ teamName }}</h2> -->

        <div class="row member-cards">
          <team-member-card
            v-for="member in members"
            :key="member.id"
            :member="member"
          ></team-member-card>
        </div>
        <stand-up-run v-if="isStandUpRun"></stand-up-run>
      </div>
      <button v-if="!isStandUpRun" v-on:click="isStandUpRun = true" class="btn">
        התחל בססנדאפ
      </button>
      <button
        v-if="isStandUpRun"
        v-on:click="isStandUpRun = false"
        class="close"
      >
      </button>
    </section>
  </div>
</template> 

<script>
import teamMemberCard from "@/components/TeamMemberCard.vue";
import standUpRun from "../components/StandUpRun.vue";

export default {
  name: "TeamBoard",
  components: {
    teamMemberCard,
    standUpRun,
  },
  mounted() {},
  methods: {
    outsideClicked() {
      alert("clicked outside");
    },
    defocusApp() {
      alert("hbhj");
    },
  },
  data() {
    return {
      isStandUpRun: false,
      colors: ["primary", "secondary", "yellow darken-2", "red", "orange"],
      model: 0,

      // need to save the team code name in local storage and put it in the store
      // in case of first log in we need to let the user picking a team
      teamName: "צוות גלובוס",
      kl: "df",
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
<style>
@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css");

section {
}

section .section-title {
  text-align: center;
  color: rgb(23, 162, 184);
  margin-bottom: 50px;
  text-transform: uppercase;
}
.member-cards {
  margin-top: 20px;
}
#team .card {
  /* border: none; */
  /* background: #ffffff; */
}
.btn {
  display: inline-block;
  font-weight: bold;
  padding: 0.25em 0.5em;
  text-decoration: none;
  color: #00bcd4;
  background: white;
  border-radius: 0 15px 15px 0;
  transition: 0.4s;
  position: fixed;
  left: 10px;
  top: 70px;
  font-size: 24px;
}

.btn:hover {
  background: #17a2b8;
  box-shadow: 0px 0px 0px 5px #17a2b8;
}
.close {
  position: absolute;
  right: 15px;
  top: 15px;
  width: 32px;
  height: 32px;
  opacity: 0.6;
}
.close:hover {
  opacity: 1;
}
.close:before, .close:after {
  position: absolute;
  left: 15px;
  content: ' ';
  height: 33px;
  width: 2px;
  background-color: white;
}
.close:before {
  transform: rotate(45deg);
}
.close:after {
  transform: rotate(-45deg);
}

</style>