<template>
    <div class="footer">
      <a 
       href="#" 
       class="footer-link" 
       title="About Vue Mastery"
      >
        About Vue Mastery
      </a>
      <span class="footer-space"></span>
      <a 
       href="#" 
       class="footer-link" 
       title="Latest Stories for Vue Mastery"
      >
        Latest Stories
      </a>
      <span class="footer-space"></span>
      <a
       href="#" 
       class="footer-link" 
       title="Archive for Vue Mastery"
      >
        Archive
      </a>
      <span class="footer-space"></span>
      <a
       href="#" 
       class="footer-link"
      >
        About Medium
      </a>
      <span class="footer-space"></span>
      <a
       href="#" 
       class="footer-link"
      >
        Terms
      </a>
      <span class="footer-space"></span>
      <a 
       href="#" 
       class="footer-link"
      >
        Privacy
      </a>
    </div>
</template>
<script>
export default {
    name: "TheFooter"
}
</script>
<style lang="scss">
$color-gray: rgba(0, 0, 0, 0.54);
$color-darkblack: #000;
.footer {
  display: flex;
  justify-content: flex-end;
  margin: 35px 0;
}
.footer-link {
  display: block;
  color: $color-gray;
  text-decoration: none;
}
.footer-space::after {
  content: "\00B7";
  margin: 0 3px;
}
.footer-link:hover {
  color: $color-darkblack;
}
    
</style>