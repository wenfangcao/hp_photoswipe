<template>
  <div>
    <div class="pswp" tabindex="-1" role="dialog" aria-hidden="true">
        <div class="pswp__bg"></div>
        <div class="pswp__scroll-wrap">
            <div class="pswp__container">
                <div class="pswp__item"></div>
                <div class="pswp__item"></div>
                <div class="pswp__item"></div>
            </div>
            <div class="pswp__ui pswp__ui--hidden">
                <div class="pswp__top-bar">
                    <div v-show="false" class="pswp__counter"></div>
                    <button class="pswp__button pswp__button--close" title="Close (Esc)"></button>
                    <!-- <button class="pswp__button pswp__button--share" title="Share"></button> -->
                    <!-- <button class="pswp__button pswp__button--fs" title="Toggle fullscreen"></button> -->
                    <button class="pswp__button pswp__button--zoom" title="Zoom in/out"></button>
                    <div class="pswp__preloader">
                        <div class="pswp__preloader__icn">
                          <div class="pswp__preloader__cut">
                            <div class="pswp__preloader__donut"></div>
                          </div>
                        </div>
                    </div>
                </div>
                <div class="pswp__share-modal pswp__share-modal--hidden pswp__single-tap">
                    <div class="pswp__share-tooltip"></div> 
                </div>
                <!-- <button class="pswp__button pswp__button--arrow--left" title="Previous (arrow left)">
                </button>
                <button class="pswp__button pswp__button--arrow--right" title="Next (arrow right)">
                </button> -->
                <div class="pswp__caption">
                    <div class="pswp__caption__center"></div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
  export default {
    methods: {
      show (imgs) {
        let _this = this
        let pswpElement = document.querySelectorAll('.pswp')[0];
        let options = {
          index: 0
        }
        new PhotoSwipe(pswpElement, PhotoSwipeUI_Default, imgs, options).init()
      }
    },
    created () {
      let link = [
        {
          type: 'link',
          href: 'https://cdn.bootcss.com/photoswipe/4.1.3/photoswipe.min.css',
          rel: 'stylesheet'
        },
        {
          type: 'link',
          href: 'https://cdn.bootcss.com/photoswipe/4.1.3/default-skin/default-skin.min.css',
          rel: 'stylesheet'
        },
        {
          type: 'script',
          src: 'https://cdn.bootcss.com/photoswipe/4.1.3/photoswipe.min.js'
        },
        {
          type: 'script',
          src: 'https://cdn.bootcss.com/photoswipe/4.1.3/photoswipe-ui-default.min.js'
        }
      ]

      for (let item of link) {
        let ele = document.createElement(item.type)
        for (let [key, val] of Object.entries(item)) {
          if (key !== 'type') {
            ele.setAttribute(key, val)
          }
        }
        document.head.appendChild(ele)
      }
    }
  }
</script>