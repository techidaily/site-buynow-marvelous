---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2025-01-27T22:44:27.584Z
updated: 2025-01-29T18:32:38.470Z
tags:
  - games
  - tv
  - movies
categories:
  - tech
thumbnail: https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/06/a-playstation-1-controller-with-metal-gear-solid-running-on-a-tv-and-a-glitch-effect.jpg
---

## Exploring How and Why PlayStation Classic Struggled with Graphic Stability

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/eMEJvwMM0vk?si=EQF_jo_4u9v5iJ_C" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

### Highlights

* PlayStation 1 lacked FLOPs due to not having an FPU.
* No Z-buffer resulted in small errors & visible polygons.
* Affine texture mapping caused warping; PS1 trade-offs were speed and cost over complexity.

 Call me biased, but the original PlayStation is still my favorite console of all time. While the games might look a little rough now, they're still as good to play as ever. That said, even back then, PS1 graphics had this signature wobble you didn't find in the competition, so what gives?

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/LlVkEwpjKKo?si=hXi-mchMaJvbnIzM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/BR4gsW-J7as?si=9a56UDKZKhREZnwz" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/7JBG_O3Vnh4?si=lUO0fta6YPJ50qjg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/jnITUsxMz5s?si=ohwRVH6eWhVnC6Xf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
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
<li><a href="https://youtube-docs.techidaily.com/024-approved-elevate-your-viewing-game-with-concurrent-channel-watches/"><u>[New] 2024 Approved Elevate Your Viewing Game with Concurrent Channel Watches</u></a></li>
<li><a href="https://screen-recording.techidaily.com/new-master-your-download-installation-and-usage-of-ez-grabber/"><u>[New] Master Your Download Installation and Usage of EZ Grabber</u></a></li>
<li><a href="https://digital-screen-recording.techidaily.com/updated-in-2024-how-to-record-iphoneipads-screen-2023-latest-method/"><u>[Updated] In 2024, How to Record iPhone/iPad’s Screen [2023 Latest Method]</u></a></li>
<li><a href="https://youtube-help.techidaily.com/2024-approved-transforming-life-experiences-into-engaging-yt-videos/"><u>2024 Approved Transforming Life Experiences Into Engaging YT Videos</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/endless-kid-friendly-entertainment/"><u>Endless Kid-Friendly Entertainment</u></a></li>
<li><a href="https://some-techniques.techidaily.com/flawless-photo-management-on-iphone-size-adjustment-basics-for-2024/"><u>Flawless Photo Management on iPhone Size Adjustment Basics for 2024</u></a></li>
<li><a href="https://location-social.techidaily.com/in-2024-how-to-sharefake-location-on-whatsapp-for-apple-iphone-14-drfone-by-drfone-virtual-ios/"><u>In 2024, How to Share/Fake Location on WhatsApp for Apple iPhone 14 | Dr.fone</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/in-depth-testing-of-the-jackery-powerbar-with-built-in-wall-plug/"><u>In-Depth Testing of the Jackery PowerBar with Built-In Wall Plug</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/justification-why-choosing-an-ipad-makes-sense-financially/"><u>Justification: Why Choosing an iPad Makes Sense Financially</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/leading-linkedin-course-picks-to-advance-your-expertise/"><u>Leading LinkedIn Course Picks to Advance Your Expertise</u></a></li>
<li><a href="https://facebook.techidaily.com/metaverse-milestones-six-intriguing-facebook-updates/"><u>Metaverse Milestones: Six Intriguing Facebook Updates</u></a></li>
<li><a href="https://tech-renaissance.techidaily.com/solving-issues-with-roku-subtitles-troubleshooting-guide/"><u>Solving Issues with Roku Subtitles - Troubleshooting Guide</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/the-essential-5-points-to-contemplate-pre-purchase-for-the-ideal-health-band/"><u>The Essential 5 Points to Contemplate Pre-Purchase for the Ideal Health Band</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/thorough-review-of-winegards-fl5500a-flatwave-antenna-reliable-quality-meets-steep-pricing/"><u>Thorough Review of Winegard's FL5500A FlatWave Antenna: Reliable Quality Meets Steep Pricing</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/top-wi-fi-signal-boosters-for-superior-coverage/"><u>Top Wi-Fi Signal Boosters for Superior Coverage</u></a></li>
</ul></div>

