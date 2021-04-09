<template>
  <div id="member-card" class="col-xs-12 col-sm-6 col-md-4">
    <div class="image-flip" ontouchstart="this.classList.toggle('hover');">
      <div class="mainflip">
        <div class="frontside">
          <div class="card">
            <div class="card-body text-center">
              <p>
                <img
                  class="img-fluid"
                  :src="getImgUrl(member.user.img)"
                  alt="card image"
                />
              </p>
              <h4 class="card-title">{{ member.user.name }}</h4>
              <p
                v-for="task in member.preTasks"
                :key="task.id"
                class="card-text"
              >
                {{ task.taskText }}
              </p>
              
            </div>
          </div>
        </div>
        <div class="backside">
          <div class="card">
            <div class="card-body text-center mt-4">
              <h4 class="card-title">כותרת של משימה ראשית</h4>
              <p class="card-text">כאן נכניס אפרות להוסיף ולמחוק משימות</p>
              <h4 class="card-title">כותרת של משימה ראשית</h4>
              <p class="card-text">כאן נכניס אפרות להוסיף ולמחוק משימות</p>
              <br/>
              <p class="card-text">
                --בלחיצה על חלון זה החלון יתרחב לFULL SCREEN--
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TeamMemberCard",
  data() {
    return {};
  },
  methods: {
    getImgUrl(picname) {
      var images = require.context("../assets/images/", false, /\.jpeg$/);
      // need to return "no img" pic in case that the file dosent exists :(
      // for example  ==link== >>    data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw0HDQ0ICA0OCAgICA0NCAcIDQ8ICQcNFREWFhURExMYKCggGBolGxMTIT0hJSkrLi4uFx8zOTMsNygtLysBCgoKBQUFDgUFDisZExkrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrKysrK//AABEIAOEA4QMBIgACEQEDEQH/xAAbAAEBAAMBAQEAAAAAAAAAAAAAAQIEBQYDB//EADcQAQACAQAFCAkEAQUAAAAAAAABAgMEBRESUhUhMTJBkaKxBlFTYXFyc7LREyIzNCMUQoGC4f/EABQBAQAAAAAAAAAAAAAAAAAAAAD/xAAUEQEAAAAAAAAAAAAAAAAAAAAA/9oADAMBAAIRAxEAPwD9BEUAABAABQQUARQEFAAAAAAAAAAAAAAAAAQFAAAAAAAAAABFEBQAAAAAAAAAAAAAAARUUAAAAAAAAAABFAAAAAAAAAAAAAAAAARUUAAAAAAAAAABFQFAAAAAAAAAAAAAAABFRQAAAAAAAI5+btnoj1gC7luG3dJuW4bd0ggu5bhnuk3LcM90ggu5bhnuk3LcNu6QQXctwz3Sk1mOmJj3zEwAIoAAAAAAAAAAIqAKIAogCiADs+j9I2ZL7P3bYrFu2IcZ2/R/q5PqR5A3M2sMOG048l929dm9G7adnNt7IYcqaP7TwX/Dj62/sZPjX7Ibmg6prekZM8ztvG2uOs7sVjs2+8G5ypo/tPBf8HKmj+08F/w5es9X/wCk2ZMczbFadn7utSWgD0fKmj+08F/wcqaP7TwX/Dzj7ZdGvipTLeNlMvV9cerb8Qd3lTR/aeC/4bGO9NKpvV/yYr7Y54mIt2TzS8m9Hqb+CnzX+6QeeyV3bWrHRW8xH/Eozzde/wBS3nLAAAAAAAAAAAEAAAAABQAHa9H+rk+ePJxHb9H+rk+ePIGhrb+xk+Nfsh1dA1hjyY61vauPJSsRat5iu3Z2w5Wtv7GT41+yGtXFa9bXrWZpj2b9o6KbQdPXOm0y1jBinf2W3r3rz1j3Q1tA1fbS4m8z+njiJittm3ft+GOr9DnS7bOrir/JePKPe9JSkY4ilI3a1jZWsdEQDiav1ZackzpFd2mG3Vnoy293rh2NIw10ilsV+raOntrPZMPoA8nnxWwWtivzWpOyfVPvd/U38FPmv90vnrnRP1q/rUj/ACYo54jpvX/x9NTfwU+a/wB0g4Gbr3+pbzYM83Xv9S3mwAAAAAAAAAAAAAAAAAABHb9H+rk+ePJxHb9H+rk+ePIGlrKk5dJvSkbbXtSKx/1h3NE0aujY4xRz8c8c9stTLoeaM99JwzjjfiIr+rvTNY2RE+TPc0zjw91gbeLFXDG5jrFK7ZndrzQzaO7pnHh7rG7pnHh7rA3ho7mmceHusbmmceHusDdt0T8Jaepv69Pjb7pSaaZPNv4ef3WfbV+CdGxVxXmJtWbbZrtmOedoPN5uvf6lvOWDPN17/Ut5sAAAAAAAAAAAAAAAAAAARsaJpd9EmbY9kxaP3Utz1s+ADp8t5OCniOWsnBTxOYA6fLWTgp4jlrJwU8TmAOny1k4KeI5aycFPE5gDp8tZOCniY5NcZbxNaxWkz/vrE70fBzgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAH/9k=
      return images("./" + picname + ".jpeg");
    },
  },
  props: {
    member: Object,
  },
};
</script>

<style>
@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css");
#team {
  background: #eee !important;
}

/* .btn-primary:hover,
.btn-primary:focus {
  background-color: rgb(23, 162, 184);
  border-color: rgb(23, 162, 184);
  box-shadow: none;
  outline: none;
}

.btn-primary {
  color: #fff;
  background-color: rgb(23, 162, 184);
  border-color: rgb(23, 162, 184);
} */

#team .card {
  border: none;
  background: #ffffff;
}

.image-flip:hover .backside,
.image-flip.hover .backside {
  -webkit-transform: rotateY(0deg);
  -moz-transform: rotateY(0deg);
  -o-transform: rotateY(0deg);
  -ms-transform: rotateY(0deg);
  transform: rotateY(0deg);
  border-radius: 0.25rem;
}

.image-flip:hover .frontside,
.image-flip.hover .frontside {
  -webkit-transform: rotateY(180deg);
  -moz-transform: rotateY(180deg);
  -o-transform: rotateY(180deg);
  transform: rotateY(180deg);
}

.mainflip {
  -webkit-transition: 1s;
  -webkit-transform-style: preserve-3d;
  -ms-transition: 1s;
  -moz-transition: 1s;
  -moz-transform: perspective(1000px);
  -moz-transform-style: preserve-3d;
  -ms-transform-style: preserve-3d;
  transition: 1s;
  transform-style: preserve-3d;
  position: relative;
}

.frontside {
  position: relative;
  -webkit-transform: rotateY(0deg);
  -ms-transform: rotateY(0deg);
  z-index: 2;
  margin-bottom: 30px;
}

.backside {
  position: absolute;
  top: 0;
  left: 0;
  background: white;
  -webkit-transform: rotateY(-180deg);
  -moz-transform: rotateY(-180deg);
  -o-transform: rotateY(-180deg);
  -ms-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
  -webkit-box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
  -moz-box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
  box-shadow: 5px 7px 9px -4px rgb(158, 158, 158);
}

.frontside,
.backside {
  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -ms-backface-visibility: hidden;
  backface-visibility: hidden;
  -webkit-transition: 1s;
  -webkit-transform-style: preserve-3d;
  -moz-transition: 1s;
  -moz-transform-style: preserve-3d;
  -o-transition: 1s;
  -o-transform-style: preserve-3d;
  -ms-transition: 1s;
  -ms-transform-style: preserve-3d;
  transition: 1s;
  transform-style: preserve-3d;
}

.frontside .card,
.backside .card {
  min-height: 312px;
}

.backside .card a {
  font-size: 18px;
  color: rgb(23, 162, 184) !important;
}

.frontside .card .card-title,
.backside .card .card-title {
  color: rgb(23, 162, 184) !important;
}

.frontside .card .card-body img {
  object-fit: cover;
  width: 120px;
  height: 120px;
  border-radius: 50%;
  box-shadow: 0px 15px 8px -5px rgb(158, 158, 158);
}
</style>