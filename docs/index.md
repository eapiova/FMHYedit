---
title: Welcome
layout: home
description: The largest collection of free stuff on the internet!

hero:
  name: freemediaheckyeah
  tagline: The largest collection of free stuff on the internet!
  prelink:
    title: August Updates ✨
    link: /posts/aug-2024
  image:
    src: /test.png
    alt: FMHY Icon
  actions:
    - theme: brand
      text: See Beginners Guide
      link: /beginners-guide
    - theme: alt
      text: Posts
      link: /posts
    - theme: alt
      text: Contribute
      link: /other/contributing
    - theme: alt
      text: Discord
      link: https://discord.gg/Stz6y6NgNg
---
<p class="text-center text-lg text-gray-500 dark:text-gray-400">Or browse these pages ✨️</p>
<LinkCard title="Adblocking" href="/adblockvpnguide" tags="adblock,privacy" description="Learn how to block ads, trackers and other nasty things." />
<LinkCard title="Artificial Intelligence" href="/ai" tags="AI" description="Learn how to use AI to make your life easier." />
<LinkCard title="Streaming" href="/videopiracyguide" tags="movies" description="Stream, download and torrent all your favourite movies or shows!" />
<LinkCard title="Listening" href="/audiopiracyguide" tags="music" description="Stream, download and torrent songs, podcasts and more!" />
<LinkCard title="Gaming" href="/gamingpiracyguide" tags="gaming,emulation" description="Download and play all your favourite games or emulate some old but gold ones!" />
<LinkCard title="Reading" href="/readingpiracyguide" tags="books,manga,comics" description="Whether you're a bookworm, otaku or comic book fan, you'll be able to find your favourite pieces of literature here for free!" />
<LinkCard title="Downloading" href="/downloadpiracyguide" tags="games,movies" description="Learn how to download movies, tv shows, music, comics, manga, games and more." />
<LinkCard title="Torrenting" href="/torrentpiracyguide" tags="torrenting" description="Learn how to torrent movies, tv shows, music, comics, manga, games and more." />
<LinkCard title="Educational" href="/edupiracyguide" tags="educational" description="Learn how to download, torrent and read educational content." />
<LinkCard title="Android / iOS" href="/android-iosguide" tags="android,apple" description="Learn how to download, torrent and read educational content." />
<LinkCard title="Linux / MacOS" href="/linuxguide" tags="linux,macos" description="Learn how to download, torrent and read educational content." />
<LinkCard title="Non English" href="/non-english" tags="Non-English" description="Learn how to download, torrent and read educational content." />
<LinkCard title="Miscellaneous" href="/miscguide" tags="miscellaneous" description="Learn how to download, torrent and read educational content." />
<LinkCard title="Tools" href="/system-tools" tags="system,tools" description="Learn how to download, torrent and read educational content." />

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  var preferredKawaii
  try {
    preferredKawaii = localStorage.getItem('uwu')
  } catch (err) {}
  const urlParams = new URLSearchParams(window.location.search)
  const kawaii = urlParams.get('uwu')
  const setKawaii = () => {
    const images = document.querySelectorAll('.VPImage.image-src')
    images.forEach((img) => {
      img.src = '/logo-uwu.svg'
    })
  }
  const resetKawaii = () => {
    const images = document.querySelectorAll('.VPImage.image-src')
    images.forEach((img) => {
      img.src = '/test.png'
    })
  }
  if (kawaii === 'true') {
    try {
      localStorage.setItem('uwu', true)
    } catch (err) {}
    console.log('uwu mode enabled. Disable with "?uwu=false".');
    setKawaii()
  } else if (kawaii === 'false') {
    try {
      localStorage.removeItem('uwu', false)
    } catch (err) {}
    resetKawaii()
  } else if (preferredKawaii) {
    setKawaii()
  }

  let clickCount = 0;
  const heroImage = document.querySelector('.VPImage.image-src');
  
  const handleClick = () => {
    clickCount += 1;
    if (clickCount === 5) {
      const isKawaii = localStorage.getItem('uwu') === 'true';
      if (isKawaii) {
        localStorage.removeItem('uwu');
        resetKawaii();
        console.log('uwu mode disabled.');
      } else {
        localStorage.setItem('uwu', true);
        setKawaii();
        console.log('uwu mode enabled after 5 clicks.');
      }
      clickCount = 0;
    }
  };

  if (heroImage) {
    heroImage.addEventListener('click', handleClick);
  }
})
</script>
