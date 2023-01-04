<script lang="ts">
  import Button from '$lib/button/Button.svelte';
  import Icon from '$lib/icon/Icon.svelte';
  import Countdown from '$lib/section/countdown/Countdown.svelte';
  import Modal from '$lib/modal/Modal.svelte';
  import { openModal } from 'svelte-modals';

  function handleClick() {
    const url ='https://gdg.community.dev/events/details/google-gdg-settat-presents-devfest-settat-x-marrakesh-2022/'
    window.open(url, '_blank').focus();
  }
</script>

<section
  id="hero"
  class="flex w-full flex-col items-center justify-start space-y-8 px-24 transition-all  duration-500 ease-in-out"
>
  <div
    id="hero-content-group"
    class="flex flex-col items-center justify-start space-y-8"
  >
    <div class="bg-text-container max-w-7xl">
      <div class="animate-text">
        <span>DevFest22</span>
        <span>DevFest22</span>
      </div>
      <div class="animate-text left">
        <span>DevFest22</span>
        <span>DevFest22</span>
      </div>
    </div>

    <h1
      class="text-start text-4xl font-bold tracking-tight text-black md:text-center md:text-6xl lg:text-center lg:text-7xl"
    >
      Google’s most awaited developer conference
    </h1>
    <p class="max-w-2xl text-start text-gray-700 md:text-center lg:text-center">
      Come learn, network and celebrate with the Google Developer Ecosystem
      while also learning ML, Cloud, and Web.
    </p>
  </div>

  <div
    id="hero-cta-group"
    class="flex w-full max-w-2xl flex-col items-center justify-start space-y-4 md:flex-row md:space-x-4 md:space-y-0 lg:flex-row"
  >
    <Button
      id="button-hero-get-tickets"
      title="Get Your Tickets"
      onClick={() => handleClick()}
    >
      <Icon width="20" height="20" name="ticket" />
    </Button>

    <Button
      id="button-hero-add-to-calendar"
      title="Add to calendar"
      isSecondaryButton={true}
      onClick={() =>
        window.open(
          'https://calendar.google.com/calendar/u/0/r/eventedit?text=DevFest2022+Settat+x+Marrakesh&details=Welcome+to+DevFest+2022+Settat+x+Marrakesh.+This+is+GDG%27s+most+awaited+developer+conference.%0A%0ANote:+This+event+is+invite+only.+Please+visit+https://devfest22.gdgsettat.ma+for+more+info.&dates=20230107T093000/20230107T173000&location=Facult%C3%A9+des+sciences+et+techniques,+BP+:+577,+Route+de+Casa,+Settat,+Morocco'
        )}
    >
      <i class="fa fa-calendar" />
    </Button>
  </div>

  <div
    class="flex w-full flex-col items-center justify-center space-y-3 text-xl sm:flex-row sm:space-y-0 sm:space-x-6"
  >
    <div class="flex items-center space-x-2">
      <i class="fa fa-calendar" />
      <p>7th January</p>
      <i class="fa fa-location-arrow" />
      <a href="https://goo.gl/maps/4Cd2obaCUHUJ8GJ76"
        ><p>FST Settat</p></a>
    </div>
  </div>
  <div class="items-center">
    <Countdown />
  </div>
</section>

<style>
  #hero {
    transform: skewY(-5deg);
  }

  .bg-text-container {
    transform: translateX(-50%);
    left: 50%;
    position: absolute;
    z-index: -999;
  }

  span {
    font-size: 280px;
    color: transparent;
    -webkit-text-stroke: 2px #30442a;
    text-transform: uppercase;
    display: inline-block;
    line-height: 0.75;
    min-width: auto;
    font-weight: 200;
    opacity: 0.1;
  }

  @keyframes text-scrolling {
    0% {
      transform: translate3d(-100%, 0, 0);
    }
    100% {
      transform: translate3d(0%, 0, 0);
    }
  }
  .animate-text {
    animation: text-scrolling 20s linear infinite;
    will-change: transform;
    display: block;
    position: relative;
    white-space: nowrap;
  }
  .animate-text.left {
    animation-direction: reverse;
  }
</style>
