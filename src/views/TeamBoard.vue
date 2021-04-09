<template>
  <div id="team-board" class="about">
    <section id="team" class="pb-5">
      <div class="container">
        <h2 class="section-title h1">{{ teamName }}</h2>
        <div class="row">
          <team-member-card
            v-for="member in members"
            :key="member.id"
            :member="member"
          ></team-member-card>
        </div>
      </div>
    </section>
  </div>
</template> 

<script>
import teamMemberCard from "@/components/TeamMemberCard.vue";
export default {
  data() {
    return {
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
  name: "TeamBoard",
  components: {
    teamMemberCard,
  },
};
</script>
<style>
@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css");
#team {
  background: #eee !important;
}

section {
  padding: 60px 0;
}

section .section-title {
  text-align: center;
  color: rgb(23, 162, 184);
  margin-bottom: 50px;
  text-transform: uppercase;
}

#team .card {
  border: none;
  background: #ffffff;
}
</style>