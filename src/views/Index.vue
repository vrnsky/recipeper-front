<template>
   <div class="wrapper">
    <div class="section page-header header-filter" :style="headerStyle">
       <div class="brand">
              <h1>Recipeper</h1>
              <h3>Cook. Eat. Repeat</h3>
        </div>
    </div>
    <div
           class="md-layout-item md-size-66 md-xsmall-size-100 ml-auto mr-auto text-center">
              <h2>Disclaimer of this project</h2>
      <h4>
        Sometimes it happens that you are too lazy to go to the store and you decide, something to cook from what is at hand.
        But not always it is possible from the first time to google some recipe. This project is designed to solve this problem.
      </h4>
    </div>
    <div class="features text-center">
            <div class="md-layout">
              <div class="md-layout-item md-medium-size-33 md-small-size-100">
                <div class="info">
                  <div class="icon icon-info">
                    <md-icon>note_add</md-icon>
                  </div>
                  <h4 class="info-title">Add your own recipe</h4>
                  <p>
                   Do you have an incredibly tasty recipe? Great!
                   Add your recipes to the app, share your recipes with others.
                   Tasty does not happen much
                  </p>
              </div>
            </div>
             <div class="md-layout-item md-medium-size-33 md-small-size-100">
                <div class="info">
                  <div class="icon icon-success">
                    <md-icon>view_headline</md-icon>
                  </div>
                  <h4 class="info-title">Read and cook</h4>
                  <p>
                  We collect recipes for delicious meals and drinks.
                  So why not try them to cook them today.
                  Without leaving home!
                  </p>
                </div>
              </div>
              <div class="md-layout-item md-medium-size-33 md-small-size-100">
                <div class="info">
                  <div class="icon icon-danger">
                    <md-icon>favorite</md-icon>
                  </div>
                  <h4 class="info-title">With love to User and Food</h4>
                  <p>
                    The Recipeper team loves to eat and does not like to leave the house.
                    More food only love our users.
                  </p>
                </div>
              </div>
          </div>
    </div>
  </div>
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import Navigation from "./components/NavigationSection";
import SmallNavigation from "./components/SmallNavigationSection";
import Tabs from "./components/TabsSection";
import NavPills from "./components/NavPillsSection";
import Notifications from "./components/NotificationsSection";
import TypographyImages from "./components/TypographyImagesSection";
import JavascriptComponents from "./components/JavascriptComponentsSection";
import { LoginCard } from "@/components";

export default {
  components: {
    BasicElements,
    Navigation,
    SmallNavigation,
    Tabs,
    NavPills,
    Notifications,
    TypographyImages,
    JavascriptComponents,
    LoginCard
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
</style>
