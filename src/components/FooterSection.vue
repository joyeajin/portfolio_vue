<template lang="">
  <footer id="footer" role="contentinfo">
    <div class="footer__inner">
      <div class="footer__text">
        <span>joyeajin</span>
        <span>© yeajin</span>
      </div>
      <div class="footer__info">
        <div class="left">
          <div class="title">
            <a href="#">chat</a>
          </div>
          <p>게시판과 실시간 채팅 이용 가능합니다.</p>
        </div>
        <div class="right">
          <h3>social</h3>
          <ul v-for="(footer, index) in footerText" :key="index">
            <li>
              <a :href="footer.link">{{ footer.title }}</a>
              <em>{{ footer.desc }}</em>
            </li>
          </ul>
        </div>
      </div>
      <div class="footer__right">
        이 사이트는 vue를 이용하여 제작하였습니다.
      </div>
    </div>
  </footer>
</template>

<script>
import { footerText } from "@/constants/index.js";

export default {
  name: "FooterSection",
  data() {
    return {
      footerText: footerText,
    };
  },
};
</script>

<style lang="scss" scoped>
#footer {
  font-family: var(--mainKor-font);
}
.footer__inner {
  padding: 16px;

  .footer__text {
    font-size: 12px;
    text-transform: uppercase;
    border-top: 1px solid var(--black);
    border-bottom: 1px solid var(--black);
    display: flex;
    justify-content: space-between;
  }
  .footer__info {
    display: flex;
    justify-content: space-between;
    margin: 100px 0;

    @media (max-width: 800px) {
      flex-direction: column;
    }

    .left {
      width: 40%;

      @media (max-width: 800px) {
        width: 100%;
      }

      .title {
        border-top: 2px solid var(--black);
        border-bottom: 1px solid var(--black);
        padding: 20px 0;
        text-transform: uppercase;
        font-weight: 700;
        background: url(@/assets/img/arrow.svg) no-repeat right 20px;
        transition: all 0.3s;

        &:hover {
          background-color: var(--black400);
          padding-left: 10px;
          border-color: transparent;
        }
      }
      .desc {
        font-size: 12px;
        padding-top: 20px;

        @media (max-width: 800px) {
          margin-bottom: 40px;
        }
      }
    }

    .right {
      width: 50%;

      @media (max-width: 800px) {
        width: 100%;
      }

      h3 {
        border-top: 2px solid var(--black);
        font-size: 10px;
        margin-bottom: 40px;
        padding-top: 10px;
      }
      ul {
        border-top: 1px solid var(--black);

        li {
          border-bottom: 1px solid var(--black);

          a {
            padding: 14px 0;
            font-size: 14px;
            display: inline-block;
            text-transform: uppercase;
          }
          em {
            font-size: 12px;
            padding-left: 10px;
            opacity: 0;
            transition: all 0.3s;
          }

          &:hover {
            em {
              opacity: 1;
            }
          }
        }
      }
    }
  }
  .footer__right {
    text-align: center;
    text-transform: uppercase;
    font-size: 12px;
    margin-bottom: 20px;
  }
}
</style>
