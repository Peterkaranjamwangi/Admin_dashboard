<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Application </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app class="space-between">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
      <div pa-5>
        <v-btn icon>
          <v-icon>mdi-apps</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>md-refresh</v-icon>
        </v-btn>
      </div>

      <v-btn icon>
        <v-icon>mdi-notification</v-icon>
      </v-btn>
      <v-btn icon> <v-icon>mdi-apps</v-icon> </v-btn>
      <div>
        <v-menu bottom min-width="200px" rounded offset-y>
          <template v-slot:activator="{ on }">
            <v-div icon x-large v-on="on">
              <v-avatar color="brown">
                <v-img>{{ user.image }}</v-img>
                <span></span>
              </v-avatar>
              <span>{{ user.fullName }}</span>
            </v-div>
          </template>
          <v-card>
            <v-list-item-content class="justify-center">
              <div class="mx-auto text-center">
                <v-avatar color="brown">
                  <span class="white--text text-h5">{{ user.image }</span>
                </v-avatar>
                <h3>{{ user.fullName }}</h3>
                <p class="text-caption mt-1">
                  {{ user.email }}
                </p>
                <div class="align-left">
                  <v-divider class="my-3"></v-divider>
                  <v-btn depressed rounded text>
                    <span><v-icon>mdi-account</v-icon></span> My Profile
                  </v-btn>
                  <v-divider class="my-3"></v-divider>
                  <v-btn depressed rounded text>
                    <span><v-icon>mdi-cog</v-icon></span> Accout Settings
                  </v-btn>
                  <v-divider class="my-3"></v-divider>
                  <v-btn depressed rounded text>
                    <span><v-icon>mdi-help-circle</v-icon></span> Need Help?
                  </v-btn>
                  <v-divider class="my-3"></v-divider>
                  <v-btn depressed rounded text>
                    <span><v-icon>mdi-logout</v-icon></span> Sign Out
                  </v-btn>
                </div>
              </div>
            </v-list-item-content>
          </v-card>
        </v-menu>
      </div>
    </v-app-bar>

    <v-main>
      <!--  -->
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: null,

      user: {
        image:
          "https://media.istockphoto.com/photos/smiling-indian-business-man-working-on-laptop-at-home-office-young-picture-id1307615661?b=1&k=20&m=1307615661&s=170667a&w=0&h=Zp9_27RVS_UdlIm2k8sa8PuutX9K3HTs8xdK0UfKmYk=",
        initials: "J.D",
        fullName: "John Doe",
        email: "john.doe@doe.com",
      },

      items: [
        { title: "Dashboard", icon: "mdi-view-dashboard" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" },
        { title: "Dashboard", icon: "mdi-view-dashboard" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" },
      ],
      right: null,
    };
  },
};
</script>
