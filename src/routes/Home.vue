<template>
  <div class="home__wrapper">
    <h1 class="title">원하는 영화를 쉽고 빠르게</h1>
    <div class="search-area">
      <input
        ref="search"
        class="search"
        placeholder="검색하세요 😉"
        @keyup.enter.prevent="submit"
      />
    </div>
    <p v-if="!isMoreThan3" class="recommend">3글자 이상 작성해주세요</p>
    <p v-if="!isEnglish" class="recommend">영어로 입력해주세요</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMoreThan3: true,
      isEnglish: true,
    }
  },
  mounted() {
    this.$refs.search.focus()
  },
  methods: {
    checkSearchValueLength(searchValueLength) {
      return searchValueLength < 3 ? false : true
    },
    checkEnglish(searchValue) {
      const korean = /[ㄱ-ㅎㅏ-ㅣ가-힣]/gi
      return korean.test(searchValue) ? false : true
    },
    changeData(searchValue) {
      this.isMoreThan3 = this.checkSearchValueLength(searchValue.length)
      this.isEnglish = this.checkEnglish(searchValue)
    },
    async submit() {
      const searchValue = this.$refs.search.value
      this.changeData(searchValue)
      if (!this.isMoreThan3 || !this.isEnglish) return
      await this.$store.dispatch("searchResult/updateSearchResults", {
        keyword: this.$refs.search.value,
      })
      this.$router.push({
        name: "SearchResults",
        params: { keyword: this.$refs.search.value },
      })
      this.$refs.search.value = ""
    },
  },
}
</script>

<style lang="scss" scoped>
.home__wrapper {
  height: calc(100vh - $HEADER_HEIGHT * 2);
  @include flexbox;
  flex-direction: column;
  flex-grow: 1;
}

.title {
  font-size: 50px;
  text-align: center;
  word-break: keep-all;
  font-weight: 700;
  margin-bottom: $BASE_PADDING * 4;
}

.search-area {
  display: flex;
  justify-content: center;
  width: 100%;
  .search {
    width: 80%;
    min-width: 250px;
    padding: $BASE_PADDING;
    font-size: 24px;
    border-radius: $BORDER_RADIOUS;
    border: 2px solid $COLOR_GRAY;

    &:hover,
    &:focus {
      border-color: $COLOR_RED;
      outline: none;
    }

    &::placeholder {
      color: $COLOR_SECONDARY;
    }
  }
}

.recommend {
  padding: $BASE_PADDING 0;
  color: $COLOR_RED;
}
</style>
