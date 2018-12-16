<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="pnael panel-default">
      <div class="panel-body quote">
        <!-- Use slot to render the quote (passed data) -->
        <slot></slot>
      </div>
    </div>
  </div>
</template>
  
<script>
   export default {
     
   }
</script>
  
<style scoped>
  .panel-body {
    font-family: 'Arizonia', cursive;
    font-size: 24px;
    color: #6e6e6e;
  }

  .quote {
    cursor: pointer;
    border: 1px solid black;
  }
  .quote:hover{
    background-color: #ff8f8f;    
  }
</style>