<template>
  <!-- 灵气粒子背景 -->
  <StarField />

  <!-- 远山水墨 -->
  <div class="mountains"></div>
  <div class="mist"></div>

  <div class="wrap">
    <!-- 品牌区 -->
    <div class="brand">
      <div class="seal">仙逆</div>
      <div class="title">仙逆</div>
      <div class="subtitle">逆天改命 · 问道长生</div>
    </div>

    <!-- 登录卡片 -->
    <LoginCard />
  </div>
</template>

<script setup>
import StarField from './components/StarField.vue'
import LoginCard from './components/LoginCard.vue'
</script>

<style scoped>
/* 远山水墨 */
.mountains {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  height: 42vh;
  z-index: 1;
  background:
    radial-gradient(120% 80% at 20% 100%, rgba(58, 42, 107, 0.55), transparent 60%),
    radial-gradient(90% 70% at 80% 100%, rgba(20, 30, 70, 0.5), transparent 55%);
  -webkit-mask-image: linear-gradient(to top, #000 30%, transparent 100%);
  mask-image: linear-gradient(to top, #000 30%, transparent 100%);
}

.mist {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 30vh;
  height: 18vh;
  z-index: 1;
  background: linear-gradient(to top, var(--mist), transparent);
  filter: blur(8px);
  animation: drift 14s ease-in-out infinite alternate;
}

@keyframes drift {
  from {
    transform: translateX(-4%);
  }
  to {
    transform: translateX(4%);
  }
}

.wrap {
  position: relative;
  z-index: 3;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 26px;
  padding: 24px;
}

.brand {
  text-align: center;
  user-select: none;
}

.seal {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 104px;
  height: 104px;
  margin-bottom: 14px;
  border-radius: 18px;
  background: linear-gradient(160deg, rgba(232, 198, 107, 0.18), rgba(111, 233, 255, 0.08));
  border: 1px solid rgba(232, 198, 107, 0.45);
  box-shadow:
    0 0 32px rgba(232, 198, 107, 0.25),
    inset 0 0 24px rgba(111, 233, 255, 0.12);
  font-family: 'Ma Shan Zheng', serif;
  font-size: 42px;
  line-height: 1;
  color: var(--gold);
  letter-spacing: 2px;
  writing-mode: vertical-rl;
  padding: 10px 0;
  text-shadow: 0 0 18px rgba(232, 198, 107, 0.6);
}

.title {
  font-family: 'Ma Shan Zheng', serif;
  font-size: 64px;
  letter-spacing: 14px;
  color: #fff;
  text-shadow:
    0 0 26px rgba(111, 233, 255, 0.55),
    0 0 60px rgba(232, 198, 107, 0.35);
}

.subtitle {
  margin-top: 8px;
  font-size: 17px;
  letter-spacing: 6px;
  color: rgba(233, 238, 251, 0.72);
}
</style>
