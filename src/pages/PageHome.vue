<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end
    q-col-gutter-md">
      <div class="col">
        <q-input
          bottom-slots
          v-model="newTweetContent"
          class="new-tweet"
          autogrow
          placeholder="What's happening?"
          counter
          maxlength="280"
        >
            <template v-slot:before>
              <q-avatar size="xl">
                <img src="https://kb.rspca.org.au/wp-content/uploads/2018/11/golder-retriever-puppy.jpeg">
              </q-avatar>
            </template>
          </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn
              :disable="!newTweetContent"
                unelevated
                rounded
                no-caps
                class="q-mb-lg"
                color="primary"
                label="Tweet"
          />
      </div>
    </div>

    <q-separator
      class="divider"
      size="10px"
      color="grey-2" />
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PageHome',
  data () {
    return {
      newTweetContent: ''
    }
  }
})
</script>

<style lang="sass">
.new-tweet
  textarea
    font-size: 19px
    line-height: 1.4 !important

.divider
  border-top: 1px solid
  border-bottom: 1px solid
  border-color: $grey-4

</style>
