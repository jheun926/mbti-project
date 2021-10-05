<template>
  <!-- 인트로 페이지 -->
  <main v-if="page === 0">
    <img src="/onepiece.jpg" alt="원피스 캐릭터들" />
    <h1>원피스 캐릭터 찾기</h1>
    <h2>나와 닮은 원피스 캐릭터는 누구일까요?</h2>
    <Button text="테스트 시작!" :clickEvent="startTest" />
  </main>
  <!-- 질문 페이지 -->
  <main v-else-if="page < 5">
    <Question />
  </main>
</template>
<script>
/* * 메인 페이지 안에 들어갈 것 * 1. 인트로 페이지 * 2. 조건부 렌더링을 통해
퀴즈 컴포넌트 * 3. 페이지 이동 /result/_mbti */

export default {
  computed: {
    page() {
      return this.$store.state.page;
    }
  },
  methods: {
    startTest() {
      this.$store.commit("SET_PAGE", 1);
    }
  }
};
</script>

<style>
main {
  padding: 30px 0;
  width: 100%;
  max-width: 360px;
  margin: auto;
  text-align: center;
}

h1 {
  font-size: 1.8em;
  margin-bottom: 25px;
}

h2 {
  font-size: 1.2em;
  color: #b9b8b7;
  margin-bottom: 25px;
}

img {
  width: inherit;
  margin-bottom: 30px;
}

p {
  margin-bottom: 40px;
  text-align: left;
}
</style>
