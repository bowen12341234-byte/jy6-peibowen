 <template>
  <fieldset>
    <legend> v-if </legend>
    <p v-if="flag">欢迎你，XXX</p>
    <P v-if="!flag">你好，请登录，免费注册</P>
  </fieldset>
  <fieldset>
    <legend> v-if v-else</legend>
    <p v-if="flag">欢迎你，XXX</p>
    <P v-else>你好，请登录，免费注册</P>
  </fieldset>
  <fieldset>
    <legend> v-if v-else-if v-else </legend>
    <p v-if="score >= 90">A</p>
    <p v-else-if="score >= 80">B</p>
    <p v-else-if="score >= 70">C</p>
    <p v-else-if="score >= 60">D</p>
    <p v-else>E</p>
  </fieldset>
</template>

<script setup>
import { ref } from 'vue';

const flag = ref(false)
const score = ref(80)

</script>

<style scoped>

</style>