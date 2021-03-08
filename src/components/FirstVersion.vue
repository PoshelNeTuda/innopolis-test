<template>
  <div class="first-version">
    <div class="header-version">1. Если <span class="pink">ХОТИМ</span> вызывать validate у вложенных компонентов</div>
      <!--  1 --><validate-component-first>
          <some-component>
              <div>
                  <!--  2 --><validate-component-first></validate-component-first>
              </div>
          </some-component>
          <some-component>
              <!--  3 --><validate-component-first>
                  <!--  4 --><validate-component-first/>
              </validate-component-first>
          </some-component>
           <!--  5 --><validate-component-first/>
      </validate-component-first>
  </div>
</template>

<script>
import ValidateComponentFirst from './ValidateComponentFirst.vue'
import SomeComponent from './SomeComponent.vue'

export default {
  name: 'FirstVersion',
  components: {
    ValidateComponentFirst,
    SomeComponent
  }
}
</script>

<style>
.first-version{
  width: 500px;
}
</style>
