<template>
  <div class = "event">
    <h1>Upcoming Events</h1>
    <ul class="list">
      <EventsList v-for = "oneEvent in myEvents" :key = "oneEvent.id" v-bind:event = "oneEvent"/>
    </ul>
    <router-link id = "create-button" to="/create">Create New Event</router-link>
  </div>
</template>


<script>
import EventsList from "./EventsList"

export default {
  name: 'Events',
  props: ["myEvents"],
  components: {
    EventsList
  }
}
</script>


<style scoped>

.event {
  display:flex;
  align-items:center;
  flex-direction:column;
}

.list {
  width: 40vw;
  list-style-type: none;
  height: 30vw;
  overflow: scroll;
}

#create-button {
  background-color:rgb(255, 177, 153);
  color: black;
  text-align: center;
  text-decoration: none;
  font-size: 1vw;
  font-weight: 500;
  margin: 0;
  margin-left: 2.5vw;
  padding: .5vw .5vw;
  cursor: pointer;
  border-radius: .25vw;
  border: 1px solid black;
  box-shadow: .25vw .25vw .125vw 0vw rgba(0,0,0,0.75);
}

</style>
