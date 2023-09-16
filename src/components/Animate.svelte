<script>
  import gsap from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  import { onMount } from 'svelte';
  gsap.registerPlugin(ScrollTrigger);
  const timeLineScroll = gsap.timeline();
  const timeLine = gsap.timeline();
  const gsapMatchMedia = gsap.matchMedia();
  onMount(() => {
    // scroll animations

    timeLineScroll.from('#seccion2', {
      xPercent: -100,
    });
    timeLineScroll.from('#elipses', {
      y: 800,
      opacity: 0,
    });
    timeLineScroll.to('#elipses', {
      y: -500,
      opacity: 0,
    });
    timeLineScroll.from('#aboutme', {
      y: 500,
      opacity: 0,
    });
    timeLineScroll.to('#aboutme', {
      y: -500,
      opacity: 0,
    });
    timeLineScroll.from('#about-1', {
      scale: 0,
      opacity: 0,
      duration: 1,
    });
    timeLineScroll.to('#about-1', {
      scale: 0,
      opacity: 0,
      delay: 1,
    });
    timeLineScroll.from('#about-2', {
      y: 500,
      opacity: 0,
    });
    timeLineScroll.to('#about-2', {
      y: -500,
      opacity: 0,
    });
    timeLineScroll.from('#about-3', {
      y: 500,
      opacity: 0,
    });
    timeLineScroll.to('#about-3', {
      y: -500,
      opacity: 0,
    });
    timeLineScroll.from('#about-4', {
      y: 500,
      opacity: 0,
    });
    timeLineScroll.to('#about-4', {
      y: -500,
      opacity: 0,
    });
    timeLineScroll.from('#about-5', {
      y: 500,
      opacity: 0,
    });
    timeLineScroll.to('#about-5', {
      y: -500,
      opacity: 0,
    });

    timeLineScroll.from('#seccion4', {
      yPercent: 100,
    });
    timeLineScroll.from(
      '#project-card-1',
      {
        scale: 0,
        duration: 3,
        y: 1000,
        delay: 1,
        ease: 'power4.out',
      },
      '-=.5'
    );
    timeLineScroll.to('#project-card-1', {
      y: -800,
    });
    timeLineScroll.from('#project-card-2', {
      y: 1000,
      duration: 1,
      ease: 'power4.out',
    });
    timeLineScroll.to('#project-card-2', {
      yPercent: -110,
    });
    gsapMatchMedia.add('(max-width:640px)', () => {
      timeLineScroll.to('#project-card-2', {
        yPercent: -90,
      });
    });

    //static animations
    timeLine.from('#text-cover1', {
      x: 300,
      ease: 'power.out',
    });
    timeLine.to('#text-cover1', {
      x: -700,
      ease: 'power.out',
    });
    timeLine.from(
      '#text1',
      {
        x: 700,
      },
      '-=1'
    );
    timeLine.from(
      '#text-cover2',
      {
        x: 700,
      },
      '-=0.7'
    );
    timeLine.from(
      '#text2',
      {
        x: 700,
      },
      '-=0.5'
    );
    timeLine.to(
      '#text-cover2',
      {
        x: -700,
      },
      '-=0.01'
    );
    ScrollTrigger.create({
      animation: timeLineScroll,
      trigger: '#app',
      start: 'top top',
      end: '+=6000',
      pin: true,
      scrub: true,
    });
  });
</script>

<div class="w-full h-screen flex-col items-center sm:gap-5 flex">
  <div class="w-full flex flex-col sm:items-end items-center sm:pr-28">
    <div class="relative overflow-hidden">
      <div class="absolute w-full h-full bg-black z-10" id="text-cover1" />
      <h2
        class=" text-neutral-800 text-[69.33px] sm:text-9xl font-[600] font-['Lexend'] text-right"
        id="text1"
      >
        hello
      </h2>
    </div>
    <div class="relative overflow-hidden">
      <div class="absolute w-full h-full bg-black z-10" id="text-cover2" />
      <h1
        class=" text-neutral-800 sm:text-9xl text-[69.33px] font-[600] font-['Lexend'] 2xl:w-full sm:flex sm:text-right text-center"
        id="text2"
      >
        I’m Marcos
      </h1>
    </div>
  </div>
  <div
    class=" w-full justify-between items-center flex flex-col sm:flex-row gap-20"
  >
    <div
      class="w-full sm:w-[475px] py-[21px] flex-col sm:justify-start sm:items-start justify-center gap-2.5 inline-flex"
    >
      <h2
        class=" 2xl:w-full text-neutral-800 sm:text-7xl text-5xl font-semibold font-['Lexend'] sm:text-left text-center"
      >
        My
      </h2>
      <h2
        class="text-center text-neutral-800 sm:text-7xl text-5xl font-semibold font-['Lexend']"
      >
        Portfolio
      </h2>
      <h2
        class="text-center text-neutral-800 sm:text-7xl text-5xl font-semibold font-['Lexend']"
      >
        Showcase
      </h2>
    </div>
    <div class="">
      <h2
        class="-rotate-90 text-neutral-800 text-8xl font-black font-['Lexend']"
      >
        2K23
      </h2>
    </div>
  </div>
</div>
