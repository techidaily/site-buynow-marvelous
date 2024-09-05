---
title: Exploring How and Why PlayStation Classic Struggled with Graphic Stability
date: 2024-09-04T20:11:25.425Z
updated: 2024-09-05T20:11:25.425Z
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

##  It’s All About Floating Points

 Modern GPU performance is often measured ([controversially](https://hardware-help.techidaily.com/brother-hl-2280dw-driver-package-universal-download-for-windows-11-windows-10-windows-8-and-7-users/)) in FLOPs or FLoating Point Operations. This is simply math involving floating point numbers, which in turn are simply whole numbers with a decimal point. The PlayStation's graphics processor had zero FLOPs, because it lacked an FPU or Floating Point Unit. Instead, it uses fixed-point integers to calculate the positions of vertices.

 A "vertice" is a point where two or more lines meet. So in a polygon, which is typically (but not always) a triangle in 3D graphics, there are three vertices. A 3D model consists of multiple polygons, and as that object moves on screen, the positions of the vertices must be calculated in 3D space.

 Since you can only use integers, any position for a vertice that's not an integer will simply be skipped over. So you'll see polygons "snap" between positions with certain types of motion. For example, a character that's standing still and has a subtle idle animation will look like they're jittering a little.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/1868575/19272" target="_top" id="1868575">
  <img src="//a.impactradius-go.com/display-ad/19272-1868575" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1868575/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->
##  Z-Buffer Not Found

 Apart from the lack of an FPU, the PlayStation also lacked a hardware Z-buffer. You might remember XYZ coordinates from school, where you can describe any point within a 3D space using three numbers. The PlayStation lacked a hardware buffer to store depth or Z-axis values, sorted in order of how far away something is from the "camera."

 This meant that game developers had to create their own in-house Z-buffering solution, and since it was not done in hardware, they had to be economical with their depth-sorting algorithms. This led to a common situation in PS1 games where small sorting errors were made and polygons that should have been hidden from view pop in and out of sight.

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2037346/7443" target="_top" id="2037346">
  <img src="//a.impactradius-go.com/display-ad/7443-2037346" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2037346/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->
##  Affine Texture Mapping Is Not So Fine After All

 Texture mapping is the process of adding textures (which are basically digital pictures) to a polygon wireframe. It's basically the "skin" of a 3D object. The PS1 uses a method known as "affine" texture mapping, which uses simple math to determine the coordinates on the polygon where the texture should be drawn. Affine texture mapping does not take Z-coordinates into account, and so perspective projection will appear incorrect for 3D objects. Remember the PS1 has no Z-buffer!

 Consoles like the Nintendo 64 do have a Z-buffer, and also use a method known as mipmapping, where multiple versions of a texture are swapped out depending on your distance from the object, further improving the clarity and stability of textures in motion. On the PS1, lacking these technologies, it leads to what's known as affine texture warping.

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/1885947/19272" target="_top" id="1885947">
  <img src="//a.impactradius-go.com/display-ad/19272-1885947" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1885947/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->
##  Fast, Cheap, or Complex: Pick Two

 Different developers did find ways to work around these limitations, and so some PS1 games exhibit these issues to varying degrees. However, trying to address these issues in software almost always means eating up processing power that could have gone to something else. Despite these cutbacks, the PS1's hardware was above all fast. It could pump out polygons faster than anything else at the time.

 It also helps that CRT displays mask most of these issues quite well, and that would have been what the console was designed for. Modern flat panel displays have a negative effect on how PS1 games are presented, making the graphics uglier now than they were back then!

 The bottom line is that the console could have had that extra hardware, but it would have driven the cost up significantly, without any clear benefit to Sony or its players at the time. The company went with "fast and cheap," leaving complexity at the door. History has shown this was the right decision.

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2087390/7443" target="_top" id="2087390">
  <img src="//a.impactradius-go.com/display-ad/7443-2087390" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2087390/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->
##  Emulators Can Correct This (But Should You?)

![An iPad running G-Police next a  physical original copy of the game and a PS4 controller](https://static1.howtogeekimages.com/wordpress/wp-content/uploads/2024/05/an-ipad-running-g-police-next-a-physical-original-copy-of-the-game-and-a-ps4-controller.jpeg) 

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2030373/7443" target="_top" id="2030373">
  <img src="//a.impactradius-go.com/display-ad/7443-2030373" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2030373/7443" style="position:absolute;visibility:hidden;" border="0" />
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
<li><a href="https://youtube-zero.techidaily.com/iscover-the-secrets-to-youtubes-rankings-with-keywords/"><u>[New] Discover the Secrets to YouTube's Rankings with Keywords</u></a></li>
<li><a href="https://screen-capture.techidaily.com/updated-peer-reviewed-best-action-replay-tech/"><u>[Updated] Peer-Reviewed Best Action Replay Tech</u></a></li>
<li><a href="https://some-guidance.techidaily.com/updated-unlocking-full-access-to-itunes-radio-features/"><u>[Updated] Unlocking Full Access to iTunes Radio Features</u></a></li>
<li><a href="https://extra-skills.techidaily.com/2024-approved-pajama-plots-reviewed-analyzing-childrens-video-stories/"><u>2024 Approved  Pajama Plots Reviewed  Analyzing Children's Video Stories</u></a></li>
<li><a href="https://facebook-clips.techidaily.com/access-the-latest-social-interactions-watch-facebook-live-on-roku/"><u>Access the Latest Social Interactions  Watch Facebook Live on Roku</u></a></li>
<li><a href="https://extra-lessons.techidaily.com/are-feedbacks-on-items-monetized-in-videos/"><u>Are Feedbacks on Items Monetized in Videos?</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/balancing-the-flaws-and-wonders-of-cyberpunk-2n77-review/"><u>Balancing the Flaws and Wonders of Cyberpunk 2N77 Review</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/caixuns-big-screen-marvel-in-depth-analysis-of-the-budget-friendly-75-inch-4k-smart-tv-experience/"><u>Caixun's Big Screen Marvel: In-Depth Analysis of the Budget-Friendly 75-Inch 4K Smart TV Experience</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/canon-vixia-hf-r800-camcorder-review-modest-price-average-video/"><u>Canon VIXIA HF R800 Camcorder Review: Modest Price, Average Video</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/comprehensive-analysis-google-maps-app-on-ios-devices/"><u>Comprehensive Analysis: Google Maps App on iOS Devices</u></a></li>
<li><a href="https://buynow-help.techidaily.com/comprehensive-kobo-nia-ebook-display-assessment-daring-to-rival-amazon-kindle/"><u>Comprehensive Kobo Nia Ebook Display Assessment: Daring to Rival Amazon Kindle?</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/comprehensive-uniden-r3-radar-detector-analysis-durable-and-extended-detection-capability/"><u>Comprehensive Uniden R3 Radar Detector Analysis – Durable & Extended Detection Capability</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/diving-into-fortnites-latest-adventure-comprehensive-insights-for-a-brand-new-season/"><u>Diving Into Fortnite's Latest Adventure: Comprehensive Insights for a Brand-New Season</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/elite-rankings-for-personal-weather-gadgets-whats-hot-in-2-groghty-2024/"><u>Elite Rankings for Personal Weather Gadgets - What's Hot in 2 Groghty, 2024!</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/experience-the-virtual-universe-in-depth-analysis-of-the-vive-cosmos-top-contender-in-a-crowded-market/"><u>Experience the Virtual Universe: In-Depth Analysis of the Vive Cosmos - Top Contender in a Crowded Market</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/head-to-head-showdown-iphone-15-pro-against-pro-max-unveiled/"><u>Head-to-Head Showdown: IPhone 15 Pro Against Pro Max Unveiled</u></a></li>
<li><a href="https://blog-min.techidaily.com/how-to-rescue-lost-pictures-from-xiaomi-14-pro-by-fonelab-android-recover-pictures/"><u>How to Rescue Lost Pictures from Xiaomi 14 Pro?</u></a></li>
<li><a href="https://tech-recovery.techidaily.com/how-to-securely-store-and-protect-your-digital-assets-in-5-ways/"><u>How to Securely Store and Protect Your Digital Assets in 5 Ways</u></a></li>
<li><a href="https://tech-savvy.techidaily.com/how-to-stop-your-xbox-one-from-self-starting-simple-solutions-explored/"><u>How to Stop Your Xbox One From Self-Starting – Simple Solutions Explored</u></a></li>
<li><a href="https://extra-resources.techidaily.com/in-2024-camera-confusion-no-video-display-issue/"><u>In 2024, Camera Confusion  No Video Display Issue</u></a></li>
<li><a href="https://screen-mirroring-recording.techidaily.com/in-2024-insearchofimprovedcameratech-beyond-mycam/"><u>In 2024, InSearchOfImprovedCameraTech Beyond MyCam</u></a></li>
<li><a href="https://screen-recording.techidaily.com/in-2024-top-10-epic-adventures-ultimate-gameplay-showdowns/"><u>In 2024, Top 10 Epic Adventures  Ultimate Gameplay Showdowns</u></a></li>
<li><a href="https://youtube-web.techidaily.com/24-unlock-vfx-magic-top-4-youtube-tutorials-for-no-cost-green-screen-techniques/"><u>In 2024, Unlock VFX Magic  Top 4 YouTube Tutorials for No-Cost Green Screen Techniques</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/lg-k92-5g-evaluation-assessing-the-value-beyond-just-5g-capabilities/"><u>LG K92 5G Evaluation: Assessing the Value Beyond Just 5G Capabilities</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/oculus-quest-2-evaluation-seamless-superior-vr-fun-without-breaking-your-budget/"><u>Oculus Quest 2 Evaluation: Seamless, Superior VR Fun without Breaking Your Budget</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/performance-vs-practicality-in-the-lenovo-ideapad-130s-review-power-boundaries-and-usability-breakthroughs/"><u>Performance Vs. Practicality in the Lenovo IdeaPad 130S Review: Power Boundaries and Usability Breakthroughs</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/premier-pro-basketball-gaming-in-nba-2k19/"><u>Premier Pro-Basketball Gaming in NBA 2K19</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/spectacular-bargain-tech-the-arcshell-ar-5-tested-superb-functionality-unbeatable-cost/"><u>Spectacular Bargain Tech: The Arcshell AR- 5 Tested - Superb Functionality, Unbeatable Cost</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/the-improved-experience-with-apple-watch-series-4-our-comprehensive-review/"><u>The Improved Experience with Apple Watch Series 4 – Our Comprehensive Review</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/the-perfect-travel-companion-unraveling-the-benefits-and-features-of-the-audew-portable-compressor/"><u>The Perfect Travel Companion: Unraveling the Benefits and Features of the Audew Portable Compressor</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/the-ultimate-solution-to-overheating-exploring-the-efficiency-of-the-havit-5-laptop-chiller-innovative-gaming-accessory-reviewed/"><u>The Ultimate Solution to Overheating: Exploring the Efficiency of the HAVIT 5 Laptop Chiller - Innovative Gaming Accessory Reviewed!</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/unboxing-and-testing-the-oculus-quest-2-top-tier-virtual-reality-for-a-steal-of-a-deal/"><u>Unboxing & Testing the Oculus Quest 2 - Top-Tier Virtual Reality for a Steal of a Deal!</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/unlocking-creativity-with-anthropics-smart-photo-editor-a-detailed-review-for-photographers/"><u>Unlocking Creativity with Anthropics Smart Photo Editor: A Detailed Review for Photographers</u></a></li>
<li><a href="https://buynow-marvelous.techidaily.com/withings-move-critique-how-an-old-school-style-meets-new-age-technology/"><u>Withings Move Critique: How an Old-School Style Meets New Age Technology</u></a></li>
</ul></div>
