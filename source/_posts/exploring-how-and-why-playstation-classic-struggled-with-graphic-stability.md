---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2024-09-25T21:32:28.515Z
updated: 2024-10-01T18:35:11.496Z
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
<a href="https://appsumo.8odi.net/c/5597632/2082526/7443" target="_top" id="2082526">
  <img src="//a.impactradius-go.com/display-ad/7443-2082526" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2082526/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/2047346/19272" target="_top" id="2047346">
  <img src="//a.impactradius-go.com/display-ad/19272-2047346" border="0" alt="https://techidaily.com" width="300" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/2047346/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/1885928/19272" target="_top" id="1885928">
  <img src="//a.impactradius-go.com/display-ad/19272-1885928" border="0" alt="https://techidaily.com" width="300" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1885928/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/2016134/19272" target="_top" id="2016134">
  <img src="//a.impactradius-go.com/display-ad/19272-2016134" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/2016134/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

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
<li><a href="https://article-tips.techidaily.com/new-the-photopea-blueprint-for-flawless-image-backdrop/"><u>[New] The Photopea Blueprint for Flawless Image Backdrop</u></a></li>
<li><a href="https://vimeo-videos.techidaily.com/updated-claim-the-crown-strategies-for-staff-picked-videos-at-vimeo-for-2024/"><u>[Updated] Claim the Crown Strategies for Staff-Picked Videos at Vimeo for 2024</u></a></li>
<li><a href="https://screen-video-capture.techidaily.com/updated-replay-retro-thrills-top-5-ps1-game-emulators-reviewed-for-pc/"><u>[Updated] Replay Retro Thrills - Top 5 PS1 Game Emulators Reviewed for PC</u></a></li>
<li><a href="https://facebook-video-content.techidaily.com/2024-approved-the-pathway-to-earning-facebook-written-by-your-assistant/"><u>2024 Approved The Pathway to Earning Facebook’ Written by Your Assistant</u></a></li>
<li><a href="https://win-howtos.techidaily.com/conquer-update-errors-on-your-windows-11-system-a-comprehensive-fix-for-the-notorious-error-0x8020390541-issue/"><u>Conquer Update Errors on Your Windows 11 System: A Comprehensive Fix for the Notorious Error 0X80^20390541 Issue</u></a></li>
<li><a href="https://extra-tips.techidaily.com/elite-photography-narrative-assembler-kit/"><u>Elite Photography Narrative Assembler Kit</u></a></li>
<li><a href="https://some-techniques.techidaily.com/hide-your-identity-share-your-life-instagram-live-secrets-for-2024/"><u>Hide Your Identity, Share Your Life - Instagram Live Secrets for 2024</u></a></li>
<li><a href="https://android-pokemon-go.techidaily.com/in-2024-here-are-some-reliable-ways-to-get-pokemon-go-friend-codes-for-infinix-hot-30i-drfone-by-drfone-virtual-android/"><u>In 2024, Here Are Some Reliable Ways to Get Pokemon Go Friend Codes For Infinix Hot 30i | Dr.fone</u></a></li>
<li><a href="https://screen-recording.techidaily.com/in-2024-the-ultimate-approach-to-preserving-your-ps4-experience/"><u>In 2024, The Ultimate Approach to Preserving Your PS4 Experience</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/performance-assessment-of-the-hp-15-inch-notebook-featuring-an-amd-chip-is-it-practical/"><u>Performance Assessment of the HP 15 Inch Notebook Featuring an AMD Chip - Is It Practical?</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/performance-insights-on-pioneers-bdr-xd05b-addressing-its-design-flaws-and-capabilities/"><u>Performance Insights on Pioneer's BDR-XD05B: Addressing Its Design Flaws and Capabilities</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/premium-features-face-off-ipad-air-4-versus-galaxy-tab-s7plus-unveiled/"><u>Premium Features Face Off: IPad Air 4 Versus Galaxy Tab S7+ Unveiled</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/pushing-limits-review-of-jabra-steel-tier-buds/"><u>Pushing Limits: Review of Jabra Steel-Tier Buds</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/reviewing-the-motorola-one-hyper-standout-features-in-a-competitive-mid-range-phone-market/"><u>Reviewing the Motorola One Hyper - Standout Features in a Competitive Mid-Range Phone Market</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/revolutionizing-vinyl-playback-with-audio-techs-turntable-at-lp120xusb/"><u>Revolutionizing Vinyl Playback with Audio-Tech's Turntable, AT-LP120XUSB</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/syma-x8-series-flyer-test-flight-budget-friendly-indoor-drone-experience/"><u>Syma X8 Series Flyer Test Flight: Budget-Friendly Indoor Drone Experience</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/the-acer-chromebook-15-exposed-balancing-size-and-efficiency-for-a-top-browser-experience/"><u>The Acer Chromebook 15 Exposed - Balancing Size and Efficiency for a Top Browser Experience</u></a></li>
</ul></div>

