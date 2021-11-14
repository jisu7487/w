<template>
  <div>
    <nav class="breadcrumb">
      <ul>
        <li>
          <nuxt-link to="/"
          ><i class="fas fa-home"></i> Home</nuxt-link>
        </li>
        <li>
      <nuxt-link to="/restaurant"
      ><i class="fas fa-utensils"></i>&nbsp;비빔밥 맛집</nuxt-link>
        </li>
       <li>
      <nuxt-link to="/food"
      ><i class="fas fa-bacon"></i>&nbsp;불고기 맛집</nuxt-link>
        </li>
           <li>
              <nuxt-link to="/Chart"
                ><i class="fas fa-money-bill-alt"></i>&nbsp;가격변화 chart</nuxt-link>
        </li>
         <li>
           <nuxt-link to="/Recipe"
         ><i class="fas fa-receipt"></i>&nbsp;레시피</nuxt-link></li>
      </ul>
    </nav>
    <nuxt/>
    <footer class="footer">
      <div class="content has-text-centered">
        <i class="fas fa-copyright"></i> 2020-2021, 모든 저작권은 <strong>나지수</strong>에게 있습니다. 
      </div>
    </footer>
  </div>
</template>