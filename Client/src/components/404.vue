<template>
 <div>
   <v-row>
     <v-col>
        <v-app-bar justify="center" align="center" max-width="60%"
          ><v-spacer />
            <h1>
              Event Support -- ERROR 404 Room Not Found
            </h1>
          <v-spacer />
        </v-app-bar>
     </v-col>
   </v-row>
   <v-row>
     <v-col>
        <v-card max-width="60%">
          <v-card-text>
            <h1>Sorry for the inconvenience, please call 801-863-8612 for assistance</h1>
          </v-card-text>
          <v-card-actions>
            <v-row>
              <v-col>
                <v-btn small text v-on:click="toggle()">or click here for more options</v-btn>
                <v-row>
                  <v-col />
                  <v-col cols='5'>
                    <v-row>
                    <v-text-field type=text max-width='50%' v-if='menu' >
                      <template v-slot:label>
                        <div>Room Number <small>(ex: SC214 or SC206A)</small></div>
                      </template>
                    </v-text-field>
                    <v-btn>Submit</v-btn>
                    </v-row>
                  </v-col>
                  <v-col />
                </v-row>
              </v-col>
            </v-row>
          </v-card-actions>
        </v-card>
     </v-col>
   </v-row>
 </div>
</template>

<script>
export default {
  name: 'Error404',
  props: {
    room: String,
  },
  data: () => ({
    menu: false,
  }),
  methods: {
    toggle: function() {
      this.menu = !this.menu;
    },
  }
}
</script>