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

    <q-list separator>
      <q-item
      v-for="tweet in tweets"
      :key="tweet.date"
        class="q-py-md"
      >
        <q-item-section avatar top>
          <q-avatar size="xl">
            <img src="https://kb.rspca.org.au/wp-content/uploads/2018/11/golder-retriever-puppy.jpeg">
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong>Unmesh Padhye</strong>
            <span class="text-grey-7">
              @UnmeshPadhye
            </span>
          </q-item-label>
          <q-item-label class="tweet-content text-body1">
            {{ tweet.content }}
          </q-item-label>
          <div class="tweet-icons row justify-between q-mt-sm">
           <q-btn
              flat
              round
              size="sm"
              color="grey"
              icon="far fa-comment" />
           <q-btn
              flat
              round
              size="sm"
              color="grey"
              icon="fas fa-retweet" />
           <q-btn
              flat
              round
              size="sm"
              color="grey"
              icon="far fa-heart" />
           <q-btn
              flat
              round
              size="sm"
              color="grey"
              icon="fas fa-trash" />
          </div>
        </q-item-section>

        <q-item-section side top>
          {{ tweet.date}}
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PageHome',
  data () {
    return {
      newTweetContent: '',
      tweets: [
        {
          content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Unde dignissimos animi ducimus nihil fugiat, molestiae facere voluptate ex? Perspiciatis aperiam magnam repellendus, id numquam mollitia corporis quos dolores tempora quasi?',
          date: 1632249308033
        },
        {
          content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Unde dignissimos animi ducimus nihil fugiat, molestiae facere voluptate ex? Perspiciatis aperiam magnam repellendus, id numquam mollitia corporis quos dolores tempora quasi?',
          date: 1632249729785
        }
      ]
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

.tweet-content
  white-space: pre-line

.tweet-icons
  margin-left: -5px
</style>
