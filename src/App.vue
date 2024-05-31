<template>
  <div class="wrapp">
    <main class="main">
      <section class="section">
        <div class="section__wrapp">
          <div class="section__item">
            <div class="section__img">
              <img
                src="https://images.unsplash.com/photo-1716630115181-f84021ed7849?q=80&w=2796&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                alt=""
              />
            </div>
            <div class="section__txt">
              <span class="section__span"> work 01 </span>
              <h2 class="section__title">
                Position <span class="stroke">Sticky</span>
              </h2>
              <img class="star" src="./assets/star.svg" alt="" />
            </div>
          </div>

          <div class="section__item">
            <div class="section__txt">
              <span class="section__span"> work 02 </span>
              <h2 class="section__title">web design</h2>
              <img class="star" src="./assets/star.svg" alt="" />
            </div>
            <div class="section__img">
              <img
                src="https://images.unsplash.com/photo-1716470952592-9be1f999878a?q=80&w=2267&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                alt=""
              />
            </div>
          </div>

          <div class="section__item">
            <div class="section__img">
              <img
                src="https://images.unsplash.com/photo-1716470940908-d1be8dba5b59?q=80&w=2274&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                alt=""
              />
            </div>
            <div class="section__txt">
              <span class="section__span"> work 03 </span>
              <h2 class="section__title">ux/ui design</h2>
              <img class="star" src="./assets/star.svg" alt="" />
            </div>
          </div>

          <div class="section__item">
            <div class="section__txt">
              <span class="section__span"> work 04 </span>
              <h2 class="section__title">brand design</h2>
              <img class="star" src="./assets/star.svg" alt="" />
            </div>
            <div class="section__img">
              <img
                src="https://images.unsplash.com/photo-1716630115669-c0351993bcd9?q=80&w=2792&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                alt=""
              />
            </div>
          </div>
        </div>
      </section>

      <section class="section-text">
        <div class="content">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum ea
            quia vitae officiis dicta placeat nostrum possimus ducimus omnis
            aliquid! Lorem ipsum dolor sit amet consectetur adipisicing elit.
            Laborum ea quia vitae officiis dicta placeat nostrum possimus
            ducimus omnis aliquid! Lorem ipsum dolor sit amet consectetur
            adipisicing elit. Laborum ea quia vitae officiis dicta placeat
            nostrum possimus ducimus omnis aliquid!
          </p>
        </div>
      </section>
      <section class="section-text">
        <div class="content">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum ea
            quia vitae officiis dicta placeat nostrum possimus ducimus omnis
            aliquid! Lorem ipsum dolor sit amet consectetur adipisicing elit.
            Laborum ea quia vitae officiis dicta placeat nostrum possimus
            ducimus omnis aliquid! Lorem ipsum dolor sit amet consectetur
            adipisicing elit. Laborum ea quia vitae officiis dicta placeat
            nostrum possimus ducimus omnis aliquid!
          </p>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import Lenis from "@studio-freight/lenis";

export default {
  data() {
    return {
      works: [
        {
          imageUrl:
            "https://images.unsplash.com/photo-1716630115181-f84021ed7849?q=80&w=2796&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          altText: "work 01",
          label: "work 01",
          title: "Position",
          sticky: true,
        },
        // Define other works similarly
      ],
      texts: [
        "Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum ea quia vitae officiis dicta placeat nostrum possimus ducimus omnis aliquid! Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum ea quia vitae officiis dicta placeat nostrum possimus ducimus omnis aliquid! Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum ea quia vitae officiis dicta placeat nostrum possimus ducimus omnis aliquid!",
        // Define other texts similarly
      ],
      lenis: null,
    };
  },
  mounted() {
    this.lenis = new Lenis({
      duration: 1.2,
      easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
      direction: "vertical",
      gestureDirection: "vertical",
      smooth: true,
      mouseMultiplier: 1,
      smoothTouch: false,
      touchMultiplier: 2,
      infinite: false,
    });

    // Get scroll value
    this.lenis.on(
      "scroll",
      ({ scroll, limit, velocity, direction, progress }) => {
        console.log({ scroll, limit, velocity, direction, progress });
      }
    );

    // Start animation loop
    this.raf();
  },
  methods: {
    raf(time) {
      this.lenis.raf(time);
      requestAnimationFrame(this.raf);
    },
  },
};
</script>

<style>
@import url(./assets/styles.css);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
