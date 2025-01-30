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
          <label for="email">Email or Phone Number</label>
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
              :type="showPassword ? 'text' : 'password'"
              id="password"
              v-model="password"
              class="input-field"
              placeholder="*******"
            />
            <span>
              <i
                @mousedown="showPassword = true"
                @mouseup="showPassword = false"
                @touchstart="showPassword = true"
                @touchend="showPassword = false"
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
  margin-left: 1em;
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
  font-family: inherit;
  font-size: inherit;
  padding-left: 3em;
}
.input-field::placeholder {
  color: #ccc;
  opacity: 1;
  font-family: inherit;
  font-size: 1.3em;
  padding-left: 0em;
}
.input-field :focus ::placeholder {
  color: #ffffff;
}
.password-field {
  position: relative;
}
.password-field.input-field ::placeholder {
  margin-top: 5em;
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

.submit-button {
  width: 111%;
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
  right: 0.7em;
}
@media (max-width: 506px) {
  .landing-page {
    flex-direction: column;
  }
  .left-half {
    flex: none;
    height: 100vh;
    /* width: 120vw; */
    /* order: 1; */
  }
  .right-half {
    flex: none;
    height: 100vh;
    position: absolute;
    top: 0;
    left: 50%;
    width: 90%;
    transform: translateX(-50%);
    order: 1;
  }
  .login-form {
    width: 80%;
    height: 60%;
    padding-right: 0em;
  }
  .login-header h1 {
    font-size: 32px;
  }
  .background-image {
    opacity: 30%;
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  .login-header p {
    font-size: 14px;
    color: black;
  }
  .form-group {
    margin-left: 0.4em;
    margin-top: 1em;
  }
  .input-field {
    width: 80%;
    height: 2em;
    padding: 0.7em;
    padding-left: 1.4em;
  }
  .input-field::placeholder {
    font-size: 1.1em;
    padding-left: 0em;
  }
  .eye-icon {
    position: absolute;
    right: 3em;
    top: 1em;
    cursor: pointer;
  }
  .submit-button {
    width: 80%;
    height: 3em;
  }
  .submit {
    /* position: relative; */
    margin-top: 3em;
    margin-left: -1em;
  }
  .fa-arrow-right {
    top: 2.1em;
  }
  .text-overlay {
    /* position: absolute; */
    bottom: 1em;
    margin-left: 3em;
    /* font-weight: 700; */
    font-size: 12px;
  }
}
</style>
