<template>
  <div class="screen">
    <div class="card">
      
      <div class="verify-section">
        <button
          @click="handleRedirect"
          :disabled="isVerified"
          class="verify-btn"
          :class="{ success: isVerified }"
        >
          <svg
            v-if="isVerified"
            class="check-icon"
            viewBox="0 0 48 48"
            width="20"
            height="20"
          >
            <path fill="#ffffff"
              d="M34.602,14.602L21,28.199l-5.602-5.598l-2.797,2.797L21,33.801l16.398-16.402L34.602,14.602z"/>
          </svg>
        </button>

        <p
          class="verify-text"
          :class="{ success: isVerified }"
        >
          {{ isVerified ? "Success!" : "Verify you are human" }}
        </p>
      </div>

      <div class="logo-section">
        <div class="logo-wrapper">
          <img
            src="https://upload.wikimedia.org/wikipedia/zh/thumb/a/a2/Cloudflare_logo.svg/1200px-Cloudflare_logo.svg.png"
            alt="Cloudflare"
          />
        </div>

        <div class="links">
          <a href="https://www.cloudflare.com/privacypolicy/">Privacy</a>
          .
          <a href="https://www.cloudflare.com/website-terms/">Term</a>
        </div>
      </div>

    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      isVerified: false,
    };
  },
  methods: {
      handleRedirect() {
    this.isVerified = true;

    setTimeout(() => {
      this.$router.push('/index.vue');
    }, 1000); 
  },
  },
};
</script>



<style>
  body {
    margin: 0;
    height: 100vh;
    display: grid;
    place-content: center;
    background: #f3f4f6;
    font-family: Arial, sans-serif;
  }

  .card {
    display: flex;
    align-items: center;
    gap: 24px;
    background: white;
    border: 2px solid #e5e7eb;
    padding: 16px 24px;
    border-radius: 4px;
  }

  .verify-section {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .verify-btn {
    width: 32px;
    height: 32px;
    background: white;
    border: 2px solid #9ca3af;
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .verify-btn.success {
    background: #22c55e;
    border-color: #22c55e;
  }

  .verify-text {
    font-size: 14px;
    color: #1f2937;
    transition: all 0.3s ease;
  }

  .verify-text.success {
    color: #16a34a;
    font-weight: bold;
    font-size: 20px;
  }

  .logo-section {
    text-align: right;
  }

  .logo-section img {
    height: 30px;
  }

  .links {
    margin-top: -6px;
    font-size: 10px;
  }

  .links a {
    text-decoration: underline;
    color: black;
  }

  .links a:hover {
    color: #16a34a;
  }

  .check-icon {
    display: none;
  }

  .verify-btn.success .check-icon {
    display: block;
  }
</style>