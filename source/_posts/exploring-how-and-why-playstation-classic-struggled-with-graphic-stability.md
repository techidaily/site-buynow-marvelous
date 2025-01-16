---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2025-01-13T06:42:35.627Z
updated: 2025-01-16T03:40:15.144Z
tags:
  - games
  - tv
  - movies
categories:
  - tech
thumbnail: https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/06/a-playstation-1-controller-with-metal-gear-solid-running-on-a-tv-and-a-glitch-effect.jpg
---

## Exploring How and Why PlayStation Classic Struggled with Graphic Stability

### Highlights

* PlayStation 1 lacked FLOPs due to not having an FPU.
* No Z-buffer resulted in small errors & visible polygons.
* Affine texture mapping caused warping; PS1 trade-offs were speed and cost over complexity.

 Call me biased, but the original PlayStation is still my favorite console of all time. While the games might look a little rough now, they're still as good to play as ever. That said, even back then, PS1 graphics had this signature wobble you didn't find in the competition, so what gives?

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/E3yY7lZ-FKA?si=g8VEuExP8GH59B69" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/PD0vq5qAYkw?si=5H3KWtCfUOYg1Nlv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/15TKQ-BOENI?si=Ri4B2AuxAdi0Bglz" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/nWu29cqFjZA?si=TNZyCbPq68PQ0JIb" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/6nvb0775GOM?si=peBB_Mo_4zcZFuci" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

Sydney Louw Butler / How-To Geek

 If you play PS1 games using one of [many possible emulators](https://some-techniques.techidaily.com/new-immersion-in-hue-and-light-dreamcolors-z32-x-explored/) today, you usually have the option to "fix" most of these problems. We can magically inject floating point values into the game, and clean up texture mapping so the games shine. However, should you do that? There's an argument to be made that these characteristics are part and parcel of the PS1 experience, and just as people don't want to smooth the pixels in their 8- or 16-bit games, I rarely want to remove the wobble from my favorite PS1 titles.

---

 For an excellent explanation from a real game developer and emulation programmer, I highly recommend Modern Vintage Gamer's deep dive into [PS1 graphical warping](https://youtu.be/x8TO-nrUtSI?si=6SUk7e0hBQSiOnoj).

<ins class="adsbygoogle"
     style="display:block"
     data-ad-format="autorelaxed"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="1223367746"></ins>

<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="8358498916"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>

<span class="atpl-alsoreadstyle">Also read:</span>
<div><ul>
<li><a href="https://tiktok-video-recordings.techidaily.com/new-2024-approved-how-to-make-a-best-tiktok-intro-video-on-mac/"><u>[New] 2024 Approved How to Make a Best Tiktok Intro Video on Mac?</u></a></li>
<li><a href="https://article-helps.techidaily.com/updated-cutting-out-distractions-in-photos/"><u>[Updated] Cutting Out Distractions in Photos</u></a></li>
<li><a href="https://instagram-clips.techidaily.com/updated-in-2024-unveiling-secrets-for-converting-instagram-vids-into-high-quality-mp4/"><u>[Updated] In 2024, Unveiling Secrets for Converting Instagram Vids Into High-Quality MP4</u></a></li>
<li><a href="https://ios-unlock.techidaily.com/a-comprehensive-guide-to-iphone-13-pro-blacklist-removal-tips-and-tools-by-drfone-ios/"><u>A Comprehensive Guide to iPhone 13 Pro Blacklist Removal Tips and Tools</u></a></li>
<li><a href="https://tech-savvy.techidaily.com/amd-zen-amo-upgraded-ayaneo-am01-the-new-minimalist-macintosh-inspired-pc/"><u>AMD Zen Amo Upgraded Ayaneo AM01: The New Minimalist Macintosh-Inspired PC</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/discover-the-gold-standard-for-phablet-devices-with-our-expert-review-on-the-samsung-galaxy-note-9/"><u>Discover the Gold Standard for Phablet Devices with Our Expert Review on the Samsung Galaxy Note 9</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/discover-the-most-advanced-wireless-mesh-networks-of-2024/"><u>Discover the Most Advanced Wireless Mesh Networks of 2024</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/discover-why-the-maisto-rock-crawler-is-a-must-have-toy-in-every-familys-garage/"><u>Discover Why the Maisto Rock Crawler Is a Must-Have Toy in Every Family's Garage</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/eclipse-antenna-by-clearstream-unmatched-performance-in-an-effortlessly-user-friendly-design/"><u>Eclipse Antenna by ClearStream: Unmatched Performance in an Effortlessly User-Friendly Design</u></a></li>
<li><a href="https://techtrends.techidaily.com/enhance-privacy-with-a-vpn-for-apple-vision-pro-step-by-step-installation-and-benefits-techworld-daily/"><u>Enhance Privacy with a VPN for Apple Vision Pro: Step-by-Step Installation and Benefits | TechWorld Daily</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/experience-sunrise-at-home-a-comprehensive-guide-to-totobays-latest-and-budget-friendly-alarm-clock/"><u>Experience Sunrise at Home: A Comprehensive Guide to Totobay's Latest and Budget-Friendly Alarm Clock</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/experience-the-best-in-audio-creatives-sound-blaster-zxr-tested-and-analyzed-2013-model/"><u>Experience the Best in Audio - Creative's Sound Blaster ZxR Tested & Analyzed (2013 Model)</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/experience-the-moto-g-stylus-outstanding-performance-meets-enduring-power-and-smart-pen-capabilities/"><u>Experience the Moto G Stylus: Outstanding Performance Meets Enduring Power and Smart Pen Capabilities</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/expert-reviews-the-most-effective-storm-chasing-tools-for-navigating-2024/"><u>Expert Reviews: The Most Effective Storm Chasing Tools for Navigating 2024</u></a></li>
<li><a href="https://activate-lock.techidaily.com/in-2024-how-to-bypass-icloud-by-checkra1n-even-on-iphone-se-if-youve-tried-everything-by-drfone-ios/"><u>In 2024, How To Bypass iCloud By Checkra1n Even On iPhone SE If Youve Tried Everything</u></a></li>
<li><a href="https://windows11.techidaily.com/reinstating-microsoft-store-apps-windows-11s-guide-to-fixes/"><u>Reinstating Microsoft Store Apps: Windows 11'S Guide to Fixes</u></a></li>
<li><a href="https://techno-recovery.techidaily.com/score-the-latest-on-apple-watch-deals-and-special-pricing/"><u>Score the Latest on Apple Watch Deals and Special Pricing</u></a></li>
</ul></div>

