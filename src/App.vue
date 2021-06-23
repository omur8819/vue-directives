<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <h1>Directives</h1>
        <p v-text="'writen by v-text'"></p>
        <p v-html="'<strong>writen by html directive</strong>'"></p>
      </div>
    </div>
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <h1>Custom Directives</h1>
        <p v-color:background.delay="'green'">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Saepe tempora incidunt recusandae ab quam ratione aliquam distinctio consequatur non doloremque consequuntur ex, natus vitae quibusdam maxime laboriosam at fugiat ipsa.</p>
        <p v-color="'red'">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Saepe tempora incidunt recusandae ab quam ratione aliquam distinctio consequatur non doloremque consequuntur ex, natus vitae quibusdam maxime laboriosam at fugiat ipsa.</p>
        <p v-color:background="'#03a9f4'">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Saepe tempora incidunt recusandae ab quam ratione aliquam distinctio consequatur non doloremque consequuntur ex, natus vitae quibusdam maxime laboriosam at fugiat ipsa.</p>
        <p v-html="'<strong>writen by html directive</strong>'"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  directives: {
    "color": {
      bind(el, binding, vnode){
        
        if(binding.modifiers["delay"]){
          setTimeout(() => {
            if(binding.arg == "background"){
              el.style.backgroundColor = binding.value;
            } else {
              el.style.color = binding.value;
            }
          }, 2000)
        } else {
          if(binding.arg == "background"){
            el.style.backgroundColor = binding.value;
          } else {
            el.style.color = binding.value;
          }
        }


      }
    }
  }
}
</script>

<style>

</style>
