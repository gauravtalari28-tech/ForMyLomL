<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>For My LOML 💗</title>

  
  <style>
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%;font-family:Inter,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial;color:#fff;background:#050307;overflow-x:hidden;}
    .scene{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;position:relative;overflow:hidden;text-align:center;padding:4rem 1rem;}
    h1,h2{font-family:'Playfair Display',serif}
    h1{font-size:clamp(2.5rem,6vw,4rem);color:#ffd6e0;text-shadow:0 6px 30px rgba(255,150,180,0.2);margin-bottom:1rem;}
    h2{font-size:2rem;color:#ffd6e0;margin-bottom:1rem}
    p{max-width:800px;margin:auto;line-height:1.6;color:#ffeef4}
    .enter-btn{margin-top:1.4rem;padding:0.9rem 1.8rem;border:none;border-radius:999px;background:linear-gradient(90deg,#ff8dc0,#ffc7dd);color:#fff;font-size:1rem;cursor:pointer;box-shadow:0 0 20px rgba(255,130,180,.4);transition:.3s}
    .enter-btn:hover{transform:scale(1.05)}
    .panel{padding:4rem 2rem;width:100%;max-width:900px;}
    .event{background:rgba(255,255,255,.05);padding:1.2rem 1.5rem;border-radius:12px;margin:1rem 0;text-align:left;backdrop-filter:blur(6px);box-shadow:0 0 25px rgba(0,0,0,0.4);}
    .event h3{color:#ffd6e0;margin-bottom:.4rem;font-size:1.1rem;}
    img{border-radius:14px;max-width:100%;height:auto;box-shadow:0 12px 30px rgba(0,0,0,0.6);margin-bottom:1.5rem;}
    audio{margin-top:1rem}
    footer{padding:1rem;font-size:.9rem;color:#ffd6e0;opacity:.8;text-align:center}
    #tsparticles{position:absolute;inset:0;pointer-events:none;z-index:1}
  </style>
</head>
<body>

<div id="tsparticles"></div>

<!-- HERO -->
<section class="scene hero" id="hero">
  <div>
    <h1>For the one who changed everything 💞</h1>
    <p>A journey made of laughter, warmth, and all the memories that still make my heart race.</p>
    <button class="enter-btn" id="enter">Enter the Experience</button>
  </div>
</section>

<!-- THE MOMENT WE MET -->
<section class="scene panel" id="meet">
  <h2>The Moment We Met</h2>

  <div class="event">
    <h3>That night — (a night I’ll never forget)</h3>
    <p>We laughed until our sides ached. The way you tilted your head when you listened, the warmth of your hugs, and how our eyes locked like the world paused for us — I still feel it every time I think of you.</p>
  </div>

  <h3 style="color:#ffcce0;margin:1rem 0;">Cute You 💗</h3>
  <img src="cute you.jpg" alt="Cute You">

  <div class="event">
    <h3>Cheek Kiss 💋</h3>
    <p>That time when you kissed me on the cheek in the middle of the road — so unexpected, so adorable, and one of my cutest memories of us 💞</p>
  </div>
</section>

<!-- OUR STORY -->
<section class="scene panel" id="story">
  <h2>Our Story</h2>

  <div class="event">
    <h3>First Date 💐</h3>
    <p>That silly date we had turned into one of the sweetest memories of my life. Every laugh, every small moment, it all still plays in my head like a movie.</p>
  </div>

  <div class="event">
    <h3>First Kiss 💋</h3>
    <p>That first kiss we shared at the park was so unexpected and funny — the way we both blushed and laughed after still makes my heart melt.</p>
  </div>

  <div class="event">
    <h3>Midnight Talks 🌙</h3>
    <p>When the world fell silent, our voices stayed. The late-night talks, the soft “goodnights,” and the warmth of your words are still my favorite sound.</p>
  </div>
</section>

<!-- WHY I LOVE YOU -->
<section class="scene panel" id="why">
  <h2>Why I Love You</h2>
  <div class="event">
    <p>Your smile, your voice, your courage, and your beautifully crafted soul — everything about you feels like art. You make even silence sound like music.</p>
  </div>
</section>

<!-- FUTURE -->
<section class="scene panel" id="future">
  <h2>Forever & Always</h2>
  <div class="event">
    <p>Here’s to every moment we’ll share and the quiet nights between them. You are my constant, my calm, and my chaos — all at once.</p>
  </div>
</section>

<!-- CONFESSION / SONG -->
<section class="scene panel" id="confess">
  <h2>I love you — forever.</h2>
  <p>Here’s a song that comes to my mind when you stare at me with those beautiful eyes:</p>
  <audio id="song" controls>
    <source src="maulameremaula.mp3" type="audio/mpeg">
    Your browser doesn’t support the audio tag 😔
  </audio>
</section>

<footer>Made with ♥ from your cutu — forever yours 💋</footer>
<script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.2/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3.12.2/dist/ScrollTrigger.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles@2.9.4/tsparticles.bundle.min.js"></script>
<script>
  // floating hearts background
  tsParticles.load("tsparticles", {
    fullScreen:{enable:false},
    particles:{
      number:{value:25},
      move:{enable:true,speed:1.3,direction:"top",outModes:{default:"out"}},
      shape:{type:"char",character:{value:["❤","💞","💖"],font:"Verdana"}},
      size:{value:{min:8,max:16}},
      color:{value:["#ff9bbf","#ffd6e0","#ffcce8"]},
      opacity:{value:0.8}
    }
  });

  // smooth scroll from hero
  // smooth scroll + start music on first interaction
const song = document.getElementById("song");

document.getElementById("enter").addEventListener("click", () => {
  window.scrollTo({ top: window.innerHeight, behavior: "smooth" });
  // attempt to start playback only after user action
  song.play().catch(() => {
    console.log("Browser blocked autoplay until user interacts again.");
  });
});
  // fade in sections on scroll
  const sections=document.querySelectorAll('.scene.panel');
  sections.forEach(sec=>{
    gsap.from(sec,{
      scrollTrigger:{trigger:sec,start:"top 80%"},
      opacity:0,y:50,duration:1
    });
  });
// test GSAP connection
gsap.to("h1", { duration: 1, y: -20, repeat: 1, yoyo: true, ease: "power1.inOut" });
console.log("✅ GSAP test animation running...");
</script>

</body>
</html>
