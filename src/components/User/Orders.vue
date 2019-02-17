<template>
    <v-container>
        <v-layout row>
            <v-flex xs12 sm8 offset-sm2>
                <v-card>
                    <v-list>
                        <h1 class="text--secondary ml-3" >Orders</h1>
                    </v-list>
                    
                    <v-divider></v-divider>

                    <v-list subheader two-line>

                        <v-list-tile 
                            avatar
                            v-for="order in orders"
                            :key="order.id">

                            <v-list-tile-action>
                                <v-checkbox
                                color="success"
                                v-model="notifications"
                                :input-value="order.done"
                                @change="markDone(order)"></v-checkbox>
                            </v-list-tile-action>

                            <v-list-tile-content @click="notifications = !notifications">
                                <v-list-tile-title>{{order.name}}</v-list-tile-title>
                                <v-list-tile-sub-title>{{order.phone}}</v-list-tile-sub-title>
                            </v-list-tile-content>

                            <v-list-tile-action>
                                <v-btn 
                                    :to="/ad/ + order.id"
                                    class="primary">Open</v-btn>
                            </v-list-tile-action>

                        </v-list-tile>
                    </v-list>


                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
</template>

<script>
export default {
    data () {
        return {
            orders: [
                {
                    id: 'wqd',
                    name: 'Igor Sobol',
                    phone: '+38 068 888 1748',
                    adId: '2',
                    done: false
                }
            ]
        }
    },
    methods: {
        markDone (order) {
            order.done = true
        }
    }
}
</script>