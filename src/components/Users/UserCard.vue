<template>
  <div
    class="bg-white q-pa-lg"
    :class="{ card: !$q.screen.xs, 'mobile-card': $q.screen.xs }"
  >
    <div class="row">
      <div class="col-12">
        <div style="position: relative" class="flex justify-center">
          <q-avatar :size="$q.screen.xs ? '60px' : '120px'">
            <img src="~/assets/card-image.png" alt="user" />
          </q-avatar>
          <img
            src="~/assets/flag.png"
            alt="flag"
            style="position: absolute; bottom: 0; right: 70px"
          />
        </div>
        <div class="col-12">
          <div class="q-my-md">
            <div class="heading">Abhishek Gupta</div>
            <div class="subheading">마케팅 · 2y+</div>
          </div>
        </div>
      </div>
    </div>

    <div class="text-color-gray row q-gutter-y-sm font-size">
      <div class="col-12">
        <div class="flex justify-center">
          <div class="q-py-xs q-px-sm text-box">마케팅 콘텐츠 제작</div>
        </div>
      </div>

      <div class="col-12">
        <div class="flex justify-center">
          <div class="q-py-xs q-px-sm text-box">인스타그램 관리</div>
        </div>
      </div>

      <div class="col-12">
        <div class="row q-gutter-x-xs">
          <div class="col text-box q-pa-xs">트위터 관리</div>
          <div class="col text-box">블로그 글 작성</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.card {
  border-radius: 12px;
  gap: 36px;
  height: 30em;
  width: 42%;
  box-shadow: 0px 15px 24px 0px rgba(0, 0, 0, 0.12);

  & .heading {
    font-size: 24px;
    font-weight: 900;
    line-height: 36px;
    text-align: center;
    color: #24252f;
  }

  & .subheading {
    color: #4a77ff;
    font-size: 16px;
    font-weight: 900;
    line-height: 24px;
    text-align: center;
  }

  & .font-size {
    font-size: 16px;
  }
}

.mobile-card {
  border-radius: 12px;
  height: 20em;
  width: 35%;
  margin-bottom: 20px;
  box-shadow: 0px 15px 24px 0px rgba(0, 0, 0, 0.12);

  & .heading {
    font-size: 18px;
    font-weight: 900;
    line-height: 36px;
    text-align: center;
    color: #24252f;
  }

  & .subheading {
    color: #4a77ff;
    font-size: 14px;
    font-weight: 900;
    line-height: 24px;
    text-align: center;
  }

  & .font-size {
    font-size: 10px;
  }
}

.text-box {
  border: solid;
  width: fit-content;
  border-radius: 6px;
  border-color: #c1c5cf;
}
</style>
