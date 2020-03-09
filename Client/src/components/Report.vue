<template>
    <div>
        <v-row>
            <v-col>
                <v-app-bar justify="center" align="center" max-width='60%'
        >         <v-col>
                        <h1> {{ roomConvert(room) }} Event Support </h1>
                    </v-col>
                </v-app-bar>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-card flat max-width='60%'>
                    <v-card-text>
                        <v-row>
                            <v-col>
                                <v-text-field label="Name" cols="5"> </v-text-field>
                            </v-col>
                            <v-col>
                                <v-text-field cols="5" float required>
                                    <template v-slot:label>
                                        <div>Email <small>(required)</small></div>
                                    </template>
                                </v-text-field>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-textarea>
                                <template v-slot:label>
                                    <div>Breif Description <small>(optional)</small></div>
                                </template>
                            </v-textarea>
                        </v-row>
                    </v-card-text>
                    <v-card-actions>
                        <v-btn>Cancel</v-btn>
                        <v-spacer />
                        <v-btn>Submit</v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    name: 'Report',
    props: {
    room: String,
  },
    methods: {
        roomConvert: function(room) {
            var building = room.substring(0, 2);
            var roomNumber = room.substring(2, 5);
            if (room.length > 5) {
                return building + "-" + roomNumber + room.substring(5, 6).toLowerCase();
            } else {
                return building + "-" + roomNumber;
      }
    },
    }
}
</script>