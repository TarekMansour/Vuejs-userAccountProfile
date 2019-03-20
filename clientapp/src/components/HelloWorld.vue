<template>
  <div class="mt-5 pt-5">
    <v-flex xs12 sm8 md6 lg4>
      <v-card class="mx-1 pa-1 mb-4">
        <div class="profile">
          <div class="name">
            <div class="customLabel">{{userFullName}}</div>
            <div class="userEmail">{{userEmail}}</div>
          </div>
          <div>
            <img :src="image_url" class="profileImage">
          </div>
        </div>

        <div class="position">{{position}}</div>

        <!-- <h3>Statstics :</h3> -->
        <div class="location">
          <v-icon class="icon">place</v-icon>
          <div class="info_text">{{location}}</div>
        </div>

        <div class="article">
          <v-icon class="icon">class</v-icon>
          <div class="info_text">{{public_article}} TechShare article(s)</div>
        </div>

        <div class="comment">
          <v-icon class="icon">comment</v-icon>
          <div class="info_text">{{comment}} comment(s)</div>
        </div>

        <div class="seenArticle">
          <v-icon class="icon">visibility</v-icon>
          <div class="info_text">{{seenArticle}} seen article(s)</div>
        </div>
        
        <div class="pointofinterst">Point of interest:</div>
        <div>
          <v-form v-model="valid" ref="form">
            <v-layout row wrap>
              <v-flex xs2 v-for="option in pointOfInterest" :key="option.text">{{option.text}}</v-flex>
            </v-layout>
          </v-form>

          <a v-bind:href="'https://techshare.o2f-it.com/post/'+ articleID">Here's an article you might want to read</a>
        </div>
      </v-card>
    </v-flex>
  </div>
</template>


<script>
export default {
  data: () => ({
    name: "",
    userFullName: "UserFullName",
    userEmail: "user@amaris.com",
    image_url:
      "http://greenwings.co/wp-content/uploads/2018/09/blank-head-profile-pic-for-a-man.jpg",
    position: "user position (e.g Software Developer)",
    public_article: "0",
    location: "Amaris Hub/Country (e.g AmaTUN)",
    comment: "0",
    seenArticle: "0",
    articleID: "5c331b070920090001a42884",
    pointOfInterest: [
      { text: ".Net", value: "dotNet" },
      { text: "ARP", value: "arp" },
      { text: "SQL", value: "sql" },
      { text: "CI/CD", value: "cicd" }
    ]
  })
};
</script>

<style scoped>
.profile {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.name {
  display: flex;
  flex-direction: column;
}

.customLabel {
  width: 15rem;
  font-weight: 400;
  font-style: italic;
  font-size: 1.75rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 0.25rem 0;
}

.userEmail {
  padding: 1rem 0;
  font-weight: 200;
  font-size: 1.1rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 0.25rem 0;
}

.profileImage {
  width: 5rem;
}

.position {
  padding: 1rem 0;
  font-weight: 300;
  font-size: 1.60rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 0.25rem 0;
}

.location,
.article,
.comment,
.seenArticle {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem 0;
}

.pointofinterst {
  color: orangered;
  padding: 1rem 3;
  font-weight: 400;
  font-size: 1.60rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 0.9rem 0;
}

.icon {
  padding: 0 2rem 0 1rem;
  font-size: 2rem;
}

.info_text {
  font-size: 1.25rem;
  font-weight: 400;
}
</style>
