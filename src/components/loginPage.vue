<template>
  <div class="login-wrapper">
    <div class="login-card">

      <!-- Left Panel  -->
      <div class="left-panel">
        <div class="logo">
          <img src="../assets/logo.svg" alt="Team Achieve Logo" class="logo-img" />
        </div>

        <div class="hero-image-wrapper">
          <img
            src="../assets/group.svg"
            alt="Team Achieve group"
            class="hero-image"
          />
        </div>

        <div class="brand-tagline">
          <p class="brand-name">Team Achieve</p>
          <p class="brand-sub">Your perfect solution for funding your desires</p>
        </div>
      </div>

      <!-- Right Panel -->
      <div class="right-panel">
        <div class="form-container">

         
          <div class="mobile-logo">
            <img src="../assets/logo.svg" alt="Team Achieve Logo" class="mobile-logo-img" />
            <p class="mobile-logo-text">Team Achieve</p>
          </div>

          <h1 class="form-title">Welcome Back</h1>
          <p class="form-subtitle">
            Enter your email address and password to access your account.
          </p>

          <form @submit.prevent="handleSubmit">

            <div class="field-group">
              <label for="email">Email Address <span class="required">*</span></label>
              <input
                id="email"
                v-model="email"
                type="email"
                placeholder="Enter your email"
                required
              />
            </div>

            <div class="field-group">
              <label for="password">Password <span class="required">*</span></label>
              <div class="password-wrapper">
                <input
                  id="password"
                  v-model="password"
                  :type="showPassword ? 'text' : 'password'"
                  placeholder="Enter your password"
                  required
                />
                <button type="button" class="toggle-password" @click="showPassword = !showPassword">
                  <svg v-if="!showPassword" xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8-11-8-11-8z"/><circle cx="12" cy="12" r="3"/>
                  </svg>
                  <svg v-else xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M17.94 17.94A10.07 10.07 0 0 1 12 20c-7 0-11-8-11-8a18.45 18.45 0 0 1 5.06-5.94M9.9 4.24A9.12 9.12 0 0 1 12 4c7 0 11 8 11 8a18.5 18.5 0 0 1-2.16 3.19m-6.72-1.07a3 3 0 1 1-4.24-4.24"/>
                    <line x1="1" y1="1" x2="23" y2="23"/>
                  </svg>
                </button>
              </div>
            </div>

            <div class="form-options">
              <label class="remember-me">
                <input type="checkbox" v-model="rememberMe" />
                <span>Remember me</span>
              </label>
              <a href="#" class="forgot-link">Forgot Password?</a>
            </div>

            <button type="submit" class="btn-signin">Sign in</button>

          </form>

          <p class="signup-prompt">
            Don't have an account? <a href="#" class="signup-link">Sign up</a>
          </p>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const rememberMe = ref(false)
const showPassword = ref(false)

function handleSubmit() {
  console.log('Sign in:', { email: email.value, rememberMe: rememberMe.value })
  
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* ── Wrapper ── */
.login-wrapper {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  font-family: 'Segoe UI', sans-serif;
}

/* ── Card ── */
.login-card {
  display: flex;
  width: 100%;
  max-width: 860px;
  background: #fff;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.12);
}

/* ── Left Panel ── */
.left-panel {
  background-color: #f5eeff;
  width: 42%;
  padding: 2rem 1.5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.logo {
  align-self: flex-start;
}

.logo-img {
  width: 120px;
  height: auto;
}

.hero-image-wrapper {
  width: 100%;
  border-radius: 12px;
  overflow: hidden;
}

.hero-image {
  width: 100%;
  height: auto;
  display: block;
  object-fit: cover;
}

.brand-tagline {
  text-align: center;
}

.brand-name {
  font-weight: 700;
  font-size: 1rem;
  color: #6b21a8;
  margin-bottom: 0.25rem;
}

.brand-sub {
  font-size: 0.85rem;
  color: #4b5563;
  line-height: 1.4;
}

/* ── Right Panel ── */
.right-panel {
  width: 58%;
  padding: 2.5rem 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.form-container {
  width: 100%;
  max-width: 400px;
}


.mobile-logo {
  display: none;
}

.mobile-logo-img {
  width: 60px;
  height: auto;
}

.mobile-logo-text {
  font-size: 0.95rem;
  font-weight: 600;
  color: #1a1a2e;
  margin-top: 0.4rem;
}

.form-title {
  font-size: 1.75rem;
  font-weight: 700;
  color: #6b21a8;
  text-align: center;
  margin-bottom: 0.4rem;
}

.form-subtitle {
  font-size: 0.875rem;
  color: #6b7280;
  text-align: center;
  margin-bottom: 1.75rem;
  line-height: 1.5;
}


.field-group {
  margin-bottom: 1.25rem;
}

.field-group label {
  display: block;
  font-size: 0.875rem;
  font-weight: 500;
  color: #374151;
  margin-bottom: 0.4rem;
}

.required {
  color: #ef4444;
}

.field-group input[type='email'],
.field-group input[type='text'],
.field-group input[type='password'] {
  width: 100%;
  padding: 0.65rem 0.9rem;
  border: 1px solid #d1d5db;
  border-radius: 8px;
  font-size: 0.9rem;
  color: #1a1a2e;
  outline: none;
  transition: border-color 0.2s;
  box-sizing: border-box;
}

.field-group input:focus {
  border-color: #6b21a8;
  box-shadow: 0 0 0 3px rgba(107, 33, 168, 0.1);
}


.password-wrapper {
  position: relative;
}

.password-wrapper input {
  padding-right: 2.75rem;
}

.toggle-password {
  position: absolute;
  right: 0.75rem;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  cursor: pointer;
  color: #9ca3af;
  display: flex;
  align-items: center;
  padding: 0;
}

.toggle-password:hover {
  color: #6b21a8;
}

.form-options {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 1.5rem;
}

.remember-me {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  font-size: 0.875rem;
  color: #374151;
  cursor: pointer;
}

.remember-me input[type='checkbox'] {
  accent-color: #6b21a8;
  width: 15px;
  height: 15px;
}

.forgot-link {
  font-size: 0.875rem;
  color: #6b21a8;
  text-decoration: none;
  font-weight: 500;
}

.forgot-link:hover {
  text-decoration: underline;
}


.btn-signin {
  width: 100%;
  padding: 0.8rem;
  background-color: #6b21a8;
  color: #fff;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
}

.btn-signin:hover {
  background-color: #581c87;
}

/* ── Sign Up ── */
.signup-prompt {
  text-align: center;
  font-size: 0.875rem;
  color: #6b7280;
  margin-top: 1.25rem;
}

.signup-link {
  color: #6b21a8;
  font-weight: 600;
  text-decoration: none;
}

.signup-link:hover {
  text-decoration: underline;
}


@media (max-width: 768px) and (min-width: 641px) {
  .login-card {
    flex-direction: column;
  }

  .left-panel,
  .right-panel {
    width: 100%;
  }

  .hero-image-wrapper {
    max-height: 260px;
  }

  .hero-image {
    height: 100%;
    object-fit: cover;
  }
}


@media (max-width: 640px) {
  .login-wrapper {
  
    padding: 2rem 1rem;
    align-items: center;
  }

  .login-card {
    flex-direction: column;
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 360px;
  }

 
  .left-panel {
    display: none;
  }

  .right-panel {
    width: 100%;
    padding: 2rem 1.5rem;
  }

  .form-container {
    max-width: 100%;
  }

 
  .mobile-logo {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 1.25rem;
  }

  .form-title {
    font-size: 1.4rem;
  }
}
</style>