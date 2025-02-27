<template>
  <section class="hero">
    <div class="container">
      <div class="hero-container">
        <h1 class="title">
          The Foundation for your
          <br>
					<span>
						next
						<Typewriter :words="['business', 'project', 'idea']" />
					</span>
        </h1>

        <h2 class="subtitle">
          The Node.js Framework highly focused on developer ergonomics, stability and speed.
          Start building efficient, reliable and scalable server-side applications.
        </h2>

        <div class="cta">
          <!-- @hardcoded -->
          <Button title="Get Started" href="/guides/quick-start" :external="false" />
          <Button theme="secondary" href="https://github.com/adonisjs/core/stargazers" :external="true" class="gh-button-wrapper">
            <div class="gh-button">
              <span class="icon">
                <svg viewBox="0 0 16 16" width="16" height="16" class="octicon octicon-star" aria-hidden="true"><path fill-rule="evenodd" fill="currentColor" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"></path></svg>
              </span>
              <span>
                Star
              </span>
              <span class="count">8K+</span>
            </div>
          </Button>
        </div>

        <div class="code-showcase-wrapper" v-if="codeHighlightSections.length">
          <CodeGroup :sections="codeHighlightSections" />
        </div>
      </div>
    </div>
    <div class="dots-bg"></div>
  </section>
</template>

<script>
  import Button from '~/components/Button.vue'
  import CodeGroup from '~/components/Home/CodeGroup.vue'
  import Typewriter from '~/components/Typewriter.vue'

  export default {
    components: { Button, CodeGroup, Typewriter },
    data () {
      return {
        codeHighlightSections: []
      }
    },
    mounted () {
      this.codeHighlightSections = this.$static.showCaseTabs.edges.map((edge) => edge.node)
    }
  }
</script>

<static-query>
  query {
    showCaseTabs: allHomePageShowCaseTabs(order: ASC) {
      edges {
        node {
          title
          code
        }
      }
    }
  }
</static-query>

<style scoped>
  .hero-container {
    padding-top: 80px;
  }

  .title {
    font-size: 5rem;
    color: var(--grey-900);
    font-weight: 700;
    line-height: 58px;
    margin-bottom: 34px;
  }

  .subtitle {
    font-weight: 500;
    font-size: 2.4rem;
    line-height: 30px;
    margin-bottom: 1rem;
    color: var(--grey-700);
  }

  .subtitle:last-of-type {
    margin-bottom: 40px;
  }

  .code-showcase-wrapper {
    margin-top: 80px;
    position: relative;
    z-index: 1;
  }

  .code-showcase-wrapper div {
    border-radius: 6px;
    background-color: var(--pre-bg);
  }

  .gh-button-wrapper {
    margin-top: 15px;
  }

  .gh-button {
    display: flex;
    align-items: center;
    height: 100%;
  }

  .gh-button .icon {
    position: relative;
    top: 3px;
    color: var(--grey-900);
    margin-right: 5px;
    margin-bottom: -1px;
  }

  .gh-button .count {
    margin-left: 10px;
    padding-left: 10px;
    height: 100%;
    border-left: 1px solid;
  }

  .cta {
    display: flex;
    align-items: flex-start;
    flex-direction: column;
  }

  @media (min-width: 768px) {
    .hero-container {
      max-width: 700px;
      text-align: center;
      margin: auto;
    }

    .title {
      font-size: 5.4rem;
      line-height: 48px;
      padding: 0 30px;
    }

    .subtitle {
      font-size: 2.4rem;
    }

    .gh-button-wrapper {
      margin-top: 0;
      margin-left: 15px;
    }

    .cta {
      flex-direction: row;
      justify-content: center;
    }
  }

  @media (min-width: 1024px) {
    .hero {
      position: relative;
    }

    .dots-bg {
      background-position:0 100%;
      background-repeat:repeat-x;
      background-size:14px;
      background-image:url('data:image/svg+xml;utf8,<svg width="20" height="317" viewBox="0 0 20 317" fill="none" xmlns="http://www.w3.org/2000/svg"> <g opacity="0.1"> <path d="M4.45203 256.184C2.54551 256.184 1 254.648 1 252.753C1 250.858 2.54551 249.322 4.45203 249.322C6.35854 249.322 7.9043 250.858 7.9043 252.753C7.9043 254.648 6.35854 256.184 4.45203 256.184Z" fill="url(%23paint0_linear)"/> <path d="M4.45203 275.789C2.54551 275.789 1 274.253 1 272.359C1 270.464 2.54551 268.928 4.45203 268.928C6.35854 268.928 7.9043 270.464 7.9043 272.359C7.9043 274.253 6.35854 275.789 4.45203 275.789Z" fill="url(%23paint1_linear)"/> <path d="M4.45203 295.395C2.54551 295.395 1 293.859 1 291.964C1 290.069 2.54551 288.533 4.45203 288.533C6.35854 288.533 7.9043 290.069 7.9043 291.964C7.9043 293.859 6.35854 295.395 4.45203 295.395Z" fill="url(%23paint2_linear)"/> <path d="M4.45203 315C2.54551 315 1 313.464 1 311.569C1 309.674 2.54551 308.138 4.45203 308.138C6.35854 308.138 7.9043 309.674 7.9043 311.569C7.9043 313.464 6.35854 315 4.45203 315Z" fill="url(%23paint3_linear)"/> <path d="M4.45203 179.724C2.54551 179.724 1 178.188 1 176.293C1 174.398 2.54551 172.862 4.45203 172.862C6.35854 172.862 7.9043 174.398 7.9043 176.293C7.9043 178.188 6.35854 179.724 4.45203 179.724Z" fill="url(%23paint4_linear)"/> <path d="M4.45203 199.329C2.54551 199.329 1 197.793 1 195.898C1 194.003 2.54551 192.467 4.45203 192.467C6.35854 192.467 7.9043 194.003 7.9043 195.898C7.9043 197.793 6.35854 199.329 4.45203 199.329Z" fill="url(%23paint5_linear)"/> <path d="M4.45203 218.934C2.54551 218.934 1 217.398 1 215.503C1 213.608 2.54551 212.072 4.45203 212.072C6.35854 212.072 7.9043 213.608 7.9043 215.503C7.9043 217.398 6.35854 218.934 4.45203 218.934Z" fill="url(%23paint6_linear)"/> <path d="M4.45203 238.539C2.54551 238.539 1 237.003 1 235.109C1 233.214 2.54551 231.678 4.45203 231.678C6.35854 231.678 7.9043 233.214 7.9043 235.109C7.9043 237.003 6.35854 238.539 4.45203 238.539Z" fill="url(%23paint7_linear)"/> <path d="M4.45203 100.322C2.54551 100.322 1 98.7863 1 96.8914C1 94.9966 2.54551 93.4605 4.45203 93.4605C6.35854 93.4605 7.9043 94.9966 7.9043 96.8914C7.9043 98.7863 6.35854 100.322 4.45203 100.322Z" fill="url(%23paint8_linear)"/> <path d="M4.45203 119.928C2.54551 119.928 1 118.392 1 116.497C1 114.602 2.54551 113.066 4.45203 113.066C6.35854 113.066 7.9043 114.602 7.9043 116.497C7.9043 118.392 6.35854 119.928 4.45203 119.928Z" fill="url(%23paint9_linear)"/> <path d="M4.45203 139.533C2.54551 139.533 1 137.997 1 136.102C1 134.207 2.54551 132.671 4.45203 132.671C6.35854 132.671 7.9043 134.207 7.9043 136.102C7.9043 137.997 6.35854 139.533 4.45203 139.533Z" fill="url(%23paint10_linear)"/> <path d="M4.45203 159.138C2.54551 159.138 1 157.602 1 155.707C1 153.812 2.54551 152.276 4.45203 152.276C6.35854 152.276 7.9043 153.812 7.9043 155.707C7.9043 157.602 6.35854 159.138 4.45203 159.138Z" fill="url(%23paint11_linear)"/> <path d="M4.45203 23.8618C2.54551 23.8618 1 22.3258 1 20.4309C1 18.5361 2.54551 17 4.45203 17C6.35854 17 7.9043 18.5361 7.9043 20.4309C7.9043 22.3258 6.35854 23.8618 4.45203 23.8618Z" fill="url(%23paint12_linear)"/> <path d="M4.45203 43.4671C2.54551 43.4671 1 41.931 1 40.0362C1 38.1413 2.54551 36.6053 4.45203 36.6053C6.35854 36.6053 7.9043 38.1413 7.9043 40.0362C7.9043 41.931 6.35854 43.4671 4.45203 43.4671Z" fill="url(%23paint13_linear)"/> <path d="M4.45203 63.0724C2.54551 63.0724 1 61.5363 1 59.6414C1 57.7466 2.54551 56.2105 4.45203 56.2105C6.35854 56.2105 7.9043 57.7466 7.9043 59.6414C7.9043 61.5363 6.35854 63.0724 4.45203 63.0724Z" fill="url(%23paint14_linear)"/> <path d="M4.45203 82.6776C2.54551 82.6776 1 81.1415 1 79.2467C1 77.3519 2.54551 75.8158 4.45203 75.8158C6.35854 75.8158 7.9043 77.3519 7.9043 79.2467C7.9043 81.1415 6.35854 82.6776 4.45203 82.6776Z" fill="url(%23paint15_linear)"/> </g> <defs> <linearGradient id="paint0_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint1_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint2_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint3_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint4_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint5_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint6_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint7_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint8_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint9_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint10_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint11_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint12_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint13_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint14_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> <linearGradient id="paint15_linear" x1="374.764" y1="315" x2="374.098" y2="-37.5446" gradientUnits="userSpaceOnUse"> <stop stop-color="%2324724D"/> <stop offset="1" stop-color="%23D2DAD7" stop-opacity="0"/> </linearGradient> </defs> </svg>');
      height: 200px;
      max-width: 1500px;
      max-height: 100%;
      margin: 0 auto;
      position: absolute;
      pointer-events: none;
      left: 0;
      right: 0;
      top: 60%;
      margin-top: -100px;
      opacity: 1;
    }

    .hero-container {
      padding-top: 120px;
      max-width: 900px;
    }

    .title {
      font-size: 6rem;
      line-height: 60px;
      padding: 0 0px;
      margin-bottom: 40px;
    }

    .subtitle {
      padding: 0 100px;
      line-height: 34px;
      font-size: 2.6rem;
      margin-bottom: 0;
    }

    .code-showcase-wrapper {
      margin-top: 80px;
      padding: 0 50px;
    }
  }
</style>
