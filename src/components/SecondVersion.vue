<template>
  <div class="first-version">
    <div class="header-version pink">2. Если НЕ ХОТИМ вызывать validate у всех компонентов </div>
      <!--  1 --><validate-component-second>
          <some-component>
              <div>
                  <!--  2 --><validate-component-second></validate-component-second>
              </div>
          </some-component>
          <some-component>
              <!--  3 --><validate-component-second>
                  <!--  4 --><validate-component-second/>
              </validate-component-second>
          </some-component>
           <!--  5 --><validate-component-second/>
      </validate-component-second>
  </div>
</template>

<script>
import ValidateComponentSecond from './ValidateComponentSecond.vue'
import SomeComponent from './SomeComponent.vue'

export default {
  name: 'SecondVersion',
  components: {
    ValidateComponentSecond,
    SomeComponent
  }
}
</script>

<style>
.first-version{
  width: 500px;
}
</style>
