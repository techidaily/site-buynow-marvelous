---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2025-02-08T07:33:22.568Z
updated: 2025-02-10T09:44:58.705Z
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
<iframe width="560" height="315" src="https://www.youtube.com/embed/jvwX82j3ci0?si=gAWoovjXgs3m1d7S" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
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
<iframe width="560" height="315" src="https://www.youtube.com/embed/rdNq2Sp031s?si=3FcJa3dQLraUDHKv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/15TKQ-BOENI?si=Ri4B2AuxAdi0Bglz" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/6xGqSETroqA?si=4C1GPgXi-AksR_oO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/Wy0uYNNdMDM?si=5ir7EHlr0CkpcYOT" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
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
<li><a href="https://youtube-help.techidaily.com/new-from-script-to-screen-building-a-youtube-trailer-in-filmora/"><u>[New] From Script to Screen Building a YouTube Trailer in Filmora</u></a></li>
<li><a href="https://vimeo-videos.techidaily.com/updated-in-2024-innovating-content-creation-vimeo-edition/"><u>[Updated] In 2024, Innovating Content Creation Vimeo Edition</u></a></li>
<li><a href="https://instagram-video-recordings.techidaily.com/updated-in-2024-unlocking-viral-potential-in-instagram-videos/"><u>[Updated] In 2024, Unlocking Viral Potential in Instagram Videos</u></a></li>
<li><a href="https://technical-tips.techidaily.com/boost-your-ipads-performance-by-replacing-the-old-battery-heres-how/"><u>Boost Your iPad's Performance by Replacing the Old Battery – Here’s How</u></a></li>
<li><a href="https://fox-direct.techidaily.com/integrating-music-into-unboxing-videos-a-comprehensible-manual/"><u>Integrating Music Into Unboxing Videos A Comprehensible Manual</u></a></li>
<li><a href="https://some-skills.techidaily.com/the-right-platform-for-content-creation-in-2024-podcast-or-video/"><u>The Right Platform for Content Creation, In 2024 Podcast or Video?</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/transform-your-game-and-creativity-corsair-one-pro-rises-as-a-leading-desktop-solution/"><u>Transform Your Game & Creativity - Corsair One Pro Rises as a Leading Desktop Solution</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/ultimate-guide-to-the-apple-airtag-ideal-gps-tracking-for-iphone-enthusiasts/"><u>Ultimate Guide to the Apple AirTag: Ideal GPS Tracking for iPhone Enthusiasts</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/ultimate-wifi-faceoff-can-the-tp-link-archer-ax6000-hold-its-own-against-the-nighthawk-ax12/"><u>Ultimate WiFi Faceoff: Can the TP-Link Archer AX6000 Hold Its Own Against the Nighthawk AX12?</u></a></li>
<li><a href="https://win-howtos.techidaily.com/unblocking-the-elevated-privileges-required-alert-in-windows-os-versions/"><u>Unblocking the 'Elevated Privileges Required' Alert in Windows OS Versions</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/unpacking-the-charm-of-campfire-chronicles-skins-in-minecraft-a-complete-review/"><u>Unpacking the Charm of Campfire Chronicles Skins in Minecraft - A Complete Review</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/unveiling-the-capabilities-a-deep-dive-into-the-linksys-ea9500-high-performance-router-review/"><u>Unveiling the Capabilities: A Deep Dive Into the Linksys EA9500 High-Performance Router Review</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/unveiling-the-enhanced-capabilities-of-the-latest-google-nest-hub-if-only-it-came-with-a-camera/"><u>Unveiling the Enhanced Capabilities of the Latest Google Nest Hub - If Only It Came with a Camera!</u></a></li>
<li><a href="https://video-ai-editor.techidaily.com/updated-get-started-with-fcp-voice-over-expert-advice-for-newbies-for-2024/"><u>Updated Get Started with FCP Voice Over Expert Advice for Newbies for 2024</u></a></li>
</ul></div>

