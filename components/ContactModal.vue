<template>
  <bModal
    :visible="value"
    class="contact-modal"
    hide-footer
    title="Test Title"
    @change="$emit('input', $event)">
    <bForm @submit="onSubmit">
      <div class="form-group row">
        <label
          :for="'name-input'"
          class="col-sm-4 col-form-label">Ваше имя:</label>
        <div class="col-sm-5">
          <bFormInput
            id="name-input"
            v-model="name"
            name="name"
            type="text"/>
        </div>
      </div>
      <div class="form-group row">
        <label
          :for="'phone-input'"
          class="col-sm-4 col-form-label">Ваш номер телефона:</label>
        <div class="col-sm-5">
          <bFormInput
            id="phone-input"
            v-model="phone"
            type="text"
            name="phone"
            placeholder="Например: +79991112233"
            required/>
        </div>
      </div>
      <div class="row">
        <div class="offset-sm-6 col-sm-3 text-right">
          <br>
          <Button
            type="primary"
            submit
            block>OK</Button>
        </div>
      </div>
      <input
        :value="backRedirect"
        type="hidden"
        name="_next">
    </bForm>
  </bModal>
</template>

<script>
import bModal from 'bootstrap-vue/src/components/modal/modal'
import bForm from 'bootstrap-vue/src/components/form/form'
import bFormInput from 'bootstrap-vue/src/components/form-input/form-input'
import Button from './Button'

// const qwe = process['server'] ? Buffer.from('spamto' + 'petrovich_yar@mail.ru').toString('base64') : undefined

export default {
  name: 'ContactModal',
  components: {
    bModal,
    bForm,
    bFormInput,
    Button
  },
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  data: function () {
    return {
      name: '',
      phone: ''
    }
  },
  computed: {
    backRedirect: function () {
      return process['client'] ? location.origin : ''
    }
  },
  methods: {
    onSubmit: function (event) {
      event.preventDefault()
      event.target.method = 'POST'
      // trying to fool a spam-bot
      event.target.action = 'https://formspree.io/' + process.env.secretEmail.substring(6)
      event.target.submit()
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/customs";

/deep/ {
  @import "../assets/bootstrap/utilities/display";
  @import "../assets/bootstrap/utilities/text";
  @import "../assets/bootstrap/grid";
  @import "../assets/bootstrap/type";
  @import "../assets/bootstrap/transitions";
  @import "../assets/bootstrap/modal";
  @import "../assets/bootstrap/close";
  @import "../assets/bootstrap/forms";

  .close {
    position: fixed;
    top: $modal-header-padding;
    right: $modal-header-padding;
  }

  .modal-header > h5 {
    font-size: 1.25rem;
    color: $text-muted;
    text-transform: uppercase;
  }
}
</style>
