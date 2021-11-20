<template>
  <div class="test">
    <img class="test__logo" alt="Vue logo" src="../assets/logo.png" />

    <br />
    <br />

    <h1>Start project for UI Library Starter</h1>

    <br />
    <br />

    {{ test }}

    <br />
    <br />

    {{ layout }}

    <br />
    <br />

    <div>
      <Link path="https://www.npmjs.com/package/ui-library-starter-test"
        >Library package on NPM</Link
      >
    </div>
    <br />
    <div>
      <Link path="https://ui-library-starter-test.netlify.app"
        >Library deploy on Netlify</Link
      >
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import resize from 'ui-library-starter-test/src/mixins/resize.js';

export default {
  name: 'Test',

  mixins: [resize],

  computed: {
    ...mapGetters(['test', 'layout']),
  },

  mounted() {
    setTimeout(() => {
      this.setTest('Изменяем стор библиотеки из проекта!');
      this.setLayout('Изменяем стор библиотеки из проекта!');
    }, 2000);
  },

  methods: {
    ...mapActions(['setTest', 'setLayout']),
  },
};
</script>

<style lang="stylus" scoped>
@import '~/src/stylus/_stylebase.styl';

.test {
  padding: 100px 0;
  text-align: center;

  +$mobile() {
    padding: 60px 0;
  }

  &__logo {
    max-width: 120px;
    margin: 0 auto;

    +$mobile() {
      max-width: 80px;
    }
  }

  &__components {
    margin-top: 50px;
  }

  &__wrapper-inner {
    +$mobile() {
      padding: 0 20px;
    }
  }
}

h1 {
  $text('elena');

  +$tablet() {
    padding: 0 40px;
    $text('olga');
  }

  +$mobile() {
    padding: 0 20px;
    $text('anna');
  }
}
</style>
