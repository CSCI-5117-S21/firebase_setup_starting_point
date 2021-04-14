<!-- three parts to this example:
1. See how we add "loading" to the template.<template>
2. See how we use a "Default" data value so we can tell if the data is loaded or not.<template>
3. See how we use the "beforeUpdate" hook to get notified when firebase sets the data. if it sets null, then the lookup failed and no word has that id
-->
<template>

<div v-if="word && !word.loading"> 
    <!-- if the word is valid and does not have the loading property (there by default) -->
    {{word.word}}
</div>
<div v-else >
    <!-- otherwise render this content -->
    Loading...
</div>
</template>
<script>

import {db} from "../firebaseConfig.js"

export default {
    name: "wordView",
    
    // I prefer to have the router configured to pass id as a property. see the router configuration for how that works.
    props: ["id"],

    data: function() {
        return {
            word: {loading: true},
        };
    },

    beforeUpdate() {
        if (!this.word) {
            console.log("404")
            // you could, of course, also use the router to actually go to a 404 page if you wanted.
        }
    },

    firestore: function() {
        return {
            word: db.collection("words").doc(this.id)
        }
    },

}
</script>

<style scoped>
.clickable {
    cursor: pointer;
    color:red;
}
</style>