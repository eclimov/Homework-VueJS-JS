<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawerRight"
      fixed
      right
      clipped
      app
    >
      <v-list dense>
        <v-list-tile @click.stop="right = !right">
          <v-list-tile-action>
            <v-icon>exit_to_app</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Open Temporary Drawer</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      color="blue-grey"
      dark
      fixed
      app
      clipped-right
    >
      <v-toolbar-side-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Toolbar</v-toolbar-title>
      <v-spacer />
      <v-toolbar-side-icon @click.stop="drawerRight = !drawerRight" />
    </v-toolbar>
    <v-navigation-drawer
      v-model="drawer"
      fixed
      app
    >
      <v-list dense>
        <v-list-tile @click.stop="left = !left">
          <v-list-tile-action>
            <v-icon>exit_to_app</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>Open Temporary Drawer</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer
      v-model="left"
      temporary
      fixed
    />
    <v-content>
      <v-layout center>
        <v-flex
          sm10
          offset-sm1
          mt-5
        >
          <v-card>
            <v-card-actions>
              <v-spacer />
            </v-card-actions>
            <v-container
              v-bind="{ [`grid-list-${size}`]: true }"
              fluid
            >
              <v-layout
                row
                wrap
              >
                <v-flex
                  v-for="img in images"
                  :key="img"
                  sm6
                  md4
                  xs12
                >
                  <v-card
                    flat
                    tile
                    class="d-flex"
                  >
                    <v-img
                      max-width="100%"
                      :src="img"
                    />
                  </v-card>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card>
        </v-flex>
      </v-layout>
    </v-content>
  </v-app>
</template>

<script>
import img1 from 'img/1.png'
import img2 from 'img/2.png'
import img3 from 'img/3.png'
export default {
  data: () => ({
    drawer: false,
    drawerRight: false,
    right: true,
    left: false,
    size: 'sm',
    images: [
      img1,
      img2,
      img3
    ]
  })
}
</script>
