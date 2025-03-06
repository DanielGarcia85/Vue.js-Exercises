<template>
  <h2>Add new order</h2>

  <input type="date" v-model="newOrder.date" /><br />
  <input type="text" v-model="newOrder.sender" placeholder="Sender" /><br />
  <input type="text" v-model="newOrder.destination" placeholder="Destination" /><br />
  <input type="number" v-model="newOrder.weight" placeholder="Weight in kg" min="0.1" /><br />
  <p v-if="errorMessage" style="color: red">{{ errorMessage }}</p>
  <button @click="add">Save</button>
  <router-link to="/"><button>Cancel</button></router-link>
</template>

<script>
import { nanoid } from "nanoid"

export default {
  data() {
    return {
      newOrder: {
        id: "",
        date: "",
        sender: "",
        destination: "",
        weight: null,
        status: "Confirmed"
      },
      errorMessage: ""
    }
  },
  computed: {},
  methods: {
    add() {
      if (
        !this.newOrder.date ||
        !this.newOrder.sender ||
        !this.newOrder.destination ||
        !this.newOrder.weight ||
        this.newOrder.weight <= 0
      ) {
        this.errorMessage = "All fields must be filled and weight must be greater than 0."
        return
      }

      this.errorMessage = ""

      this.newOrder.id = nanoid();

      const storedOrders = JSON.parse(localStorage.getItem("orders")) || []
      storedOrders.push(this.newOrder)
      localStorage.setItem("orders", JSON.stringify(storedOrders))
      this.$router.push("/")
    },
    newId() {
      return nanoid()
    }
  }
}
</script>
