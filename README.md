<div align="center">

<!-- Animated Header -->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #0c0c1d 0%, #1a0b33 25%, #0d1b2a 50%, #16213e 75%, #0f3460 100%);
  color: #ffffff;
  overflow-x: hidden;
  position: relative;
  min-height: 100vh;
}

body::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 10% 20%, rgba(102, 126, 234, 0.4) 0%, transparent 50%),
    radial-gradient(circle at 90% 80%, rgba(240, 147, 251, 0.4) 0%, transparent 50%),
    radial-gradient(circle at 50% 50%, rgba(245, 87, 108, 0.3) 0%, transparent 70%);
  animation: cosmicShift 20s ease-in-out infinite;
  z-index: -1;
}

@keyframes cosmicShift {
  0%, 100% { transform: translate(0, 0) scale(1); opacity: 0.8; }
  33% { transform: translate(-20px, 20px) scale(1.1); opacity: 1; }
  66% { transform: translate(20px, -20px) scale(0.9); opacity: 0.9; }
}

.particles-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: -1;
}

.particle {
  position: absolute;
  width: 3px;
  height: 3px;
  background: rgba(255, 255, 255, 0.6);
  border-radius: 50%;
  animation: particleFloat 30s infinite ease-in-out;
}

@keyframes particleFloat {
  0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
  10% { opacity: 1; }
  90% { opacity: 1; }
  100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
}

.container {
  max-width: 1600px;
  margin: 0 auto;
  padding: 20px;
  perspective: 1200px;
  position: relative;
}

.bg-effect {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.1), rgba(240, 147, 251, 0.1), rgba(245, 87, 108, 0.1));
  background-size: 400% 400%;
  animation: gradientBG 20s ease infinite;
  z-index: -2;
  filter: blur(60px);
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

header {
  text-align: center;
  padding: 80px 40px;
  margin-bottom: 80px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.08), rgba(255, 255, 255, 0.03));
  backdrop-filter: blur(20px);
  border-radius: 40px;
  border: 2px solid rgba(255, 255, 255, 0.15);
  box-shadow: 
    0 30px 80px rgba(0, 0, 0, 0.6),
    0 0 60px rgba(102, 126, 234, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.3);
  transform: rotateX(8deg) translateZ(30px);
  transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
}

header::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
  animation: headerSweep 4s ease-in-out infinite;
}

@keyframes headerSweep {
  0% { left: -100%; }
  50% { left: 100%; }
  100% { left: 100%; }
}

header:hover {
  transform: rotateX(8deg) translateZ(50px) scale(1.02);
  box-shadow: 
    0 40px 100px rgba(0, 0, 0, 0.8),
    0 0 80px rgba(102, 126, 234, 0.6);
}

.profile-section {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 40px;
  margin-bottom: 40px;
  flex-wrap: wrap;
}

.avatar-container {
  position: relative;
  width: 200px;
  height: 200px;
}

.avatar {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  background: linear-gradient(45deg, #667eea, #764ba2, #f093fb, #f5576c);
  background-size: 400% 400%;
  animation: gradientShift 8s ease infinite, avatarPulse 4s ease-in-out infinite;
  box-shadow: 
    0 0 80px rgba(102, 126, 234, 0.8),
    0 0 120px rgba(240, 147, 251, 0.6),
    inset 0 0 40px rgba(255, 255, 255, 0.3);
  position: relative;
}

.avatar::after {
  content: '';
  position: absolute;
  top: -15px;
  left: -15px;
  right: 15px;
  bottom: 15px;
  border-radius: 50%;
  background: linear-gradient(45deg, #f093fb, #667eea);
  z-index: -1;
  animation: auraExpand 6s ease-in-out infinite;
  filter: blur(20px);
  opacity: 0.7;
}

@keyframes avatarPulse {
  0%, 100% { transform: scale(1) rotate(0deg); }
  50% { transform: scale(1.05) rotate(180deg); }
}

@keyframes auraExpand {
  0%, 100% { transform: scale(1) rotate(0deg); opacity: 0.7; }
  50% { transform: scale(1.3) rotate(180deg); opacity: 1; }
}

.name-section h1 {
  font-size: 5em;
  font-weight: 300;
  margin-bottom: 15px;
  background: linear-gradient(45deg, #fff, #a8edea, #ffd89b);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-shadow: 0 4px 30px rgba(168, 237, 234, 0.6);
  position: relative;
  display: inline-block;
}

.name-section h1::before {
  content: '👋';
  position: absolute;
  left: -60px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 0.8em;
  animation: wave 2s ease-in-out infinite;
}

@keyframes wave {
  0%, 100% { transform: translateY(-50%) rotate(0deg); }
  50% { transform: translateY(-50%) rotate(20deg); }
}

.name-section h3 {
  font-size: 1.8em;
  color: rgba(255, 255, 255, 0.9);
  font-weight: 300;
  margin-top: 20px;
  background: linear-gradient(45deg, #a8edea, #ffd89b);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: titleFloat 4s ease-in-out infinite;
}

@keyframes titleFloat {
  0%, 100% { transform: translateY(0); opacity: 0.8; }
  50% { transform: translateY(-10px); opacity: 1; }
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 25px;
  margin-top: 50px;
  flex-wrap: wrap;
  perspective: 500px;
}

.social-link {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  color: white;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  border: 1px solid rgba(255, 255, 255, 0.2);
  position: relative;
  overflow: hidden;
  transform-style: preserve-3d;
}

.social-link::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
  transition: 0.8s;
}

.social-link::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.5), rgba(240, 147, 251, 0.5));
  border-radius: 50%;
  opacity: 0;
  transition: 0.3s;
  z-index: -1;
}

.social-link:hover::before {
  left: 100%;
}

.social-link:hover::after {
  opacity: 1;
}

.social-link:hover {
  transform: translateY(-15px) rotateY(180deg) scale(1.15) translateZ(20px);
  box-shadow: 
    0 25px 60px rgba(102, 126, 234, 0.7),
    0 0 50px rgba(255, 255, 255, 0.5),
    inset 0 0 30px rgba(255, 255, 255, 0.3);
  border-color: rgba(255, 255, 255, 0.5);
}

.social-link img {
  width: 40px;
  height: 40px;
  filter: drop-shadow(0 0 15px rgba(255, 255, 255, 0.5));
  transition: all 0.5s ease;
}

.social-link:hover img {
  transform: scale(1.2) rotate(360deg);
  filter: drop-shadow(0 0 25px rgba(255, 255, 255, 0.8));
}

section {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.06), rgba(255, 255, 255, 0.02));
  backdrop-filter: blur(20px);
  border-radius: 35px;
  padding: 50px;
  margin-bottom: 60px;
  border: 2px solid rgba(255, 255, 255, 0.15);
  box-shadow: 
    0 20px 60px rgba(0, 0, 0, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.15);
  transform: translateZ(15px);
  transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  opacity: 0;
  animation: sectionFadeIn 1s ease-out forwards;
}

@keyframes sectionFadeIn {
  to {
    opacity: 1;
    transform: translateZ(15px);
  }
}

section:nth-child(1) { animation-delay: 0.1s; }
section:nth-child(2) { animation-delay: 0.3s; }
section:nth-child(3) { animation-delay: 0.5s; }
section:nth-child(4) { animation-delay: 0.7s; }
section:nth-child(5) { animation-delay: 0.9s; }

section::before {
  content: '';
  position: absolute;
  top: 0;
  left: -150%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  transition: 1.5s;
  transform: skewX(-20deg);
}

section:hover::before {
  left: 150%;
}

section:hover {
  transform: translateZ(40px) scale(1.02);
  box-shadow: 
    0 30px 80px rgba(0, 0, 0, 0.6),
    0 0 60px rgba(102, 126, 234, 0.5),
    inset 0 0 20px rgba(255, 255, 255, 0.1);
  border-color: rgba(102, 126, 234, 0.6);
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
}

section h2 {
  font-size: 3em;
  margin-bottom: 40px;
  text-align: center;
  background: linear-gradient(45deg, #667eea, #f093fb, #f5576c);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  position: relative;
  text-shadow: 0 4px 20px rgba(102, 126, 234, 0.4);
}

section h2::before {
  content: '⭐';
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  font-size: 0.5em;
  opacity: 0.3;
  animation: starTwinkle 3s ease-in-out infinite;
}

@keyframes starTwinkle {
  0%, 100% { opacity: 0.3; transform: translate(-50%, -50%) scale(1); }
  50% { opacity: 1; transform: translate(-50%, -50%) scale(1.2) rotate(180deg); }
}

.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 30px;
  margin: 40px 0;
}

.tech-card {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.08), rgba(255, 255, 255, 0.03));
  border-radius: 25px;
  padding: 30px;
  text-align: center;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  border: 1px solid rgba(255, 255, 255, 0.15);
  position: relative;
  transform: translateZ(10px);
  perspective: 500px;
  overflow: hidden;
}

.tech-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.3), rgba(240, 147, 251, 0.3));
  opacity: 0;
  transition: 0.5s;
  z-index: -1;
  border-radius: 25px;
}

.tech-card:hover::before {
  opacity: 1;
  transform: scale(1.05);
}

.tech-card:hover {
  transform: translateZ(30px) translateY(-15px) rotateX(10deg) rotateY(10deg) scale(1.08);
  box-shadow: 
    0 25px 60px rgba(102, 126, 234, 0.6),
    inset 0 0 30px rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.4);
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.05));
}

.tech-card img {
  width: 60px;
  height: 60px;
  margin-bottom: 15px;
  filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.4));
  transition: all 0.5s ease;
}

.tech-card:hover img {
  transform: scale(1.3) rotate(360deg) translateZ(10px);
  filter: drop-shadow(0 0 30px rgba(255, 255, 255, 0.8));
}

.analytics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 40px;
  margin: 40px 0;
}

.analytics-card {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.02));
  border-radius: 30px;
  padding: 40px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.15);
  position: relative;
  overflow: hidden;
  transition: all 0.6s ease;
  opacity: 0;
  animation: cardSlideUp 1s ease-out forwards;
}

@keyframes cardSlideUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.analytics-card:nth-child(1) { animation-delay: 0.1s; }
.analytics-card:nth-child(2) { animation-delay: 0.3s; }

.analytics-card::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #f093fb, #f5576c, #a8edea);
  animation: progressFill 4s ease-in-out infinite;
}

@keyframes progressFill {
  0% { transform: scaleX(0); transform-origin: left; }
  100% { transform: scaleX(1); transform-origin: left; }
}

.analytics-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 50px rgba(102, 126, 234, 0.4);
  border-color: rgba(102, 126, 234, 0.6);
}

.analytics-card img {
  width: 100%;
  max-width: 300px;
  height: auto;
  border-radius: 20px;
  margin: 30px auto;
  box-shadow: 
    0 20px 50px rgba(0, 0, 0, 0.6),
    0 0 40px rgba(102, 126, 234, 0.4);
  transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
}

.analytics-card img::before {
  content: '';
  position: absolute;
  top: -5px;
  left: -5px;
  right: 5px;
  bottom: 5px;
  border-radius: 20px;
  background: linear-gradient(45deg, #f093fb, #667eea);
  z-index: -1;
  opacity: 0.7;
  filter: blur(15px);
  animation: glowPulse 3s ease-in-out infinite;
}

@keyframes glowPulse {
  0%, 100% { opacity: 0.5; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.05); }
}

.analytics-card:hover img {
  transform: translateY(-8px) scale(1.03) rotateX(5deg);
  box-shadow: 
    0 30px 70px rgba(0, 0, 0, 0.8),
    0 0 60px rgba(102, 126, 234, 0.6);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
  gap: 40px;
  margin: 40px 0;
}

.project-card {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.02));
  border-radius: 30px;
  padding: 35px;
  border: 1px solid rgba(255, 255, 255, 0.15);
  position: relative;
  transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  overflow: hidden;
  opacity: 0;
  animation: projectCardFade 1s ease-out forwards;
}

@keyframes projectCardFade {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.project-card:nth-child(1) { animation-delay: 0.1s; }
.project-card:nth-child(2) { animation-delay: 0.2s; }
.project-card:nth-child(3) { animation-delay: 0.3s; }
.project-card:nth-child(4) { animation-delay: 0.4s; }
.project-card:nth-child(5) { animation-delay: 0.5s; }
.project-card:nth-child(6) { animation-delay: 0.6s; }
.project-card:nth-child(7) { animation-delay: 0.7s; }
.project-card:nth-child(8) { animation-delay: 0.8s; }

.project-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #f093fb, #f5576c, #a8edea, #ffd89b);
  animation: borderFlow 3s ease-in-out infinite;
}

@keyframes borderFlow {
  0% { transform: scaleX(0); }
  50% { transform: scaleX(1); }
  100% { transform: scaleX(0); }
}

.project-card:hover {
  transform: translateY(-20px) rotateX(5deg) rotateY(5deg) scale(1.05);
  box-shadow: 
    0 30px 80px rgba(102, 126, 234, 0.6),
    0 0 50px rgba(255, 255, 255, 0.3),
    inset 0 0 30px rgba(255, 255, 255, 0.1);
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
}

.project-card h3 {
  font-size: 1.8em;
  margin-bottom: 15px;
  background: linear-gradient(45deg, #fff, #a8edea);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-shadow: 0 4px 15px rgba(168, 237, 234, 0.4);
}

.project-card p {
  color: rgba(255, 255, 255, 0.85);
  margin-bottom: 15px;
  line-height: 1.7;
}

.project-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin: 20px 0;
}

.stack-tag {
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.4), rgba(240, 147, 251, 0.4));
  padding: 8px 16px;
  border-radius: 25px;
  font-size: 0.9em;
  border: 1px solid rgba(102, 126, 234, 0.6);
  transition: all 0.5s ease;
  position: relative;
  overflow: hidden;
}

.stack-tag::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.5), transparent);
  transition: 0.6s;
}

.stack-tag:hover::before {
  left: 100%;
}

.stack-tag:hover {
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.7), rgba(240, 147, 251, 0.7));
  transform: scale(1.15) translateY(-3px);
  box-shadow: 0 10px 25px rgba(102, 126, 234, 0.5);
  border-color: rgba(255, 255, 255, 0.5);
}

.project-link {
  display: inline-block;
  margin-top: 20px;
  padding: 15px 35px;
  background: linear-gradient(45deg, #667eea, #764ba2, #f093fb);
  color: white;
  text-decoration: none;
  border-radius: 35px;
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  font-weight: 300;
  position: relative;
  overflow: hidden;
  letter-spacing: 1px;
}

.project-link::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
  transition: 0.7s;
}

.project-link:hover::before {
  left: 100%;
}

.project-link:hover {
  transform: translateY(-5px) scale(1.08) rotateX(5deg);
  box-shadow: 
    0 15px 40px rgba(102, 126, 234, 0.7),
    inset 0 0 20px rgba(255, 255, 255, 0.3);
  background: linear-gradient(45deg, #764ba2, #667eea, #f093fb);
}

table {
  width: 100%;
  border-collapse: collapse;
  margin: 40px 0;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.04), rgba(255, 255, 255, 0.01));
  border-radius: 20px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.15);
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
}

table th,
table td {
  padding: 20px;
  text-align: left;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

table th {
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.5), rgba(240, 147, 251, 0.5));
  color: white;
  font-weight: 300;
  position: relative;
  overflow: hidden;
}

table th::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  animation: tableHeaderShine 3s ease-in-out infinite;
}

@keyframes tableHeaderShine {
  0% { left: -100%; }
  50% { left: 100%; }
  100% { left: 100%; }
}

table tr {
  transition: all 0.4s ease;
  position: relative;
}

table tr::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  width: 4px;
  height: 100%;
  background: linear-gradient(45deg, #667eea, #f093fb);
  opacity: 0;
  transition: 0.3s;
}

table tr:hover::before {
  opacity: 1;
}

table tr:hover {
  background: linear-gradient(45deg, rgba(102, 126, 234, 0.2), rgba(240, 147, 251, 0.2));
  transform: translateX(10px) scale(1.02);
  box-shadow: 0 5px 20px rgba(102, 126, 234, 0.3);
}

.connect-section {
  text-align: center;
  padding: 80px;
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.3), rgba(118, 75, 162, 0.3), rgba(240, 147, 251, 0.3), rgba(245, 87, 108, 0.3));
  border-radius: 50px;
  position: relative;
  overflow: hidden;
  margin: 60px 0;
  border: 2px solid rgba(255, 255, 255, 0.2);
}

.connect-section::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.15) 0%, transparent 70%);
  animation: connectRotate 30s linear infinite;
  z-index: -1;
}

@keyframes connectRotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.connect-links {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin: 40px 0;
  flex-wrap: wrap;
}

.connect-link {
  padding: 18px 40px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-radius: 50px;
  text-decoration: none;
  color: white;
  transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  backdrop-filter: blur(10px);
  font-weight: 300;
  letter-spacing: 1px;
}

.connect-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #667eea, #f093fb, #f5576c);
  transform: scaleX(0);
  transition: transform 0.4s ease;
  transform-origin: center;
}

.connect-link:hover::after {
  transform: scaleX(1);
}

.connect-link:hover {
  transform: translateY(-8px) scale(1.1) rotateX(5deg);
  box-shadow: 
    0 20px 50px rgba(102, 126, 234, 0.6),
    inset 0 0 20px rgba(255, 255, 255, 0.2);
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.3), rgba(240, 147, 251, 0.3));
  border-color: rgba(255, 255, 255, 0.5);
}

footer {
  text-align: center;
  padding: 60px;
  margin-top: 80px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.02));
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.15);
  position: relative;
  overflow: hidden;
}

footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, transparent, #667eea, #f093fb, #f5576c, transparent);
  animation: footerGlow 4s ease-in-out infinite;
}

@keyframes footerGlow {
  0%, 100% { opacity: 0.3; transform: scaleX(0.8); }
  50% { opacity: 1; transform: scaleX(1.2); }
}

.scroll-top {
  position: fixed;
  bottom: 40px;
  right: 40px;
  width: 70px;
  height: 70px;
  background: linear-gradient(45deg, #667eea, #764ba2, #f093fb);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-decoration: none;
  font-size: 30px;
  transition: all 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  box-shadow: 0 15px 40px rgba(102, 126, 234, 0.5);
  opacity: 0;
  visibility: hidden;
  transform: translateY(30px) scale(0.8);
  z-index: 1000;
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.scroll-top.active {
  opacity: 1;
  visibility: visible;
  transform: translateY(0) scale(1);
  animation: scrollButtonBounce 2s ease-in-out infinite;
}

@keyframes scrollButtonBounce {
  0%, 100% { transform: translateY(0) scale(1); }
  50% { transform: translateY(-10px) scale(1.1); }
}

.scroll-top:hover {
  transform: translateY(-15px) scale(1.2) rotate(360deg);
  box-shadow: 0 20px 60px rgba(102, 126, 234, 0.8);
  background: linear-gradient(45deg, #f093fb, #667eea, #764ba2);
}

@media (max-width: 768px) {
  .container {
    padding: 10px;
  }

  header {
    padding: 40px 20px;
    transform: rotateX(2deg) translateZ(10px);
  }

  .name-section h1 {
    font-size: 2.5em;
  }

  .profile-section {
    flex-direction: column;
    gap: 20px;
  }

  .avatar-container,
  .avatar {
    width: 150px;
    height: 150px;
  }

  .tech-grid {
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 15px;
  }

  .tech-card {
    padding: 20px;
  }

  .tech-card img {
    width: 40px;
    height: 40px;
  }

  section {
    padding: 30px;
    border-radius: 25px;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .analytics-grid {
    grid-template-columns: 1fr;
  }

  .connect-links {
    flex-direction: column;
    align-items: center;
  }

  .connect-link {
    width: 100%;
    max-width: 250px;
    text-align: center;
  }

  .scroll-top {
    width: 50px;
    height: 50px;
    font-size: 20px;
    bottom: 20px;
    right: 20px;
  }

  .particle {
    display: none;
  }
}
</style>

<div class="bg-effect"></div>
<div class="particles-container" id="particles"></div>

<div class="container">
  <header>
    <div class="profile-section">
      <div class="avatar-container">
        <div class="avatar"></div>
      </div>
      <div class="name-section">
        <h1 class="glitch-text" data-text="Md. Raihan Rimon">Md. Raihan Rimon</h1>
        <h3>Full-Stack Developer</h3>
      </div>
    </div>

    <p align="center">
      <div style="display: flex; justify-content: center; gap: 20px; margin-bottom: 20px;">
        <img src="https://skillicons.dev/icons?i=github" width="50" height="50" alt="GitHub" />
        <img src="https://skillicons.dev/icons?i=linkedin" width="50" height="50" alt="LinkedIn" />
        <img src="https://img.icons8.com/color/48/gmail-new.png" width="50" height="50" alt="Email" />
        <img src="https://skillicons.dev/icons?i=instagram" width="50" height="50" alt="Instagram" />
      </div>
    </p>
  </header>

  <section id="about">
    <h2>About Me</h2>

    I'm a **Full-Stack Developer** passionate about building modern, scalable web applications and real-world solutions.

    I enjoy transforming complex problems into elegant, complete digital solutions — from **UI/UX design and frontend development to backend architecture, databases, authentication, APIs, and deployment**.

    ### 🎯 What I Do

    - 🔭 Currently working on **FindBD**
    - 🌱 Learning **Cybersecurity & Modern Web Security**
    - 💻 Focused on **Next.js, React, Node.js, TypeScript & MongoDB**
    - ⚙️ Experienced with **REST APIs, JWT, Socket.IO, and role-based authentication**
    - 🧠 Interested in **automation, scalable architecture and business applications**
    - 🚀 Building projects from **idea → development → deployment**
  </section>

  <section id="tech-stack">
    <h2>Tech Stack</h2>

    ### Frontend

    <p align="left">
      <div style="display: flex; gap: 15px; flex-wrap: wrap; margin: 20px 0;">
        <img src="https://skillicons.dev/icons?i=nextjs" width="50" height="50" alt="Next.js" title="Next.js" />
        <img src="https://skillicons.dev/icons?i=react" width="50" height="50" alt="React" title="React" />
        <img src="https://skillicons.dev/icons?i=typescript" width="50" height="50" alt="TypeScript" title="TypeScript" />
        <img src="https://skillicons.dev/icons?i=javascript" width="50" height="50" alt="JavaScript" title="JavaScript" />
        <img src="https://skillicons.dev/icons?i=html" width="50" height="50" alt="HTML" title="HTML" />
        <img src="https://skillicons.dev/icons?i=css" width="50" height="50" alt="CSS" title="CSS" />
        <img src="https://skillicons.dev/icons?i=tailwind" width="50" height="50" alt="Tailwind CSS" title="Tailwind CSS" />
        <img src="https://skillicons.dev/icons?i=bootstrap" width="50" height="50" alt="Bootstrap" title="Bootstrap" />
      </div>
    </p>

    ### Backend & Database

    <p align="left">
      <div style="display: flex; gap: 15px; flex-wrap: wrap; margin: 20px 0;">
        <img src="https://skillicons.dev/icons?i=nodejs" width="50" height="50" alt="Node.js" title="Node.js" />
        <img src="https://skillicons.dev/icons?i=express" width="50" height="50" alt="Express" title="Express" />
        <img src="https://skillicons.dev/icons?i=mongodb" width="50" height="50" alt="MongoDB" title="MongoDB" />
        <img src="https://skillicons.dev/icons?i=mysql" width="50" height="50" alt="MySQL" title="MySQL" />
        <img src="https://skillicons.dev/icons?i=postgres" width="50" height="50" alt="PostgreSQL" title="PostgreSQL" />
        <img src="https://skillicons.dev/icons?i=nestjs" width="50" height="50" alt="NestJS" title="NestJS" />
      </div>
    </p>

    ### Programming & Tools

    <p align="left">
      <div style="display: flex; gap: 15px; flex-wrap: wrap; margin: 20px 0;">
        <img src="https://skillicons.dev/icons?i=python" width="50" height="50" alt="Python" title="Python" />
        <img src="https://skillicons.dev/icons?i=java" width="50" height="50" alt="Java" title="Java" />
        <img src="https://skillicons.dev/icons?i=c" width="50" height="50" alt="C" title="C" />
        <img src="https://skillicons.dev/icons?i=cpp" width="50" height="50" alt="C++" title="C++" />
        <img src="https://skillicons.dev/icons?i=git" width="50" height="50" alt="Git" title="Git" />
        <img src="https://skillicons.dev/icons?i=github" width="50" height="50" alt="GitHub" title="GitHub" />
        <img src="https://skillicons.dev/icons?i=docker" width="50" height="50" alt="Docker" title="Docker" />
        <img src="https://skillicons.dev/icons?i=figma" width="50" height="50" alt="Figma" title="Figma" />
        <img src="https://skillicons.dev/icons?i=linux" width="50" height="50" alt="Linux" title="Linux" />
      </div>
    </p>

    ### Other Technologies

    <p align="left">
      <div style="display: flex; gap: 15px; flex-wrap: wrap; margin: 20px 0;">
        <img src="https://skillicons.dev/icons?i=threejs" width="50" height="50" alt="Three.js" title="Three.js" />
        <img src="https://skillicons.dev/icons?i=tensorflow" width="50" height="50" alt="TensorFlow" title="TensorFlow" />
        <img src="https://skillicons.dev/icons?i=opencv" width="50" height="50" alt="OpenCV" title="OpenCV" />
        <img src="https://skillicons.dev/icons?i=php" width="50" height="50" alt="PHP" title="PHP" />
        <img src="https://skillicons.dev/icons?i=dotnet" width="50" height="50" alt=".NET" title=".NET" />
        <img src="https://skillicons.dev/icons?i=cs" width="50" height="50" alt="C#" title="C#" />
        <img src="https://skillicons.dev/icons?i=firebase" width="50" height="50" alt="Firebase" title="Firebase" />
        <img src="https://skillicons.dev/icons?i=postman" width="50" height="50" alt="Postman" title="Postman" />
      </div>
    </p>
  </section>

  <section id="analytics">
    <h2>GitHub Analytics</h2>

    <div class="analytics-grid">
      <div class="analytics-card">
        <h3>GitHub Stats</h3>
        <img src="https://github-readme-stats.vercel.app/api?username=rimon213311004&show_icons=true&theme=tokyonight&hide_border=true&rank_icon=github&include_all_commits=true" alt="GitHub Stats" />
      </div>
      <div class="analytics-card">
        <h3>Top Languages</h3>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rimon213311004&layout=compact&theme=tokyonight&hide_border=true&langs_count=10" alt="Top Languages" />
      </div>
    </div>

    <p align="center">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=rimon213311004&theme=tokyonight&hide_border=true" alt="GitHub Streak" />
    </p>
  </section>

  <section id="achievements">
    <h2>GitHub Achievements</h2>
    <p align="center">
      <img src="https://github-profile-trophy.vercel.app/?username=rimon213311004&theme=tokyonight&no-frame=true&no-bg=true&margin-w=10&row=2&column=4" alt="GitHub Trophies" />
    </p>
  </section>

  <section id="contribution">
    <h2>Contribution Activity</h2>
    <p align="center">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=rimon213311004&theme=tokyo-night&hide_border=true&area=true" width="100%" alt="Activity Graph" />
    </p>
  </section>

  <section id="snake">
    <h2>Contribution Snake</h2>
    <p align="center">
      <img src="https://raw.githubusercontent.com/rimon213311004/rimon213311004/output/github-contribution-grid-snake.svg" alt="Contribution Snake" />
    </p>
  </section>

  <section id="3d-contrib">
    <h2>3D Contribution Graph</h2>
    <p align="center">
      <img src="https://raw.githubusercontent.com/rimon213311004/rimon213311004/main/profile-3d-contrib/profile-night-rainbow.svg" width="100%" alt="3D Contribution Graph" />
    </p>
  </section>

  <section id="projects">
    <h2>Featured Projects</h2>

    <div class="projects-grid">
      <div class="project-card" style="--card-index: 1;">
        <h3>🛡️ SafeCheck</h3>
        <p>Privacy-first personal safety, verification and incident reporting platform.</p>
        <p>- 🔐 Privacy-focused architecture</p>
        <p>- 🧩 Shared validation contracts</p>
        <p>- ✅ Zod validation</p>
        <p>- 👤 Verification & review workflow</p>
        <p>- ⚖️ Appeal system</p>
        <p>- ⚡ Modern Next.js + Express architecture</p>
        <p>- 🗄️ MongoDB + Mongoose</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">React</span>
          <span class="stack-tag">TypeScript</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Zod</span>
        </div>
        <a href="https://github.com/rimon213311004/Safe" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 2;">
        <h3>🔎 FindBD</h3>
        <p>Lost & Found platform with an intelligent matching system.</p>
        <p>- 🔍 Lost & Found matching</p>
        <p>- 📍 Location-based matching</p>
        <p>- 🏷️ Category & brand matching</p>
        <p>- 🎨 Colour matching</p>
        <p>- 📅 Date & time matching</p>
        <p>- 🧠 Weighted 100-point matching algorithm</p>
        <p>- ⚡ Full-stack architecture</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">TypeScript</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
        </div>
        <a href="https://github.com/rimon213311004/Findbd" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 3;">
        <h3>🚌 TicketBus</h3>
        <p>Full-stack bus ticket booking and management platform.</p>
        <p>- 🔎 Route search</p>
        <p>- 🚌 Bus/operator comparison</p>
        <p>- 💺 Exact seat selection</p>
        <p>- 🔒 Seat holding</p>
        <p>- 🚫 Double-booking prevention</p>
        <p>- 💳 Payment verification</p>
        <p>- 🎫 E-ticket generation</p>
        <p>- 📊 Admin control centre</p>
        <p>- 📈 Sales analytics</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
        </div>
        <a href="https://github.com/rimon213311004/TicketBus" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 4;">
        <h3>📚 AssignmentHub</h3>
        <p>Academic assignment management platform for students, teachers and administrators.</p>
        <p>- 👨‍🎓 Student management</p>
        <p>- 👨‍🏫 Teacher management</p>
        <p>- 📝 Assignment creation</p>
        <p>- 📤 Assignment submission</p>
        <p>- 📊 Marks & feedback</p>
        <p>- 🔐 Role-based access</p>
        <p>- 📖 Swagger API documentation</p>
        <p>- 🐳 Docker support</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">React</span>
          <span class="stack-tag">TypeScript</span>
          <span class="stack-tag">ASP.NET Core 8</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Docker</span>
        </div>
        <a href="https://github.com/rimon213311004/Assignment" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 5;">
        <h3>💼 Job Tracking System</h3>
        <p>A full-stack job application tracking platform.</p>
        <p>- 🔐 Secure authentication</p>
        <p>- 📝 Job application management</p>
        <p>- 🔎 Search & filtering</p>
        <p>- 📊 Application analytics</p>
        <p>- 📅 Monthly trends</p>
        <p>- 👀 Employer interest tracking</p>
        <p>- ⚡ Real-time updates</p>
        <p>- 🔄 Job data synchronisation</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Socket.IO</span>
        </div>
        <a href="https://github.com/rimon213311004/Jobtracking" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 6;">
        <h3>🎓 UniHive</h3>
        <p>University-focused social networking platform.</p>
        <p>- 👨‍🎓 Student / Faculty / Alumni roles</p>
        <p>- 👤 User profiles</p>
        <p>- 🤝 Follow system</p>
        <p>- 📝 Posts</p>
        <p>- 👥 Groups</p>
        <p>- 💬 Real-time chat</p>
        <p>- ☁️ Cloudinary media</p>
        <p>- ⚡ Socket.IO</p>
        <div class="project-stack">
          <span class="stack-tag">React</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Socket.IO</span>
        </div>
        <a href="https://github.com/rimon213311004/Unihive-main" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 7;">
        <h3>📦 Rice Shop Management</h3>
        <p>Business inventory, sales and customer due management system.</p>
        <p>- 📦 Inventory management</p>
        <p>- 💰 Sales management</p>
        <p>- 👥 Customer management</p>
        <p>- 💳 Due tracking</p>
        <p>- 📈 Business analytics</p>
        <p>- 📊 Recharts dashboards</p>
        <p>- 📄 PDF reports</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">TypeScript</span>
          <span class="stack-tag">MongoDB</span>
          <span class="stack-tag">Tailwind CSS</span>
          <span class="stack-tag">Recharts</span>
          <span class="stack-tag">jsPDF</span>
        </div>
        <a href="https://github.com/rimon213311004/Shop" class="project-link" target="_blank">View Repository</a>
      </div>

      <div class="project-card" style="--card-index: 8;">
        <h3>🍱 Hostel Meal Management</h3>
        <p>Full-stack hostel meal and monthly settlement management system.</p>
        <p>- 🍚 Meal tracking</p>
        <p>- 💰 Deposit management</p>
        <p>- 🛒 Shopping cost tracking</p>
        <p>- 📊 Monthly settlement</p>
        <p>- 👥 Member management</p>
        <p>- 📈 Financial calculations</p>
        <p>- 🎨 Modern interactive UI</p>
        <div class="project-stack">
          <span class="stack-tag">Next.js</span>
          <span class="stack-tag">React</span>
          <span class="stack-tag">Node.js</span>
          <span class="stack-tag">Express</span>
          <span class="stack-tag">MongoDB</span>
        </div>
        <a href="https://github.com/rimon213311004/Meal" class="project-link" target="_blank">View Repository</a>
      </div>
    </div>
  </section>

  <section id="other-projects">
    <h2>💡 Other Projects</h2>

    <table>
      <thead>
        <tr>
          <th>Project</th>
          <th>Description</th>
          <th>Technology</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>🤖 Automation</td>
          <td>Job discovery & browser automation</td>
          <td>Python • Playwright</td>
        </tr>
        <tr>
          <td>📱 Batch</td>
          <td>Mobile social/community application</td>
          <td>React Native • Expo</td>
        </tr>
        <tr>
          <td>💬 WhatsApp AI</td>
          <td>AI-powered WhatsApp automation</td>
          <td>Node.js • AI</td>
        </tr>
        <tr>
          <td>🌐 RimonTech</td>
          <td>Business/company website</td>
          <td>PHP • MySQL</td>
        </tr>
        <tr>
          <td>🏫 School Management</td>
          <td>School administration system</td>
          <td>PHP • MySQL</td>
        </tr>
        <tr>
          <td>👥 SSC 2K18</td>
          <td>Alumni social platform</td>
          <td>Full Stack</td>
        </tr>
        <tr>
          <td>💊 Medicine Store</td>
          <td>Online medicine e-commerce</td>
          <td>Next.js • MongoDB</td>
        </tr>
      </tbody>
    </table>
  </section>

  <section id="philosophy">
    <h2>📌 Development Philosophy</h2>

    <pre><code>const developer = {
  name: "Md. Raihan Rimon",

  focus: [
    "Full-Stack Development",
    "Real-World Applications",
    "Scalable Architecture",
    "Modern UI/UX",
    "Business Automation"
  ],

  approach: [
    "Understand the problem",
    "Design the solution",
    "Build the product",
    "Test the system",
    "Deploy and improve"
  ],

  goal: "Build software that solves real problems."
};</code></pre>
  </section>

  <section id="connect" class="connect-section">
    <h2>📫 Connect With Me</h2>

    <div class="connect-links">
      <a href="https://www.linkedin.com/in/raihan-rimon-997969289/" target="_blank" class="connect-link">LinkedIn</a>
      <a href="mailto:raihanrimon853@gmail.com" class="connect-link">Email</a>
      <a href="https://instagram.com/raihanrimon.853" target="_blank" class="connect-link">Instagram</a>
      <a href="https://github.com/rimon213311004" target="_blank" class="connect-link">GitHub</a>
    </div>

    <p><strong>📧 Email:</strong> `raihanrimon853@gmail.com`</p>
    <p><strong>💻 GitHub:</strong> <a href="https://github.com/rimon213311004">github.com/rimon213311004</a></p>
  </section>

  <footer>
    <h3>🚀 Building • Learning • Improving • Shipping</h3>
    <p><i>"Turning ideas into real-world software, one project at a time."</i></p>
  </footer>
</div>

<a href="#" class="scroll-top" id="scrollTop">↑</a>

<script>
  function createParticles() {
    const container = document.getElementById('particles');
    const particleCount = window.innerWidth > 768 ? 50 : 25;

    for (let i = 0; i < particleCount; i++) {
      setTimeout(() => {
        const particle = document.createElement('div');
        particle.className = 'particle';
        particle.style.left = Math.random() * 100 + '%';
        particle.style.animationDelay = Math.random() * 30 + 's';
        particle.style.animationDuration = 30 + Math.random() * 30 + 's';
        particle.style.width = Math.random() * 3 + 1 + 'px';
        particle.style.height = particle.style.width;
        container.appendChild(particle);
      }, Math.random() * 5000);
    }
  }

  function setupScrollTop() {
    const scrollTop = document.getElementById('scrollTop');

    window.addEventListener('scroll', () => {
      if (window.pageYOffset > 500) {
        scrollTop.classList.add('active');
      } else {
        scrollTop.classList.remove('active');
      }
    });

    scrollTop.addEventListener('click', (e) => {
      e.preventDefault();
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    });
  }

  function setupTechCards() {
    const techCards = document.querySelectorAll('.tech-card');

    techCards.forEach((card, index) => {
      card.style.setProperty('--card-index', index);

      card.addEventListener('mouseenter', () => {
        card.addEventListener('mousemove', (e) => {
          const rect = card.getBoundingClientRect();
          const x = e.clientX - rect.left;
          const y = e.clientY - rect.top;
          const centerX = rect.width / 2;
          const centerY = rect.height / 2;
          const rotateX = ((y - centerY) / centerY) * -10;
          const rotateY = ((x - centerX) / centerX) * 10;

          card.style.transform = `perspective(500px) translateZ(20px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.05)`;
        });
      });

      card.addEventListener('mouseleave', () => {
        card.style.transform = 'perspective(500px) translateZ(10px)';
        card.removeEventListener('mousemove', null);
      });
    });
  }

  function setupProjectCards() {
    const projectCards = document.querySelectorAll('.project-card');

    projectCards.forEach(card => {
      card.addEventListener('mouseenter', () => {
        card.classList.add('magnetic');
      });

      card.addEventListener('mouseleave', () => {
        card.classList.remove('magnetic');
      });
    });
  }

  function setupIntersectionObserver() {
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -50px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.animation = 'none';
          entry.target.offsetHeight;
          entry.target.style.animation = 'fadeIn3D 1s ease-out forwards';
        }
      });
    }, observerOptions);

    document.querySelectorAll('section').forEach(section => {
      observer.observe(section);
    });
  }

  document.addEventListener('DOMContentLoaded', () => {
    createParticles();
    setupScrollTop();
    setupTechCards();
    setupProjectCards();
    setupIntersectionObserver();

    const style = document.createElement('style');
    style.textContent = `
      @keyframes fadeIn3D {
        to {
          opacity: 1;
          transform: translateY(0) rotateX(0);
        }
      }
    `;
    document.head.appendChild(style);

    setTimeout(() => {
      setupTechCards();
    }, 100);
  });

  let resizeTimeout;
  window.addEventListener('resize', () => {
    clearTimeout(resizeTimeout);
    resizeTimeout = setTimeout(() => {
      const container = document.getElementById('particles');
      container.innerHTML = '';
      createParticles();
    }, 500);
  });

  window.addEventListener('load', () => {
    setTimeout(() => {
      console.log('3D Portfolio loaded successfully!');
    }, 1000);
  });
</script>

</div>
