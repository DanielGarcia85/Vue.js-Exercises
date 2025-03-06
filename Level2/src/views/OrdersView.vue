<template>
  <div class="content">

     <!-- Barre de recherche -->
    <input v-model="searchQuery" placeholder="Search by sender or destination" />

    <!-- Filtrage par statut -->
    <select v-model="selectedStatus">
      <option value="">All Status</option>
      <option value="Confirmed">Confirmed</option>
      <option value="In delivery">In delivery</option>
      <option value="Delivered">Delivered</option>
    </select>

    <router-link to="add"><button>Add new order</button></router-link>

    <!-- Tableau des commandes -->
    <table>
      <thead>
        <tr>
          <th @click="sortBy('date')">Date {{ sortIcon("date") }}</th>
          <th @click="sortBy('sender')">Sender {{ sortIcon("sender") }}</th>
          <th @click="sortBy('destination')">Destination {{ sortIcon("destination") }}</th>
          <th @click="sortBy('weight')">Weight (kg) {{ sortIcon("weight") }}</th>
          <th @click="sortBy('status')">Status {{ sortIcon("status") }}</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="order in filteredOrders" :key="order.id">
          <td>{{ order.date }}</td>
          <td>{{ order.sender }}</td>
          <td>{{ order.destination }}</td>
          <td>{{ order.weight }}</td>
          <td>{{ order.status }}</td>
          <td>
            <button @click="nextStatus(order)">Next status</button>
            <button @click="deleteOrder(order.id)">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>

  </div>
</template>
<script>
export default {
  data() {
    return {
      searchQuery: "",
      selectedStatus: "",
      sortColumn: "",
      sortOrder: "asc",
      orders: [] // On charge les commandes dans mounted()
    }
  },
  computed: {
    filteredOrders() {
      return this.orders
        .filter(
          (order) =>
            order.sender.toLowerCase().includes(this.searchQuery.toLowerCase()) ||
            order.destination.toLowerCase().includes(this.searchQuery.toLowerCase())
        )
        .filter((order) => (this.selectedStatus ? order.status === this.selectedStatus : true))
        .sort((a, b) => {
          if (!this.sortColumn) return 0
          const modifier = this.sortOrder === "asc" ? 1 : -1
          return modifier * (a[this.sortColumn] > b[this.sortColumn] ? 1 : -1)
        })
      }
  },
  mounted() {
    const storedOrders = localStorage.getItem("orders")
    if (storedOrders && JSON.parse(storedOrders).length > 0) {
      this.orders = JSON.parse(storedOrders); // Charger depuis localStorage
    } else {
      // Première utilisation, on charge des données par défaut
      this.orders = [
        { id: 1, date: "2025/02/10", sender: "Amazon", destination: "Paris", weight: 12.5, status: "Confirmed" },
        { id: 2, date: "2025/02/12", sender: "eBay", destination: "London", weight: 5.2, status: "In delivery" },
        { id: 3, date: "2025/02/15", sender: "AliExpress", destination: "Berlin", weight: 8.1, status: "Delivered" },
        { id: 4, date: "2025/02/18", sender: "Etsy", destination: "Madrid", weight: 3.0, status: "Confirmed" },
        { id: 5, date: "2025/02/20", sender: "Walmart", destination: "Rome", weight: 7.3, status: "In delivery" },
        { id: 6, date: "2025/02/22", sender: "Target", destination: "Vienna", weight: 5.9, status: "Delivered" },
        { id: 7, date: "2025/02/25", sender: "Zalando", destination: "Amsterdam", weight: 6.8, status: "Confirmed" },
        { id: 8, date: "2025/02/27", sender: "Rakuten", destination: "Brussels", weight: 9.4, status: "In delivery" },
        { id: 9, date: "2025/03/01", sender: "Newegg", destination: "Zurich", weight: 4.7, status: "Delivered" },
        { id: 10, date: "2025/03/03", sender: "Shopify", destination: "Oslo", weight: 10.2, status: "Confirmed" }

      ];
      this.saveToLocalStorage(); // Sauvegarde les données initiales
    }
  },
  methods: {
    sortBy(column) {
      if (this.sortColumn === column) {
        this.sortOrder = this.sortOrder === "asc" ? "desc" : "asc";
      } else {
        this.sortColumn = column
        this.sortOrder = "asc"
      }
    },
    sortIcon(column) {
      if (this.sortColumn === column) {
        return this.sortOrder === "asc" ? "🔼" : "🔽"
      }
      return ""
    },
    saveToLocalStorage() {
      localStorage.setItem("orders", JSON.stringify(this.orders))
    },
    deleteOrder(orderId) {
      this.orders = this.orders.filter(order => order.id !== orderId)
      this.saveToLocalStorage(); // Sauvegarde après suppression
    },
    nextStatus(order) {
      const statusIndex = ["Confirmed", "In delivery", "Delivered"].indexOf(order.status)
      order.status = ["Confirmed", "In delivery", "Delivered"][(statusIndex + 1) % 3]
      this.saveToLocalStorage(); // Sauvegarde après modification
    }
  },
  watch: {
    orders: {
      handler: "saveToLocalStorage",
      deep: true // Surveille les changements profonds
    }
  }
}
</script>
