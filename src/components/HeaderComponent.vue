<script setup></script>

<template>
  <div class="header_container">
    <header>
      <a href="/accueil" class="logo">Logo</a>

      <nav>
        <ul>
          <li><a href="/home">Home</a></li>
        </ul>
      </nav>
    </header>

    <h1>PHOTO OF THE DAY</h1>
  </div>
</template>

<style lang="scss" scoped>
.header_container {
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  font-family: var(--font1);
  header {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.3rem 2rem;
    background-color: var(--black);
    z-index: 999;

    .logo {
      color: var(--white);
      font-size: 1.5rem;
      font-weight: 700;
      text-decoration: none;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;

      ul {
        display: flex;
        justify-content: space-between;
        align-items: center;
        list-style: none;

        li {
          margin: 0 1rem;

          a {
            color: var(--white);
            text-decoration: none;
            font-size: 1rem;
            font-weight: 500;
          }
        }
      }
    }
  }
  h1 {
    margin-top: 2rem;
    font-size: 5rem;
    color: var(--blue);
  }
}
</style>
