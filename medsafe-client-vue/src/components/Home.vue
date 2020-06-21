<template>
  <div class="page-container">
    <md-app md-waterfall md-mode="fixed-last" class="fullscreen-height">
      <md-app-toolbar class="md-large md-dense md-primary">
        <div class="md-toolbar-row">
          <div class="md-toolbar-section-start">
            <md-button class="md-icon-button" @click="menuVisible = !menuVisible">
              <md-icon>menu</md-icon>
            </md-button>

            <span class="md-title header">{{header}}</span>
          </div>

          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button">
              <md-icon>more_vert</md-icon>
            </md-button>
          </div>
        </div>

        <div class="md-toolbar-row">
          <md-tabs class="md-primary">
            <md-tab id="tab-home" md-label="Home"></md-tab>
            <md-tab id="tab-pages" md-label="News"></md-tab>
            <md-tab id="tab-posts" md-label="Feel Good!"></md-tab>
          </md-tabs>
        </div>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible">
        <md-toolbar class="md-transparent" md-elevation="0">Navigation</md-toolbar>

        <md-list>
       
          <md-list-item>
            <md-icon>account_circle</md-icon>
            <span class="md-list-item-text">Profile</span>
          </md-list-item>

          <md-list-item>
            <md-icon>exit_to_app</md-icon>
            <span class="md-list-item-text">Logout</span>
          </md-list-item>

        
        </md-list>
      </md-app-drawer>

      <md-app-content>
          <h2>Feature List</h2>
        <ul>
          <li v-for="(data,index) in features" :key="index">{{data.feature}}</li>
        </ul>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      header: "MedSafe",
      features: [
        { feature: "Profile : Profile Settings" },
        { feature: "News : Covid Stats" },
        { feature: "Home : Chat Bot" },
        { feature: "Feel Good : Feel Good News!" },
        { feature: "User Authentication" }

      ],
      menuVisible: false
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fullscreen-height{
    height: 100vh;
}
.header {
  font-size: 2em;
}
.card-style {
  margin: auto;
  width: 80%;
}
</style>
