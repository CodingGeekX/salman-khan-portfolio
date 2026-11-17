<script setup>
import { ref } from 'vue'
import cvUrl from '/Salman_Khan_Full_Stack_Developer.pdf'
import {
  ArrowDown, ArrowRight, ArrowUpRight, Code2, Download, Github, Linkedin,
  Mail, MapPin, Menu, X, Send, BriefcaseBusiness, Lightbulb, Users,
  Rocket, ExternalLink, CheckCircle2, Smartphone, Database, Globe, Terminal,
  Layers3, Zap, Cpu, MessageCircle
} from 'lucide-vue-next'

const menuOpen = ref(false)
const activeSection = ref('home')
const navItems = [
  { label: 'Home', href: '#home' }, { label: 'About', href: '#about' },
  { label: 'Skills', href: '#skills' }, { label: 'Experience', href: '#experience' },
  { label: 'Projects', href: '#projects' }, { label: 'Contact', href: '#contact' }
]
const skills = [
  { name: 'PHP', short: 'PHP', class: 'php', icon: Terminal },
  { name: 'Laravel', short: 'La', class: 'laravel', icon: Layers3 },
  { name: 'CodeIgniter', short: 'CI', class: 'codeigniter', icon: Zap },
  { name: 'Python', short: 'Py', class: 'python', icon: Terminal },
  { name: 'FastAPI', short: 'API', class: 'fastapi', icon: Rocket },
  { name: 'Vue.js', short: 'V', class: 'vue', icon: Code2 },
  { name: 'MySQL', short: 'SQL', class: 'mysql', icon: Database },
  { name: 'REST APIs', short: 'API', class: 'api', icon: Globe },
  { name: 'JavaScript', short: 'JS', class: 'js', icon: Cpu },
  { name: 'Git / GitHub', short: 'Git', class: 'git', icon: Github }
]
const projects = [
  {
    number: '01', title: 'Azaan — Masjid Management', category: 'Laravel · Vue ecosystem',
    description: 'A masjid management application for prayer times, device registration and mosque-focused features.',
    tags: ['Laravel', 'Filament', 'FCM'], icon: Smartphone, tone: 'mosque',
    detail: 'API development, database design, device management and push-notification workflows.'
  },

  {
    number: '02',
    title: 'Khabar Aapka',
    category: 'Full Stack Development',
    description: 'A news publishing platform with a public-facing website and admin panel to manage, edit, and publish news articles with multiple user roles.',
    tags: ['Laravel', 'Vue.js', 'PHP', 'MySQL', 'RBAC'],
    icon: Globe,
    tone: 'news',
    detail: 'Developed news management workflows, article publishing functionality, and role-based access control to manage permissions across different user roles.'
  },

  {
    number: '03', title: 'Fyers Trading Bot', category: 'Python · FastAPI',
    description: 'A grid-trading backend with streaming market data, order workflows and background processing.',
    tags: ['FastAPI', 'WebSocket', 'Redis'], icon: Zap, tone: 'trading',
    detail: 'FastAPI services, WebSocket streams, Celery tasks, Redis and SQLAlchemy/MySQL integration.'
  },
  {
    number: '04', title: 'Rishta Assist', category: 'CodeIgniter · MySQL',
    description: 'A matrimonial platform supporting community-focused discovery and web/mobile experiences.',
    tags: ['CodeIgniter', 'REST API', 'MySQL'], icon: Users, tone: 'rishta',
    detail: 'REST API development, relational data modelling and query performance improvements.'
  }
]
const experience = [
  {
    period: 'Jan 2023 — Jul 2026', duration: '3.5 years', role: 'Full Stack Developer',
    company: 'Softlabs Technologies Pvt. Ltd.', location: 'Mumbai, India',
    points: [
      'Developed and maintained web applications using PHP, Laravel, Vue.js and MySQL.',
      'Contributed to international projects including Bartercard, A.S.A.G., UBOMI and Avante.',
      'Built REST APIs, payment integrations, scheduled jobs and backend workflows.',
      'Worked on a Python FastAPI trading system with WebSockets and background tasks.'
    ]
  },
  {
    period: 'Apr 2022 — Dec 2022', duration: '9 months', role: 'PHP Developer',
    company: 'Maqja Consultancy Services', location: 'Mumbai, India',
    points: [
      'Built CodeIgniter REST APIs for web and mobile applications.',
      'Worked on Rishta Assist and Raah-e-Nijat projects.',
      'Improved MySQL queries, data handling and responsive user interfaces.'
    ]
  }
]

function closeMenu() { menuOpen.value = false }
function setActive(id) { activeSection.value = id }
</script>

<template>
  <div class="site-shell">
    <header class="site-header">
      <a class="brand" href="#home" aria-label="Salman Khan home" @click="closeMenu">
        <span class="brand-mark">SK<span>.</span></span>
        <span class="brand-name">Salman Khan</span>
      </a>
      <button class="mobile-menu" type="button" :aria-label="menuOpen ? 'Close menu' : 'Open menu'"
        @click="menuOpen = !menuOpen">
        <X v-if="menuOpen" :size="22" />
        <Menu v-else :size="22" />
      </button>
      <nav class="main-nav" :class="{ 'nav-open': menuOpen }" aria-label="Main navigation">
        <a v-for="item in navItems" :key="item.label" :href="item.href"
          :class="{ active: activeSection === item.href.slice(1) }"
          @click="setActive(item.href.slice(1)); closeMenu()">{{ item.label }}</a>
        <a class="nav-mobile-cv" :href="cvUrl" download>
          <Download :size="15" /> Download CV
        </a>
      </nav>
      <a class="button button-primary header-cv" :href="cvUrl" download>
        <Download :size="16" /> Download CV
      </a>
    </header>

    <main>
      <section id="home" class="hero section-wrap">
        <div class="hero-copy">
          <p class="eyebrow"><span class="status-dot"></span> AVAILABLE FOR OPPORTUNITIES</p>
          <p class="hero-intro">Hello, I'm</p>
          <h1>Salman <span class="gradient-text">Khan</span><span class="hero-period">.</span></h1>
          <h2>Full Stack <span>Developer</span></h2>
          <p class="hero-description">I build reliable, user-focused web applications with <strong>PHP, Laravel,
              CodeIgniter, Vue.js and Python.</strong> I enjoy turning complex problems into clean, scalable solutions.
          </p>
          <div class="hero-actions">
            <a class="button button-primary" href="#contact">Let's talk
              <ArrowRight :size="17" />
            </a>
            <a class="button button-outline" href="https://github.com/CodingGeekX/" target="_blank" rel="noreferrer">
              <Github :size="18" /> View GitHub
              <ArrowUpRight :size="15" />
            </a>
          </div>
          <div class="hero-meta">
            <span>
              <MapPin :size="16" /> Mumbai, India
            </span><i></i>
            <a href="mailto:khansalman.ks1998@gmail.com">
              <Mail :size="16" /> khansalman.ks1998@gmail.com
            </a>
          </div>
        </div>
        <div class="hero-art" aria-label="Decorative developer illustration">
          <div class="art-orbit orbit-one"></div>
          <div class="art-orbit orbit-two"></div>
          <div class="art-grid"></div>
          <div class="code-window">
            <div class="window-top"><span></span><span></span><span></span><small>developer.php</small></div>
            <div class="code-lines">
              <p><b>01</b> <span class="code-purple">class</span> <span class="code-blue">Developer</span></p>
              <p><b>02</b> {</p>
              <p><b>03</b> &nbsp; <span class="code-purple">public string</span> $focus =</p>
              <p><b>04</b> &nbsp; <span class="code-green">'build &amp; improve'</span>;</p>
              <p><b>05</b> &nbsp; <span class="code-purple">public function</span> <span
                  class="code-blue">create</span>()</p>
              <p><b>06</b> &nbsp; { <span class="code-muted">// make it useful</span> }</p>
              <p><b>07</b> }</p>
            </div>
          </div>
          <div class="floating-chip chip-api"><span class="chip-icon">
              <Code2 :size="18" />
            </span><span><b>REST APIs</b><small>Designed to scale</small></span></div>
          <div class="floating-chip chip-python"><span class="python-symbol">Py</span><span><b>Python +
                FastAPI</b><small>Backend engineering</small></span></div>
          <div class="hero-sticker"><span>CODE.</span><span>CREATE.</span><span class="gradient-text">GROW.</span>
            <ArrowDown :size="18" />
          </div>
          <div class="hero-visual-caption"><span class="caption-line"></span><span>Building digital experiences</span>
          </div>
        </div>
        <a class="scroll-cue" href="#about"><span class="scroll-mouse"></span> SCROLL TO EXPLORE
          <ArrowDown :size="13" />
        </a>
      </section>

      <section id="about" class="section section-wrap about-section">
        <div class="section-heading">
          <p class="eyebrow">A LITTLE ABOUT ME</p>
          <h2>Developer by craft.<br /><span class="gradient-text">Problem solver by nature.</span></h2>
        </div>
        <div class="about-layout">
          <div class="about-copy">
            <p>I'm a full stack developer with around <strong>4.5 years of experience</strong> building web applications
              and backend services. My work spans PHP and Laravel, CodeIgniter applications, Vue.js interfaces, REST
              APIs, and Python
              FastAPI services.</p>
            <p>I care about maintainable code, thoughtful architecture and products that make a real difference to the
              people using them.</p><a class="text-link" href="#experience">Explore my experience
              <ArrowRight :size="16" />
            </a>
          </div>
          <div class="about-stats">
            <article class="stat-card"><span class="stat-icon">
                <BriefcaseBusiness :size="22" />
              </span>
              <div><strong>4.5<span>+</span></strong>
                <p>Years of experience</p>
              </div>
            </article>
            <article class="stat-card"><span class="stat-icon">
                <Layers3 :size="22" />
              </span>
              <div><strong>Full stack</strong>
                <p>From APIs to UI</p>
              </div>
            </article>
            <article class="stat-card"><span class="stat-icon">
                <Lightbulb :size="22" />
              </span>
              <div><strong>Curious</strong>
                <p>Always learning</p>
              </div>
            </article>
            <article class="stat-card"><span class="stat-icon">
                <Users :size="22" />
              </span>
              <div><strong>Team-first</strong>
                <p>Collaborative mindset</p>
              </div>
            </article>
          </div>
        </div>
      </section>

      <section id="skills" class="section section-wrap skills-section">
        <div class="section-topline">
          <div>
            <p class="eyebrow">MY TOOLKIT</p>
            <h2>Skills & <span class="gradient-text">technologies</span></h2>
          </div>
          <p class="section-aside">The tools I use to turn ideas<br />into dependable products.</p>
        </div>
        <div class="skills-grid">
          <article v-for="skill in skills" :key="skill.name" class="skill-card"><span class="skill-logo"
              :class="skill.class">
              <component :is="skill.icon" :size="23" stroke-width="2.1" />
            </span><span>{{ skill.name }}</span></article>
        </div>
        <div class="skill-footnote"><span class="mini-check">
            <CheckCircle2 :size="15" />
          </span> Also comfortable with Git, cron jobs, webhooks, third-party integrations and debugging production
          issues.</div>
      </section>

      <section id="experience" class="section section-wrap experience-section">
        <div class="section-topline">
          <div>
            <p class="eyebrow">WHERE I'VE WORKED</p>
            <h2>Professional <span class="gradient-text">journey</span></h2>
          </div>
          <p class="section-aside">Learning, building and shipping<br />software with great teams.</p>
        </div>
        <div class="timeline">
          <article v-for="(job, index) in experience" :key="job.company" class="timeline-item">
            <div class="timeline-rail"><span class="timeline-dot"></span><span v-if="index !== experience.length - 1"
                class="timeline-line"></span></div>
            <div class="timeline-date"><strong>{{ job.period }}</strong><span>{{ job.duration }}</span></div>
            <div class="experience-card">
              <div class="experience-card-top">
                <div class="company-monogram">{{ index === 0 ? 'ST' : 'MC' }}</div>
                <div>
                  <h3>{{ job.company }}</h3>
                  <p>{{ job.role }} <span>·</span> {{ job.location }}</p>
                </div><span class="job-index">0{{ index + 1 }}</span>
              </div>
              <ul>
                <li v-for="point in job.points" :key="point">{{ point }}</li>
              </ul>
            </div>
          </article>
        </div>
      </section>

      <section id="projects" class="section section-wrap projects-section">
        <div class="section-topline">
          <div>
            <p class="eyebrow">SELECTED WORK</p>
            <h2>Things I've <span class="gradient-text">built</span></h2>
          </div>
          <p class="section-aside">A selection of products and<br />engineering work I've contributed to.</p>
        </div>
        <div class="projects-grid">
          <article v-for="project in projects" :key="project.number" class="project-card">
            <div class="project-art" :class="project.tone">
              <div class="project-art-glow"></div>
              <div class="project-number">{{ project.number }}</div>
              <component :is="project.icon" class="project-main-icon" :size="58" stroke-width="1.15" />
              <div class="project-art-label">{{ project.category }}</div><span class="project-corner">
                <ArrowUpRight :size="19" />
              </span>
            </div>
            <div class="project-content">
              <p class="project-kicker">FEATURED PROJECT</p>
              <h3>{{ project.title }}</h3>
              <p class="project-description">{{ project.description }}</p>
              <p class="project-detail">{{ project.detail }}</p>
              <div class="tag-list"><span v-for="tag in project.tags" :key="tag">{{ tag }}</span></div>
            </div>
          </article>
        </div>
        <p class="projects-note"><span class="note-star">✳</span> Some projects represent work in progress or summaries
          of my contributions. Ask me for more technical details.</p>
      </section>

      <section id="contact" class="section section-wrap contact-section">
        <div class="contact-panel">
          <div class="contact-glow"></div>
          <div class="contact-copy">
            <p class="eyebrow">HAVE A PROJECT IN MIND?</p>
            <h2>Let's build something<br /><span class="gradient-text">meaningful.</span></h2>
            <p>I'm open to software development roles and interesting collaborations. If you think we'd work well
              together, I'd love to hear from you.</p><a class="button button-primary"
              href="mailto:khansalman.ks1998@gmail.com?subject=Let's%20connect">
              <Send :size="16" /> Get in touch
              <ArrowRight :size="16" />
            </a>
          </div>
          <div class="contact-details"><a href="mailto:khansalman.ks1998@gmail.com" class="contact-detail"><span>
                <Mail :size="19" />
              </span>
              <div><small>EMAIL ME AT</small><strong>khansalman.ks1998@gmail.com</strong></div>
              <ArrowUpRight :size="16" />
            </a>
            <div class="contact-detail"><span>
                <MapPin :size="19" />
              </span>
              <div><small>BASED IN</small><strong>Mumbai, India</strong></div>
            </div>
            <div class="contact-socials"><a href="https://github.com/CodingGeekX/" target="_blank" rel="noreferrer"
                aria-label="GitHub">
                <Github :size="19" />
              </a><a href="https://www.linkedin.com/in/salman-khan-47196a220" target="_blank" rel="noreferrer"
                aria-label="LinkedIn">
                <Linkedin :size="19" />
              </a><a href="mailto:khansalman.ks1998@gmail.com" aria-label="Email">
                <MessageCircle :size="19" />
              </a><span>Usually replies within 1–2 days</span></div>
          </div>
        </div>
      </section>
    </main>

    <footer class="site-footer section-wrap"><a class="brand footer-brand" href="#home"><span
          class="brand-mark">SK<span>.</span></span><span class="brand-name">Salman Khan</span></a>
      <p>Designed with care. Built with Vue.js.</p><span>© {{ new Date().getFullYear() }} Salman Khan</span><a
        class="back-top" href="#home" aria-label="Back to top">
        <ArrowDown :size="17" />
      </a>
    </footer>
  </div>
</template>
