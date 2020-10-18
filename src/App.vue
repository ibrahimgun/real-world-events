<template>
  <div id="app">
    <Navbar />
    <div id="nav"></div>
    <router-view />
  </div>
</template>
<script>
import Navbar from '@/components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500&display=swap');
:root {
  --clr-gray-light: #d7dfe2;
  --clr-gray-med: #616b74;
  --clr-gray-dark: #414b56;
  --clr-link: #4d97b2;
  --clr-popular: #d7dfe2;
  --clr-technology: #651fff;
  --clr-psychology: #e85808;
}

* {
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
  margin: 0;
  padding: 0;
  text-decoration: none;
}

body {
  margin: 2rem;
  color: var(--clr-gray-dark);
  background: #f6f7f8;
}

.wrapper {
  display: inline-flex;
  flex-wrap: wrap;
  justify-content: center;
  padding-left: 4rem;
}

.card {
  overflow: hidden;
  box-shadow: 0px 2px 10px var(--clr-gray-light);
  background: white;
  border-radius: 0.5rem;
  position: relative;
  width: 350px;
  margin: 1rem;
  transition: 250ms all ease-in-out;
  cursor: pointer;
}

.card:hover {
  transform: scale(1.01);
  box-shadow: 0px 2px 20px var(--clr-gray-light);
}

.banner-img {
  position: absolute;
  object-fit: cover;
  height: 14rem;
  width: 100%;
}

.status {
  font-size: 0.8rem;
  font-weight: bold;
  color: white;
  background: red;
  padding: 0.5rem 1.3rem 0.5rem 1rem;
  text-transform: uppercase;
  position: absolute;
  z-index: 1;
  top: 1rem;
  border-radius: 0 2rem 2rem 0;
}

.popular {
  background: var(--clr-popular);
  color: black;
}

.technology {
  background: var(--clr-technology);
}

.psychology {
  background: var(--clr-psychology);
}

.card-body {
  margin: 15rem 1rem 1rem 1rem;
}

.time {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--clr-link);
}

.card-title {
  line-height: 1.5rem;
  margin: 1rem 0 0.5rem;
}

.card-description {
  color: var(--clr-gray-med);
  font-size: 0.9rem;
}

.attendees {
  display: flex;
  margin-top: 2rem;
  align-items: center;
  text-decoration: none;
}

.card-profile-info {
  margin-left: 1rem;
}

.profile-name {
  font-size: 1rem;
}

.profile-followers {
  color: var(--clr-gray-med);
  font-size: 0.9rem;
}

.select {
  background: #fff
    url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 4 5'%3E%3Cpath fill='%23343a40' d='M2 0L0 2h4zm0 5L0 3h4z'/%3E%3C/svg%3E")
    no-repeat right 12px center;
}
.location {
  display: flex;
  margin-left: 6rem;
}
a:visited {
  color: currentColor;
}
</style>
