<template>
    <v-container>
        <v-row>
            <v-col cols="12">
                <h1>Autocomplete</h1>
                <v-row class="mt-2" justify="center">
                    <v-autocomplete
                        v-model="values"
                        :items="items"
                        outlined
                        dense
                        chips
                        small-chips
                        deletable-chips
                        label="Name"
                    ></v-autocomplete>
                </v-row>
            </v-col>

            <v-col class="mb-4">
                <v-row justify="center">
                    <v-progress-circular
                        :rotate="360"
                        :size="100"
                        :width="15"
                        :value="45.9"
                        color="teal"
                    >
                        45.9%
                    </v-progress-circular>

                    <v-progress-circular
                        :rotate="-90"
                        :size="100"
                        :width="15"
                        :value="value"
                        color="primary"
                    >
                        {{ value }}
                    </v-progress-circular>

                    <v-progress-circular
                        :rotate="90"
                        :size="100"
                        :width="15"
                        :value="value"
                        color="red"
                    >
                        {{ value }}
                    </v-progress-circular>

                    <v-progress-circular
                        :rotate="180"
                        :size="100"
                        :width="15"
                        :value="value"
                        color="pink"
                    >
                        {{ value }}
                    </v-progress-circular>
                </v-row>
            </v-col>

            <v-col class="mb-5" cols="12">
                <v-row justify="center"> </v-row>
            </v-col>

            <v-col class="mb-5" cols="12">
                <v-row justify="center">
                    <v-card width="500">
                        <div class="d-flex flex-row pt-1">
                            <div>
                                <v-sheet
                                    rounded
                                    class="d-flex justify-center align-center ma-2"
                                    height="50"
                                    width="50"
                                    color="primary"
                                >
                                    <v-icon m-large color="white">mdi-whistle</v-icon>
                                </v-sheet>
                            </div>
                            <div>
                                <v-card-title class="mt-0 pt-0"> Top western road trips </v-card-title>
                                <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>
                            </div>
                        </div>

                        <v-card-actions>
                            <v-btn color="primary" outlined elevation="0"> Explore </v-btn>

                            <v-spacer></v-spacer>

                            <v-btn icon @click="show = !show">
                                <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                            </v-btn>
                        </v-card-actions>

                        <v-expand-transition>
                            <div v-show="show">
                                <v-divider></v-divider>

                                <v-card-text>
                                    I'm a thing. But, like most politicians, he promised more than
                                    he could deliver. You won't have time for sleeping, soldier, not
                                    with all the bed making you'll be doing. Then we'll go with that
                                    data file! Hey, you add a one and two zeros to that or we walk!
                                    You're going to do his laundry? I've got to find a way to
                                    escape.
                                </v-card-text>
                            </div>
                        </v-expand-transition>
                    </v-card>
                </v-row>
            </v-col>

            <v-col class="mb-5" cols="12">
                <v-row justify="center"> </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    name: 'HelloWorld',

    data: () => ({
        items: ['Estelle', 'Francesco', 'Marcello', 'Boris'],
        values: [],
        show: false,
        interval: {},
        value: 0,
    }),
    beforeDestroy() {
        clearInterval(this.interval);
    },
    mounted() {
        this.interval = setInterval(() => {
            if (this.value === 100) {
                return (this.value = 0);
            }
            this.value += 10;
        }, 1000);
    },
};
</script>

<style scoped>
.v-progress-circular {
    margin: 1rem;
}
</style>
