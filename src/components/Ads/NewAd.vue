<template>
    <v-container>
        <v-layout row>
            <v-flex xs12 sm6 offset-sm3>
                <h1 class="text-secondary mb-3">Create new add</h1>
                <v-form ref="form" v-model="valid" validation>

                  <v-text-field
                    class="mb-4"
                    name="title"
                    label="Ad title"
                    type="text"
                    v-model="title"
                    required
                    :rules="[v => !!v || 'Title is required!']"
                  ></v-text-field>

                  <v-textarea
                    name="description"
                    label="Ad description"
                    :type="text"
                    v-model="description"
                    multi-line
                    :rules="[v => !!v || 'Title is required!']"
                  ></v-textarea>

                </v-form>
                <v-layout row class="mb-3">
                    <v-flex xs12>
                        <v-btn class="warning">
                            Upload
                            <v-icon right dark>cloud_upload</v-icon>
                        </v-btn>
                    </v-flex>
                </v-layout>
                
                <v-layout row>
                    <v-flex xs12>
                        <img src="https://cdn.vuetifyjs.com/images/carousel/planet.jpg" height="100" alt="">
                    </v-flex>
                </v-layout>

                <v-layout row>
                    <v-flex xs12>
                        <v-switch
                            label="Add to promo?"
                            v-model="promo"
                            color="primary"
                        ></v-switch>
                    </v-flex>
                </v-layout>

                <v-layout row>
                    <v-flex xs12>
                        <v-spacer></v-spacer>
                        <v-btn
                            :disabled="!valid" 
                            class="success"
                            @cleck="createAd">Create add</v-btn>
                    </v-flex>
                </v-layout>

            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data () {
        return {
            text: '',
            title: '',
            description: '',
            promo: false,
            valid: false
        }
    },
    methods: {
        createAd () {

        }
    }
}
</script>