<template>
  <div>

    <div id="mainmenu">
      <b-navbar type="dark" variant="dark">
        <b-navbar-nav>
          <b-nav-item :to="{name:'index'}">Home</b-nav-item>
          <b-nav-item :to="{name:'contact'}">Contact</b-nav-item>
          <b-nav-item :to="{name:'me'}">Me</b-nav-item>
          <b-nav-item :to="{name:'blog'}">Blog</b-nav-item>
        </b-navbar-nav>
      </b-navbar>
    </div>

    <nuxt />

  </div>
</template>
