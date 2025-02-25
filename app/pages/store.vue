<script>
export default {
  name: 'StoreFront',
  data() {
    return {
      selectedSize: 'M', // default size
    }
  },
  methods: {
    sendEmail() {
      // Configure your email details.
      const recipient = 'sales@example.com'
      const subject = `T-Shirt Order Request (${this.selectedSize})`
      // Use CRLF (%0D%0A) for new lines in the encoded body.
      const bodyLines = [
        'Hello,',
        '',
        `I would like to order the awesome t-shirt in size ${this.selectedSize}.`,
        '',
        'Thank you!',
      ]
      const body = bodyLines.join('%0D%0A')

      const mailtoURL = `mailto:${recipient}?subject=${encodeURIComponent(subject)}&body=${body}`

      window.location.href = mailtoURL
    },
  },
}
</script>

<template>
  <div class="container">
    <h1>精美社服</h1>
    <img
      alt="T-Shirt Image"
      class="product-image"
      src="assets/join-img/t-shirt.png"
    >
    <p class="description">
      This is a high-quality, comfortable t-shirt perfect for any occasion. Order now!
    </p>
    <p class="price">
      NT$500.99
    </p>
    <div class="options">
      <label for="size">Choose your size:</label>
      <select
        id="size"
        v-model="selectedSize"
      >
        <option value="XS">
          XS
        </option>
        <option value="S">
          S
        </option>
        <option value="M">
          M
        </option>
        <option value="L">
          L
        </option>
        <option value="XL">
          XL
        </option>
      </select>
    </div>
    <button
      class="pay-button"
      @click="sendEmail"
    >
      預約面交
    </button>
  </div>
</template>

<style scoped>
.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}
.product-image {
  width: 100%;
  max-width: 400px;
  margin: 1rem auto;
}
.description {
  font-size: 1.2rem;
  margin: 1rem 0;
}
.price {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}
.options {
  margin-bottom: 2rem;
}
.options label {
  font-size: 1rem;
  margin-right: 0.5rem;
}
.options select {
  padding: 0.5rem;
  font-size: 1rem;
}
.pay-button {
  background-color: #007bff;
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
}
.pay-button:hover {
  background-color: #0056b3;
}
</style>
