<template>
  <div class="component validate-component-first">
    <div>
      <div>Компонент <span class="green">{{ _uid }}</span></div>
      <div class="light-green">Если я вызван, то ИЗ <span class="pink">{{ parent }}</span></div>
      <button @click="validate(_uid)" class="button validate-component-first__button">validate</button>
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ValidateComponentFirst',
  data () {
    return {
      parent: ''
    }
  },
  methods: {
    validate (uid, component = this) {
      this.parent = `${uid}`
      component.$children.forEach((childrenComponent) => {
        return childrenComponent.$options.name === 'ValidateComponentFirst'
          ? childrenComponent.validate(this._uid) : this.validate(uid, childrenComponent)
      })
    }
  }
}
</script>

<style lang="scss">
.validate-component-first{
  &__button{
    margin: 10px 0;
  }
}
</style>
