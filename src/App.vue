<script setup>
const schoolUrl = 'https://www.csu.edu.cn/'
const admissionUrl = 'https://zhaosheng.csu.edu.cn/'

const navItems = [
  { label: '学校概况', href: '#about' },
  { label: '办学特色', href: '#strength' },
  { label: '学科布局', href: '#academics' },
  { label: '校园生活', href: '#life' },
  { label: '了解更多', href: '#contact' },
]

const quickFacts = [
  {
    value: '2000年',
    title: '合并组建年份',
    label: '由原中南工业大学、湖南医科大学、长沙铁道学院合并组建',
  },
  {
    value: '11个门类',
    title: '覆盖范围',
    label: '涵盖哲、经、法、教、文、理、工、医、管、艺、交叉学科',
  },
  {
    value: '5个学科',
    title: '“双一流”入选',
    label: '数学、材料、冶金、矿业、交通运输工程入选建设名单',
  },
  {
    value: '316.90万㎡',
    title: '校园占地',
    label: '学校产权土地面积，跨湘江两岸，依岳麓、临湘水',
  },
]

const features = [
  {
    title: '工科优势突出',
    tag: '工程现场',
    body: '围绕材料、冶金、矿业、土木、交通运输等优势方向，持续服务制造强国、交通强国和资源安全等领域。',
  },
  {
    title: '湘雅医学底蕴',
    tag: '生命健康',
    body: '湘雅医学传统深厚，医学教育、临床医学与生命科学研究相互支撑，形成面向人民健康的育人与科研体系。',
  },
  {
    title: '交叉融合培养',
    tag: '创新平台',
    body: '依托综合性大学平台，推进新工科、新医科与信息技术、管理科学、人文社科融合，培养复合型创新人才。',
  },
]

const disciplines = [
  { label: '材料科学与工程', url: 'https://mse.csu.edu.cn/' },
  { label: '冶金工程', url: 'https://smse.csu.edu.cn/' },
  { label: '矿业工程', url: 'https://srse.csu.edu.cn/' },
  { label: '交通运输工程', url: 'https://stte.csu.edu.cn/' },
  { label: '临床医学', url: 'https://xysm.csu.edu.cn/' },
  { label: '土木工程', url: 'https://civil.csu.edu.cn/' },
  { label: '控制科学与工程', url: 'https://soa.csu.edu.cn/' },
  { label: '管理科学与工程', url: 'https://bs.csu.edu.cn/' },
]

const lifeItems = [
  {
    title: '科研训练',
    body: '学生可参与导师课题、学科竞赛、创新创业训练，在真实项目中提升研究与协作能力。',
  },
  {
    title: '开放交流',
    body: '学校推进国际合作与校际交流，鼓励学生拓展全球视野与跨文化沟通能力。',
  },
  {
    title: '综合发展',
    body: '丰富的社团、志愿服务、文体活动与实践平台，为学生提供面向社会的成长空间。',
  },
]

const campusScenes = [
  {
    title: '校门地标',
    image: '/images/csu-sina-01.jpg',
  },
  {
    title: '湖畔楼宇',
    image: '/images/csu-sina-02.jpg',
  },
]

const lifeScenes = [
  {
    title: '校园入口',
    image: '/images/csu-win3000-01.jpg',
  },
]

const changshaLinks = [
  { label: '岳麓山', url: 'https://www.csyouji.cn/yls' },
  { label: '橘子洲', url: 'https://www.yuelu.gov.cn/zjxq/xqsj/202506/t20250630_11901612.html' },
  { label: '湘江新区', url: 'https://www.yuelu.gov.cn/zjxq/' },
  { label: '马栏山视频', url: 'https://cyfz.csmls.gov.cn/' },
]
</script>

<template>
  <header class="topbar">
    <nav class="nav" aria-label="页面导航">
      <a class="brand" href="#top" aria-label="中南大学介绍首页">
        <span class="brand-mark">中</span>
        <span>中南大学</span>
      </a>
      <div class="nav-links">
        <a v-for="item in navItems" :key="item.href" :href="item.href">
          {{ item.label }}
        </a>
      </div>
    </nav>
  </header>

  <main id="top">
    <section class="hero" aria-labelledby="hero-title">
      <div class="hero-bg-stack" aria-hidden="true">
        <span class="hero-bg bg-campus-day"></span>
        <span class="hero-bg bg-campus-night"></span>
        <span class="hero-bg bg-student-activity"></span>
        <span class="hero-bg bg-student-sports"></span>
        <span class="hero-bg bg-stone"></span>
      </div>
      <div class="hero-inner">
        <div class="hero-copy-block">
          <p class="eyebrow">Central South University</p>
          <h1 id="hero-title">中南大学</h1>
          <p class="hero-copy">
            坐落于湖南长沙，是教育部直属全国重点大学，入选国家“双一流”“211工程”“985工程”，以工学、医学、管理学等多学科交叉融合见长。
          </p>
          <div class="hero-actions">
            <a class="btn primary" href="#about">查看学校概况</a>
            <a class="btn secondary" :href="schoolUrl" target="_blank" rel="noreferrer">访问官网</a>
          </div>
        </div>

        <div class="hero-collage" aria-label="校园多场景">
          <figure v-for="scene in campusScenes" :key="scene.title">
            <img :src="scene.image" :alt="scene.title" />
          </figure>
          <figure>
            <img src="/images/csu-maigoo-01.jpg" alt="中南大学校园风景" />
          </figure>
        </div>
      </div>

      <div class="quick-facts" aria-label="学校速览">
        <div v-for="fact in quickFacts" :key="fact.value" class="fact">
          <strong>{{ fact.value }}</strong>
          <b>{{ fact.title }}</b>
          <span>{{ fact.label }}</span>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="wrap">
        <div class="section-head">
          <h2>扎根湖湘，服务国家战略的综合性研究型大学</h2>
          <p class="lead">
            中南大学兼具矿冶、医学、交通运输等鲜明底色，长期面向国家重大需求培养创新人才、开展科学研究与社会服务。
          </p>
        </div>

        <div class="about-grid">
          <article class="story">
            <p>
              学校源流可追溯至 1903 年创办的湖南高等实业学堂和 1914 年创办的湘雅医学专门学校。2000 年 4 月，原中南工业大学、湖南医科大学、长沙铁道学院合并组建为中南大学。
            </p>
            <p>
              学校坚持“知行合一、经世致用”的办学精神，形成了工医见长、理工医管文法艺多学科协调发展的格局，在有色金属、轨道交通、生命医学等领域具有深厚积累。
            </p>
            <p>
              作为教育部直属高校，中南大学面向世界科技前沿、经济主战场、国家重大需求和人民生命健康，持续推动人才培养、科研创新与开放合作。
            </p>
          </article>

          <aside class="motto-panel" aria-label="校训">
            <small>校训</small>
            <b>知行合一<br />经世致用</b>
          </aside>
        </div>

        <div class="about-mosaic" aria-label="学校发展脉络">
          <div>
            <span>1903年</span>
            <strong>实业教育源流</strong>
          </div>
          <div>
            <span>1914年</span>
            <strong>湘雅医学传承</strong>
          </div>
          <div>
            <span>2000年</span>
            <strong>三校合并组建</strong>
          </div>
        </div>
      </div>
    </section>

    <section class="feature-band" id="strength">
      <div class="wrap">
        <div class="section-head">
          <h2>回应真实问题，连接产业与科研的办学特色</h2>
          <p class="lead">
            中南大学的学科传统与产业需求、临床实践、工程现场紧密相连，强调把知识转化为解决复杂问题的能力。
          </p>
        </div>

        <div class="features">
          <article v-for="(feature, index) in features" :key="feature.title" class="feature">
            <div class="feature-top">
              <span class="num">特色 {{ String(index + 1).padStart(2, '0') }}</span>
              <span class="feature-tag">{{ feature.tag }}</span>
            </div>
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.body }}</p>
          </article>
        </div>
      </div>
    </section>

    <section id="academics">
      <div class="wrap">
        <div class="schools">
          <div>
            <h2>贯通多元学科，支撑创新培养的学术体系</h2>
            <p class="lead academics-copy">
              学校拥有较完整的人才培养层次和学科平台，学科覆盖面广，优势学科特色鲜明。
            </p>
          </div>
          <ul class="discipline-list" aria-label="学科方向">
            <li v-for="discipline in disciplines" :key="discipline.label">
              <a :href="discipline.url" target="_blank" rel="noreferrer">
                {{ discipline.label }}
              </a>
            </li>
          </ul>
        </div>

        <div class="campus-card">
          <div>
            <h3>在长沙读大学</h3>
            <p>
              中南大学位于历史文化名城长沙，校园依山傍水，连接岳麓山、湘江与城市创新生态。学习、科研、临床、工程实践与城市生活在这里形成紧密联动。
            </p>
          </div>
          <div class="academic-scenes" aria-label="长沙相关入口">
            <a v-for="link in changshaLinks" :key="link.label" :href="link.url" target="_blank" rel="noreferrer">
              {{ link.label }}
            </a>
          </div>
        </div>
      </div>
    </section>

    <section class="feature-band" id="life">
      <div class="wrap">
        <div class="section-head">
          <h2>融入多元场景，陪伴学生成长的校园生活</h2>
          <p class="lead">
            从课堂、实验室、医院到社团、体育场和创新创业平台，学生可以在多元场景中探索专业志趣与个人成长路径。
          </p>
        </div>

        <div class="life-grid">
          <div class="life-gallery" aria-label="中南大学校园风景">
            <img
              v-for="scene in lifeScenes"
              :key="scene.title"
              :src="scene.image"
              :alt="scene.title"
            />
          </div>
          <div class="life-list">
            <article v-for="item in lifeItems" :key="item.title" class="life-item">
              <h3>{{ item.title }}</h3>
              <p>{{ item.body }}</p>
            </article>
          </div>
        </div>
      </div>
    </section>

    <section class="cta" id="contact">
      <div class="wrap cta-inner">
        <div>
          <h2>连接官方渠道，获取权威发布的中南大学信息</h2>
          <p>
            招生政策、院系设置、科研平台、校园新闻等信息，请以中南大学官方网站及招生办公室发布内容为准。
          </p>
        </div>
        <div class="cta-links">
          <a class="btn primary" :href="schoolUrl" target="_blank" rel="noreferrer">学校官网</a>
          <a class="btn secondary" :href="admissionUrl" target="_blank" rel="noreferrer">本科招生网</a>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="wrap">
      <div>
        页面信息参考中南大学官网“学校概况”等公开资料，相关数据以官方最新发布为准。资料核对时间：2026 年 6 月 1 日。
      </div>
      <div>
        官方链接：
        <a :href="schoolUrl" target="_blank" rel="noreferrer">中南大学官网</a>
        ·
        <a :href="admissionUrl" target="_blank" rel="noreferrer">中南大学本科招生网</a>
      </div>
    </div>
  </footer>
</template>
