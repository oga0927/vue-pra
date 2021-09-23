<template>
  <div class="about">
    <form>
      お名前：
      <input type="text" v-model="yourName">
      <p class="{error: hasError.yourName }">{{ contact.yourName.length}} /20</p>
      <p v-show="hasError.yourName" class="error">氏名は20文字以内で入力してください</p>
      <br>
      電話番号:
      <input type="tel" v-model="contact.tel">
      {{ contact.tel }}
      <br>
      メールアドレス：
      <input type="email" v-model="contact.email">
      <br>
      性別：
      <input type="radio" value="male" v-model="contact.gender">男性
      <input type="radio" value="female" v-model="contact.gender">女性
      <input type="radio" value="other" v-model="contact.gender">その他
      <br>
      年齢：
      <select v-model="contact.age">
        <option value="">年齢を選択してください</option>
        <option>10代</option>
        <option>20代</option>
        <option>30代</option>
      </select>
      <br>
      メッセージ：
      <textarea v-model="contact.message"></textarea><br>
        注意事項にチェック：
      <input type="checkbox" v-model="contact.caution"><br><br>
      <input type="submit" value="送信">
    </form>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      contact: {
        yourName: '',
        tel: '',
        email: '',
        gender: '',
        age: '',
        message: '',
        caution: ''
      },
      hasError: {
        yourName: false
      }
    }
  },
  computed: {
    yourName: {
      get() {
        return this.contact.yourName
      },
      // valueは新しい値
      set(value) {
        // console.log(value);
        if(value.length <= 20) {
          this.hasError.yourName = false
        } else {
          this.hasError.yourName = true
        }
        // 新しい値を返す
        return this.contact.yourName = value
      }
    }
  }
}
</script>

<style scoped>
  .error {
    color: red;
  }
</style>
