<template>
  <div class="component validate-component-second">
    <div>
      <div>Компонент <span class="green">{{ _uid }}</span></div>
      <div class="light-green">Если я вызван, то ИЗ <span class="pink">{{ parent }}</span></div>
      <button @click="getValidate()" class="button validate-component-second__button">
        validate
      </button>
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ValidateComponentSecond',
  data () {
    return {
      parent: ''
    }
  },
  methods: {
    validate (uid) {
      this.parent = `${uid}`
    },
    getValidate (uid = this._uid, component = this) {
      this.validate(uid)
      component.$children.forEach((childrenComponent) => {
        return childrenComponent.$options.name === 'ValidateComponentSecond'
          ? childrenComponent.validate(uid) : this.getValidate(uid, childrenComponent)
      })
    }
  }
}
</script>

<style lang="scss">
.validate-component-second{
  &__button{
    margin: 10px 0;
  }
}
</style>
