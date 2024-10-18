---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2024-10-14T19:02:09.194Z
updated: 2024-10-18T18:28:46.167Z
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
<a href="https://aligracehair.sjv.io/c/5597632/1896532/19272" target="_top" id="1896532">
  <img src="//a.impactradius-go.com/display-ad/19272-1896532" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1896532/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/1918719/19272" target="_top" id="1918719">
  <img src="//a.impactradius-go.com/display-ad/19272-1918719" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1918719/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/2012434/19272" target="_top" id="2012434">
  <img src="//a.impactradius-go.com/display-ad/19272-2012434" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/2012434/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

<!-- affiliate ads begin -->
<a href="https://unicoeye.pxf.io/c/5597632/2134244/18498" target="_top" id="2134244">
  <img src="//a.impactradius-go.com/display-ad/18498-2134244" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://unicoeye.pxf.io/i/5597632/2134244/18498" style="position:absolute;visibility:hidden;" border="0" />
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
<li><a href="https://extra-support.techidaily.com/new-master-list-the-finest-no-money-video-player-tools-and-software-pcmobile/"><u>[New] Master List The Finest No-Money Video Player Tools & Software (PC/Mobile)</u></a></li>
<li><a href="https://facebook-video-footage.techidaily.com/updated-slash-the-size-efficient-techniques-for-reducing-youtube-video-lengths/"><u>[Updated] Slash the Size Efficient Techniques for Reducing YouTube Video Lengths</u></a></li>
<li><a href="https://techtrends.techidaily.com/amazon-flash-sale-alert-snag-the-ultra-cheap-iphone-15-pro-max-just-a-penny-learn-more-inside/"><u>Amazon Flash Sale Alert: Snag the Ultra-Cheap iPhone 15 Pro Max - Just a Penny! Learn More Inside</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/amazon-kindle-vs-amazon-fire-tablet-comparing-two-giants/"><u>Amazon Kindle Vs. Amazon Fire Tablet: Comparing Two Giants</u></a></li>
<li><a href="https://fox-links.techidaily.com/crafting-a-professional-rss-feed-for-your-podcast-for-2024/"><u>Crafting a Professional RSS Feed for Your Podcast for 2024</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/discover-bargains-near-you-with-oodles-complimentary-neighborhood-advertisements/"><u>Discover Bargains Near You with Oodle's Complimentary Neighborhood Advertisements</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/expert-insights-on-the-garmin-forerunner-265-smartwatch-a-full-review/"><u>Expert Insights on the Garmin Forerunner 265 Smartwatch – A Full Review</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/expert-insights-discover-every-feature-on-the-samsung-gear-s3-frontier-smartwatch-a-full-review/"><u>Expert Insights: Discover Every Feature on the Samsung Gear S3 Frontier Smartwatch – A Full Review</u></a></li>
<li><a href="https://unlock-android.techidaily.com/how-to-bypass-android-lock-screen-using-emergency-call-on-infinix-by-drfone-android/"><u>How to Bypass Android Lock Screen Using Emergency Call On Infinix?</u></a></li>
<li><a href="https://win-able.techidaily.com/successfully-retrieving-kodi-directory-information-solutions-for-connection-problems/"><u>Successfully Retrieving Kodi Directory Information: Solutions for Connection Problems</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/tp-link-archer-ax6000-vs-nighthawk-ax12-comparative-review-which-is-the-winner/"><u>TP-Link Archer AX6000 Vs. Nighthawk AX12: Comparative Review - Which Is the Winner?</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/ultimate-gamers-choice-the-elite-consoles-of-2024-unveiled/"><u>Ultimate Gamers' Choice: The Elite Consoles of 2024 Unveiled</u></a></li>
<li><a href="https://app-tips.techidaily.com/zdnets-expert-picks-leading-crm-solutions-of-2022-tailored-for-smb-efficiency-and-growth/"><u>ZDNet's Expert Picks: Leading CRM Solutions of 2022 Tailored for SMB Efficiency and Growth</u></a></li>
<li><a href="https://some-approaches.techidaily.com/1724313632985-abbyy/"><u>コダック・アラリスがABBYYと世界的にパートナーシップを強化</u></a></li>
</ul></div>

