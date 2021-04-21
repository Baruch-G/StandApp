<template>
  <div id="page" class="card mb-3">
    <img :src="getImgUrl(pic)" alt="Card image cap" />
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
  methods: {
    getImgUrl(picname) {
      var images = require.context("../assets/images/", false, /\.jpeg$/);
      // need to return "no img" pic in case that the file dosent exists :(
      // for example  ==link== >>    data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw0HDQ0ICA0OCAgICA0NCAcIDQ8ICQcNFREWFhURExMYKCggGBolGxMTIT0hJSkrLi4uFx8zOTMsNygtLysBCgoKBQUFDgUFDisZExkrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrK//AABEIAOEA4QMBIgACEQEDEQH/xAAbAAEBAAMBAQEAAAAAAAAAAAAAAQIEBQYDB//EADcQAQACAQAFCAkEAQUAAAAAAAABAgMEBRESUhUhMTJBkaKxBlFTYXFyc7LREyIzNCMUQoGC4f/EABQBAQAAAAAAAAAAAAAAAAAAAAD/xAAUEQEAAAAAAAAAAAAAAAAAAAAA/9oADAMBAAIRAxEAPwD9BEUAABAABQQUARQEFAAAAAAAAAAAAAAAAAQFAAAAAAAAAABFEBQAAAAAAAAAAAAAAARUUAAAAAAAAAABFAAAAAAAAAAAAAAAAARUUAAAAAAAAAABFQFAAAAAAAAAAAAAAABFRQAAAAAAAI5+btnoj1gC7luG3dJuW4bd0ggu5bhnuk3LcM90ggu5bhnuk3LcNu6QQXctwz3Sk1mOmJj3zEwAIoAAAAAAAAAAIqAKIAogCiADs+j9I2ZL7P3bYrFu2IcZ2/R/q5PqR5A3M2sMOG048l929dm9G7adnNt7IYcqaP7TwX/Dj62/sZPjX7Ibmg6prekZM8ztvG2uOs7sVjs2+8G5ypo/tPBf8HKmj+08F/w5es9X/wCk2ZMczbFadn7utSWgD0fKmj+08F/wcqaP7TwX/Dzj7ZdGvipTLeNlMvV9cerb8Qd3lTR/aeC/4bGO9NKpvV/yYr7Y54mIt2TzS8m9Hqb+CnzX+6QeeyV3bWrHRW8xH/Eozzde/wBS3nLAAAAAAAAAAAEAAAAABQAHa9H+rk+ePJxHb9H+rk+ePIGhrb+xk+Nfsh1dA1hjyY61vauPJSsRat5iu3Z2w5Wtv7GT41+yGtXFa9bXrWZpj2b9o6KbQdPXOm0y1jBinf2W3r3rz1j3Q1tA1fbS4m8z+njiJittm3ft+GOr9DnS7bOrir/JePKPe9JSkY4ilI3a1jZWsdEQDiav1ZackzpFd2mG3Vnoy293rh2NIw10ilsV+raOntrPZMPoA8nnxWwWtivzWpOyfVPvd/U38FPmv90vnrnRP1q/rUj/ACYo54jpvX/x9NTfwU+a/wB0g4Gbr3+pbzYM83Xv9S3mwAAAAAAAAAAAAAAAAAABHb9H+rk+ePJxHb9H+rk+ePIGlrKk5dJvSkbbXtSKx/1h3NE0aujY4xRz8c8c9stTLoeaM99JwzjjfiIr+rvTNY2RE+TPc0zjw91gbeLFXDG5jrFK7ZndrzQzaO7pnHh7rG7pnHh7rA3ho7mmceHusbmmceHusDdt0T8Jaepv69Pjb7pSaaZPNv4ef3WfbV+CdGxVxXmJtWbbZrtmOedoPN5uvf6lvOWDPN17/Ut5sAAAAAAAAAAAAAAAAAAARsaJpd9EmbY9kxaP3Utz1s+ADp8t5OCniOWsnBTxOYA6fLWTgp4jlrJwU8TmAOny1k4KeI5aycFPE5gDp8tZOCniY5NcZbxNaxWkz/vrE70fBzgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAH/9k=
      return images("./" + picname + ".jpeg");
    },
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