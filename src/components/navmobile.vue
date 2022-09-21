<template>
  <div id="navigation-mobile">
    <div class="search">
      <input type="text" placeholder="Search..." />
      <i class="fas fa-search"></i>
    </div>
    <ul>
      <li>Home</li>
      <li>Articles</li>
      <li>Magazines</li>
      <li>Editors</li>
      <li>Readers</li>
    </ul>
    <div class="social-media">
      <i class="fab fa-twitter"></i>
      <i class="fab fa-instagram"></i>
      <i class="fab fa-pinterest"></i>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
#navigation-mobile {
  padding: 20px 0 0 0;
}

#navigation-mobile ul {
  list-style: none;
  width: 200px;
  padding-left: 40px;
}

#navigation-mobile ul li {
  color: #fff;
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 20px;
  cursor: pointer;
}

#navigation-mobile ul li:hover {
  color: #111;
}

#navigation-mobile .search {
  position: relative;
  width: 240px;
  margin-bottom: 20px;
  padding-left: 20px;
}

#navigation-mobile .search input {
  border: none;
  outline: none;
  width: 180px;
  padding: 10px 50px 10px 20px;
  margin: 0;
  border-radius: 20px;
  background-color: #efefef;
  font-family: "Segoe UI", Tahoma;
  font-size: 1rem;
}

#navigation-mobile .search i {
  position: absolute;
  right: 5px;
  top: 10px;
  font-size: 1.6rem;
  color: #aaa;
  cursor: pointer;
}

#navigation-mobile .social-media {
  position: absolute;
  left: 40px;
  bottom: 20px;
}

#navigation-mobile .social-media i {
  margin: 0 20px 0 0;
  color: #fff;
  font-size: 2rem;
}
</style>