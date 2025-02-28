<!--
  Usage:
  <CopyInput class="address" value="106 臺北市大安區新生南路一段 3 號（國立臺北科技大學-宏裕科技研究大樓）B4 程式設計研究社"/>
-->

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'CopyInput',
  props: {
    value: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const inputRef = ref<HTMLInputElement | null>(null)
    const message = ref('')
    const noError = ref(true)
    const showMessage = (msg: string, ne = true) => {
      message.value = msg
      noError.value = ne
      setTimeout(() => {
        message.value = ''
        noError.value = true
      }, 2000)
    }
    const copyToClipboard = () => {
      // 新 API
      if (navigator.clipboard) {
        navigator.clipboard.writeText(props.value).then(
          () => {
            showMessage('複製成功')
          },
          () => {
            showMessage('複製失敗', false)
          },
        )
      } else if (inputRef.value) {
        // for 老瀏覽器
        inputRef.value.select()
        const successful = document.execCommand('copy')
        if (successful) {
          showMessage('複製成功')
        } else {
          showMessage('複製失敗', false)
        }
      } else {
        showMessage('複製失敗', false)
      }
    }
    return {
      inputRef,
      copyToClipboard,
      message,
      noError,
    }
  },
})
</script>

<template>
  <div>
    <div class="copy-input">
      <input
        ref="inputRef"
        readonly
        :value="value"
      >
      <button @click="copyToClipboard">
        <svg
          fill="#1f1f1f"
          height="24px"
          viewBox="0 -960 960 960"
          width="24px"
          xmlns="http://www.w3.org/2000/svg"
        ><path d="M360-240q-33 0-56.5-23.5T280-320v-480q0-33 23.5-56.5T360-880h360q33 0 56.5 23.5T800-800v480q0 33-23.5 56.5T720-240H360Zm0-80h360v-480H360v480ZM200-80q-33 0-56.5-23.5T120-160v-560h80v560h440v80H200Zm160-240v-480 480Z" /></svg>
      </button>
    </div>
    <p
      v-if="message"
      class="copied-message"
      :class="[{ error: !noError }]"
    >
      {{ message }}
    </p>
  </div>
</template>

<style scoped>
.copy-input {
  display: flex;
  align-items: center;
  border: 0.1rem solid;
  border-radius: 10px;
  input {
    flex: 10;
    padding: 0.5rem;
    font-size: 1rem;
    background-color: #fff;
    border: 0;
    border-radius: 8px 0 0 8px;
  }
  button {
    margin-left: 0;
    width: auto;
    border: 0;
    border-radius: 0 8px 8px 0;
    background-color: white;
    img,
    svg {
      width: 1rem;
      height: auto;
      background-color: transparent;
    }
  }
}
.copied-message {
  font-size: 0.9rem;
  margin: 0.5rem 0 0 0;
  transition: opacity 0.3s ease;
  &.error {
    color: red;
  }
}
</style>
