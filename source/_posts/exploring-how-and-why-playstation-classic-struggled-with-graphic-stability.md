---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2025-02-18T08:33:38.665Z
updated: 2025-02-19T17:27:33.702Z
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
<iframe width="560" height="315" src="https://www.youtube.com/embed/RBN1gYY5hUs?si=p89CMiMzeJzU0wGu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

### Highlights

* PlayStation 1 lacked FLOPs due to not having an FPU.
* No Z-buffer resulted in small errors & visible polygons.
* Affine texture mapping caused warping; PS1 trade-offs were speed and cost over complexity.

 Call me biased, but the original PlayStation is still my favorite console of all time. While the games might look a little rough now, they're still as good to play as ever. That said, even back then, PS1 graphics had this signature wobble you didn't find in the competition, so what gives?

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/ME5-sAQJVE4?si=ZfcvJSnhQevWtjI0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/-Bov2KfWQ_Y?si=MnVczisgeJ-sGW2r" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/9ECz3oZ8NrQ?si=86vkwkDJo9HQXpzt" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->

##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/jjGL9wFdlbo?si=Vb1JgZqRXNc03UGG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
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
<li><a href="https://youtube-sure.techidaily.com/ed-2024-approved-choosing-the-best-cameras-and-lenses-for-vloggers/"><u>[Updated] 2024 Approved Choosing the Best Cameras & Lenses for Vloggers</u></a></li>
<li><a href="https://article-tips.techidaily.com/updated-2024-approved-pinning-down-content-5-superior-free-video-downloader-tools/"><u>[Updated] 2024 Approved Pinning Down Content 5 Superior Free Video Downloader Tools</u></a></li>
<li><a href="https://facebook-record-videos.techidaily.com/updated-tips-for-youtube-video-shooting/"><u>[Updated] Tips for YouTube Video Shooting</u></a></li>
<li><a href="https://hardware-updates.techidaily.com/easy-guide-to-downloading-and-installing-hp-scanners-for-windows-computers/"><u>Easy Guide to Downloading and Installing HP Scanners for Windows Computers</u></a></li>
<li><a href="https://win11-tips.techidaily.com/essential-skills-for-photo-cropping-and-cleanup/"><u>Essential Skills for Photo Cropping and Cleanup</u></a></li>
<li><a href="https://screen-mirror.techidaily.com/how-to-mirror-infinix-zero-5g-2023-turbo-to-mac-drfone-by-drfone-android/"><u>How to Mirror Infinix Zero 5G 2023 Turbo to Mac? | Dr.fone</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/ix-escort-smart-radar-detector-tested-the-ai-powered-device-adapts-to-your-driving-habits/"><u>IX Escort Smart Radar Detector Tested: The AI-Powered Device Adapts to Your Driving Habits</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/leading-cable-modems-on-the-market-2024-edition/"><u>Leading Cable Modems on the Market - 2024 Edition</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/lightstudiokit-econ-budget-umbrella-style-lights/"><u>LightStudioKit Econ: Budget Umbrella Style Lights</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/making-an-informed-decision-on-windows-11-written-by-an-industry-insider/"><u>Making an Informed Decision on Windows 11' Written by an Industry Insider</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/maximize-savings-on-tech-products-with-amazons-prime-day-specials-2amoonguide-2024-edition/"><u>Maximize Savings on Tech Products with Amazon's Prime Day Specials - 2Amoonguide 2024 Edition</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/navigating-budget-and-quality-the-tp-link-archer-a6-ac1200-router-stellar-speeds-for-smarter-spending/"><u>Navigating Budget & Quality: The TP-Link Archer A6 AC1200 Router - Stellar Speeds for Smarter Spending</u></a></li>
<li><a href="https://win-howtos.techidaily.com/resolving-the-unrecoverable-directx-error-a-step-by-step-guide/"><u>Resolving the Unrecoverable DirectX Error: A Step-by-Step Guide</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/revolutionary-signals-with-ease-a-thorough-review-of-the-clearstream-eclipse-antenna/"><u>Revolutionary Signals with Ease: A Thorough Review of the ClearStream Eclipse Antenna</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/see-your-pet-like-never-before-affordable-hd-cam-by-petcube/"><u>See Your Pet Like Never Before - Affordable HD Cam by Petcube</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/staying-powerful-and-precise-how-aeiusnys-portable-generator-meets-the-demand-of-medical-equipment-requiring-clean-energy-output/"><u>Staying Powerful and Precise: How Aeiusny's Portable Generator Meets the Demand of Medical Equipment Requiring Clean Energy Output</u></a></li>
<li><a href="https://instagram-clips.techidaily.com/step-into-the-future-mastering-instagram-filters-for-enhanced-imagery-for-2024/"><u>Step Into the Future Mastering Instagram Filters for Enhanced Imagery for 2024</u></a></li>
<li><a href="https://win11.techidaily.com/step-by-step-approach-augmenting-virtual-memory-on-windows-11/"><u>Step-by-Step Approach: Augmenting Virtual Memory on Windows 11</u></a></li>
<li><a href="https://sim-unlock.techidaily.com/the-best-android-sim-unlock-code-generators-unlock-your-samsung-galaxy-a14-5g-phone-hassle-free-by-drfone-android/"><u>The Best Android SIM Unlock Code Generators Unlock Your Samsung Galaxy A14 5G Phone Hassle-Free</u></a></li>
</ul></div>

