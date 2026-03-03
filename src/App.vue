<script setup>
const videoLinks = [
  { name: 'B站', url: 'https://www.bilibili.com' },
  { name: '抖音', url: 'https://www.douyin.com' },
  { name: '腾讯视频', url: 'https://v.qq.com' },
  { name: '爱奇艺', url: 'https://www.iqiyi.com' },
  { name: '优酷', url: 'https://www.youku.com' },
  { name: 'YouTube', url: 'https://www.youtube.com' },
  { name: '芒果TV', url: 'https://www.mgtv.com' },
  { name: '搜狐视频', url: 'https://tv.sohu.com' },
]

const novelLinks = [
  { name: '起点中文网', url: 'https://www.qidian.com' },
  { name: '番茄小说', url: 'https://fanqienovel.com' },
  { name: '七猫小说', url: 'https://www.qimao.com' },
  { name: '掌阅小说', url: 'https://www.zhangyue.com' },
  { name: '晋江文学城', url: 'https://www.jjwxc.net' },
  { name: '纵横中文网', url: 'https://www.zongheng.com' },
]

const toolsLinks = [
  { name: '百度', url: 'https://www.baidu.com' },
  { name: 'Google', url: 'https://www.google.com' },
  { name: 'GitHub', url: 'https://github.com' },
  { name: 'Gitee', url: 'https://gitee.com' },
  { name: '蓝奏云', url: 'https://www.lanzou.com' },
  { name: '阿里云盘', url: 'https://www.aliyundrive.com' },
]
</script>

<template>
  <div class="container">
    <!-- 背景 -->
    <div class="bg"></div>
    
    <!-- 内容 -->
    <div class="content">
      <!-- 头像和名称 -->
      <div class="profile">
        <div class="avatar">
          <img src="https://api.dicebear.com/7.x/adventurer/svg?seed=Huahua&backgroundColor=e2b3cf" alt="花花" />
        </div>
        <h1 class="name">花花</h1>
        <p class="desc">欢迎来到我的小窝~ 🐍</p>
      </div>

      <!-- 搜索框 -->
      <div class="search">
        <form action="https://www.baidu.com/s" method="get" target="_blank">
          <input type="text" name="wd" placeholder="百度搜索..." />
        </form>
      </div>

      <!-- 链接卡片 -->
      <div class="links">
        <!-- 视频网站 -->
        <div class="card">
          <h2 class="card-title">📺 视频</h2>
          <div class="link-list">
            <a v-for="link in videoLinks" :key="link.url" :href="link.url" target="_blank" class="link-item">
              {{ link.name }}
            </a>
          </div>
        </div>

        <!-- 小说网站 -->
        <div class="card">
          <h2 class="card-title">📚 小说</h2>
          <div class="link-list">
            <a v-for="link in novelLinks" :key="link.url" :href="link.url" target="_blank" class="link-item">
              {{ link.name }}
            </a>
          </div>
        </div>

        <!-- 工具网站 -->
        <div class="card">
          <h2 class="card-title">🛠️ 工具</h2>
          <div class="link-list">
            <a v-for="link in toolsLinks" :key="link.url" :href="link.url" target="_blank" class="link-item">
              {{ link.name }}
            </a>
          </div>
        </div>
      </div>

      <!-- 底部 -->
      <footer class="footer">
        <p>© 2026 花花的小窝</p>
      </footer>
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  min-height: 100vh;
  position: relative;
  padding: 40px 20px;
}

.bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #e2b3cf 0%, #7d7eb2 100%);
  z-index: -1;
}

.content {
  max-width: 800px;
  margin: 0 auto;
}

/* 头像区域 */
.profile {
  text-align: center;
  margin-bottom: 30px;
}

.avatar {
  width: 120px;
  height: 120px;
  margin: 0 auto 15px;
  border-radius: 50%;
  overflow: hidden;
  border: 4px solid rgba(255, 255, 255, 0.6);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.15);
}

.avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.name {
  font-size: 32px;
  font-weight: bold;
  color: #fff;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  margin-bottom: 8px;
}

.desc {
  color: rgba(255, 255, 255, 0.9);
  font-size: 16px;
}

/* 搜索框 */
.search {
  margin-bottom: 30px;
}

.search input {
  width: 100%;
  padding: 15px 25px;
  font-size: 16px;
  border: none;
  border-radius: 50px;
  background: rgba(255, 255, 255, 0.95);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  outline: none;
  transition: transform 0.2s, box-shadow 0.2s;
}

.search input:focus {
  transform: scale(1.02);
  box-shadow: 0 6px 25px rgba(0, 0, 0, 0.15);
}

/* 链接卡片 */
.links {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
  margin-bottom: 40px;
}

.card {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 16px;
  padding: 20px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.card-title {
  font-size: 18px;
  color: #7d7eb2;
  margin-bottom: 15px;
  padding-bottom: 10px;
  border-bottom: 2px solid #e2b3cf;
}

.link-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.link-item {
  display: inline-block;
  padding: 8px 16px;
  background: linear-gradient(135deg, #e2b3cf 0%, #7d7eb2 100%);
  color: #fff;
  text-decoration: none;
  border-radius: 20px;
  font-size: 14px;
  transition: transform 0.2s, box-shadow 0.2s;
}

.link-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(125, 126, 178, 0.4);
}

/* 底部 */
.footer {
  text-align: center;
  color: rgba(255, 255, 255, 0.8);
  font-size: 14px;
}
</style>
