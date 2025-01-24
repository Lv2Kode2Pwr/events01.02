<template>
  <div class="landing-page">
    <div class="left-half">
      <img :src="pic" alt="Event Management" class="background-image" />
      <div class="text-overlay">
        <h1>Manage Santim Events Professionally!</h1>
      </div>
    </div>
    <div class="right-half">
      <div class="login-header">
        <h1>Login</h1>
        <p>For Authorized Personnel Only</p>
      </div>
      <form class="login-form">
        <div class="form-group">
          <label for="email">Email</label>
          <input
            type="email"
            id="email"
            v-model="email"
            class="input-field"
            placeholder="example@example.com"
          />
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <div class="password-field">
            <input
              type="password"
              id="password"
              v-model="password"
              class="input-field"
              placeholder="*******"
            />
            <span>
              <i
                @mousedown="showPassword = true"
                @mouseup="showPassword = false"
                class="eye-icon fas"
                :class="{
                  'fa-eye-slash': !showPassword,
                  'fa-eye': showPassword,
                }"
              ></i>
            </span>
          </div>
        </div>
        <div class="submit">
          <button type="submit" class="submit-button">Login</button>
          <i class="eye-icon fas fa-arrow-right"></i>
          <!-- <span @click="handleSubmit" class="arrow-icon"> 👁️ </span> -->
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import LoginImage from "@/assets/LoginImage.png";
export default {
  data() {
    return {
      pic: LoginImage,
      email: "",
      password: "",
      showPassword: false,
    };
  },
};
</script>

<style>
body {
  margin: 0;
  /* margin-left: 0; */
  font-family: "Raleway";
}
.landing-page {
  font-family: "Raleway";
  display: flex;
  height: 100vh;
  color: #171625;
}

.left-half {
  flex: 1;
  background-color: #d3af35;
  position: relative;
  padding: 20px;
  font-weight: 700;
}

.background-image {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.text-overlay {
  position: absolute;
  bottom: 20px;
  left: 20px;
  font-weight: 700;
  font-size: 15px;
}
.right-half {
  flex: 1;
  display: flex;
  flex-direction: column;
  padding: 20px;
  justify-content: center;
}

.login-header {
  justify-content: flex-start;
  text-align: left;
  padding-left: 1.3em;
  margin-left: 10%;
  margin-top: -8em;
}
.login-header h1 {
  font-size: 36px;
  font-weight: 700;
  font-size: 36px;
}
.login-header p {
  font-size: 14px;
  /* line-height: 16px; */
  color: #a2a2a2;
}
.login-form {
  background-color: white;
  margin-left: 10%;
  padding: 20px;
  border-radius: 10px;
  margin-top: 4em;
  width: 70%;
}

.form-group {
  justify-content: center;
  margin-bottom: 15px;
  text-align: left;
}

.form-group label {
  display: block;
  margin-bottom: 1em;
  font-size: 18px;
}

.input-field {
  width: 100%;
  height: 4em;
  border-radius: 4em;
  padding: 10px;
  border: 1px solid #ccc;
  text-shadow: 0 0 0 #000;
  font-family: inherit; /* Match font with label */
  font-size: inherit; /* Match font size with label */
  padding-left: 3em; /* Shift input text to the right */
}
.input-field::placeholder {
  color: #ccc; /* Placeolder color */
  opacity: 1; /* Ensures placeholder is visible */
  font-family: inherit; /* Match font with label */
  font-size: 1.3em; /* Match font size with label */
  padding-left: 0em; /* Shift input text to the right */
}
.input-field :focus ::placeholder {
  color: #ffffff; /* Hides placeholder on focus */
}
.password-field {
  position: relative;
}

.eye-icon {
  position: absolute;
  right: -1em;
  margin-left: auto;
  top: 2em;
  cursor: pointer;
}
.submit {
  position: relative;
  margin-top: 7em;
}
.arrow-icon {
  position: absolute;
  right: 10px;
  top: 3em;
  cursor: pointer;
}
.submit-button {
  width: 102%;
  height: 4.2em;
  border-radius: 4em;
  padding: 3px;
  margin-top: 20px;
  background-color: #d3af35;
  color: #ffffff;
  border: none;
  cursor: pointer;
  font-family: inherit;
  font-size: 18px;
}
.fa-arrow-right {
  font-size: 18px;
  color: #ffffff;
  top: 2.7em;
  right: 2em;
}
</style>
