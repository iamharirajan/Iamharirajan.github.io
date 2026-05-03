<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HARIRAJAN M — Aerospace Design Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@300;400;600;700;900&family=Barlow:wght@300;400;500;600&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<style>
:root {
  --nasa-blue: #0b3d91;
  --nasa-red: #fc3d21;
  --nasa-white: #ffffff;
  --space-black: #030712;
  --deep-space: #050e24;
  --accent-cyan: #00b4d8;
  --accent-glow: rgba(0,180,216,0.15);
  --panel-bg: rgba(5,14,36,0.92);
  --border: rgba(0,180,216,0.18);
  --text-primary: #e8f4fd;
  --text-secondary: rgba(180,215,240,0.6);
  --text-muted: rgba(140,180,220,0.4);
  --mono: 'Share Tech Mono', monospace;
  --display: 'Barlow Condensed', sans-serif;
  --body: 'Barlow', sans-serif;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  font-family: var(--body);
  background: var(--space-black);
  color: var(--text-primary);
  overflow-x: hidden;
  line-height: 1.6;
}

/* ═══ STARFIELD CANVAS ═══ */
#starfield {
  position: fixed; inset: 0;
  z-index: 0; pointer-events: none;
}

/* ═══ NASA TOP BAR ═══ */
.nasa-bar {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  background: rgba(3,7,18,0.95);
  border-bottom: 1px solid rgba(11,61,145,0.6);
  backdrop-filter: blur(20px);
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 2rem; height: 56px;
}

.nasa-bar-left {
  display: flex; align-items: center; gap: 16px;
}

.nasa-logo-img {
  width: 64px; height: 64px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid var(--nasa-blue);
  box-shadow: 0 0 20px rgba(11,61,145,0.6), 0 0 40px rgba(0,180,216,0.2);
  filter: brightness(1.1) saturate(1.2);
}

.nasa-bar-title {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.25em; text-transform: uppercase;
  color: var(--nasa-white);
}

.nasa-bar-title span { color: var(--accent-cyan); }

.nasa-bar-nav {
  display: flex; gap: 0; align-items: center;
}

.nav-link {
  font-family: var(--display);
  font-size: 11px; font-weight: 600;
  letter-spacing: 0.14em; text-transform: uppercase;
  color: var(--text-secondary);
  text-decoration: none;
  padding: 0 14px; height: 56px;
  display: flex; align-items: center;
  border-bottom: 2px solid transparent;
  transition: all 0.2s;
}

.nav-link:hover { color: var(--accent-cyan); border-bottom-color: var(--accent-cyan); }

.status-dot {
  width: 7px; height: 7px; border-radius: 50%;
  background: #00ffaa;
  box-shadow: 0 0 8px #00ffaa;
  animation: pulse 2s infinite;
  margin-right: 6px;
}

@keyframes pulse {
  0%,100% { opacity:1; transform:scale(1); }
  50% { opacity:0.4; transform:scale(0.75); }
}

.status-label {
  font-family: var(--mono);
  font-size: 10px; color: #00ffaa;
  letter-spacing: 0.1em;
}

/* ═══ MAIN LAYOUT ═══ */
.main {
  position: relative; z-index: 1;
  padding-top: 56px;
}

/* ═══ HERO SECTION ═══ */
.hero {
  min-height: 100vh;
  display: flex; flex-direction: column;
  justify-content: center; align-items: flex-start;
  padding: 6rem 5% 4rem;
  position: relative; overflow: hidden;
}

.hero-bg-img {
  position: absolute; inset: 0;
  background: url('data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAKAAoADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD5/ooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAFxjrSUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRinYAopwU0oTNUoNiuMpQDUqxn0qRYjjpVxotkuaKtFFFYlhRRRQAUUoxzn8KSgAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAoopSMY5oASiiigAooooAKKKKACiiigAooooAKKKKACijFLg07MQlFPCHNOWM01BsXMR0oQmp1hOKlWEkc1vGg2Q6iRWVDTxFVxLck1MtvXVTwjZlKskUVgOalWD2q8sOD0p4ix2rshgu5i65TS39qeIKtYC9arvcqmRnNa+xp017xKlKWxiUUUV82ekFFFGaACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKULmmk2ISinqhNPWI1SptickRYpwQntVhYamWAnrW8MO2ZuokVFjNSrEfSrqW3tU6W2O1ddPCMxlXRQWAntUy25x0rQW19qnWAY6V2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rUduT2NWorTPauunhHIxlWSKKQn0qzHbH0rRisz6VdisvavRpYI5KmKSMyK056Vcis/atWKz9qtx2ntXo0sIkefUxhmRWftVyO046VqR2hOBircVh3PSuqNOMTkdac9jLjtcc4q1Hat/d+vFaKwIg561HLcwwrgHv0zV3SIUJS3IhbALyQKR5I4VO7A+tVZb5pD8mcVQnmSJx59wqMRnbnmuepjKdNb3Oingpy8i3NqChiIxnniqUsski7nYInck4rLvNdtLT5bch29etYFzrVzcPuDFfQ5yRXj4jNm9Inp0MvjHodNNc20K7pHA46vx+Q71j3muxkNHbhmHr90VgSSPI5aRizHqSc0yvJqYqpPyPQhQjEkkmeViWbr2qOiiuU3sFFFFMAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAHbfk3cdcdefyptFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFKBmnBDVRi2K4ynheAT3qVYqnSAmt4UJMzdRIrLFntUyQk9qux2p9KuRWWeMV3UsG2c88QkZ0cGatxWhPUVqQ2XtV6Gyx2r0qWCSOGpi0jLhs/arsdmPStSOzz2q9BYM/RTiu+GHjE8+eKb2MuKzwOlXorNjgbTWzDpg6EEn0NXks1QFeMVfNGOxnyVJ7mJDY5GcfpV+LT1TnvV9vLiHOMetUri+UNhOTSlVtvoaQw3zJtkceehHeqkt6ig7Rkj0qu3nzk5JAz3OKpzS2ttGXmlU7epY8CuKrjoU0dlPBt7j3mlm4HC9sdKz7m5trRcTy7pD0jQZP6VBd+IbVELO7JGR8oXgt9K5S78QSyl1tYlt1Y8sOXP415FfNJT0jqejSwcYdC/qXia4QmG3h8j3b71c1NcSzyF5JGZj1JNMLFiSxJJ7k02vNnVnP4mdcYRjsFFFFZlhRRRQAUUUUAFFFFABRRRQAUYoooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKaQgpcUoUmpFjJq402xOViMKTT1TNWEgzzViO2J4xXTTwzZlKqkU0iz2q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fxHc6IVPZ/ArHs998X7KK1EdpbvcSFeWk+UZ+leea94w1TxDJ/pE5SD+GFOFH+Nc4c5oXIPWuWhl2HoS54q77vU2qYyrNWbsvITPWkooruOUKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAopcGnBCelUotiuNAzTglSpCSeBVmK3PpXRSw8pGcqiRWSImrEcOauxWxz0q9DZk9q9GjgWclTEJGfHbegq9BZ56itKGyz2rRhsvavVo4NLc86rjDMhshWhFZYHStW205n6LW3aaLnBZc8d667Qpo4nVqVH7phW2nu5wFP5Vs2mjZxuGfwrorbSlX+HitSGxVQDjmuapiktjanhG9ZGJa6UEHStWCxA/hH4VorAq+lOHXCiuSddyO+FBRIVgCD7tOLYBAGTUqxO56E1ettIkkGX4WuSpiIwV5M6oUW9jJCPIePyFXrfSpHwXGAa2Vt7e1TCqGesLxP4gGj6Lc3jr5hjGRChxu+vtXz2M4gpU5ezp6yeyPQoZfKe5YvbzS9DtjNcyjC9hyWPoAOSa8h+IvjrVr3Tmsl0qWwsJzgSTjDuB7dhTPF/wATWe5t4tHkEUShWkZANxP93J7V5pq+t3msXTXFzKzuc8scnFcWHnisTJVK6su1/wCv1O2cKFGDjF+8UJG3HrgVCGx0FITk0leikcApJPWkoopjCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKXFPCZqlFsTZGKeq5qZIcmrMdtntXRTw7kZSqJFVIie1Wo7firkdpwOKvw2WR0r06GBOSpiUihFan0q9DaZ7VpQ2XTitGCy/2TXq0sIo7nm1cYZsFl7Vow2Wei5rYtdJdmGVIFblpoq8Hbz610XhTRyc1Sq9Dn7XS5ZOinityz0XbgkVv2ulhf4f0rVgsgo6Vy1MX0R00sHfVmRbaYF/h/StWGxA7VeWBUHNSAE8AVwTrykd8KEYkCQhOuKXknCirUdq8zAY3H0FasOkpFGZLp1RV5OTgD61yVcTCmveZ0wouWxiQ20kxwqkn2rTg0Yqu6U477RUq6vZoCLJBIq/elPCD6HvXk+sfGWeLUWEWn79PEhTziThsHk+9eLVzfnbjQV2j0KeCtrPQ9bRLeFfkAYj8qq3mrQW8ZMkqgAZIzgCvLdd+LVhb24+w/6RIw5P3QteTaz4x1PV7iZ3mZVlxlVOBXzzjmWYv957kfxPRVOhh/jevZHrvjH4nQWlpLb6ZOrXR6MvIFePa34t1bW5WN1dOVP8AOAPwrBaRn+8c0wmvUweWUMKtFd93uc1bFynpBWQpYsSScmkBwaSivROQKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAopQKcq5HSrjFsTY0c09Vz2qVYcnpVmO39q6KeHcjKVRIrLFntVmODParsVoW7VfgsvavTo4I5KmJSKENtk9Kvw2RPatKGx9q0rexJ4Ck/hXq0sJGO55lXGdjMgsPatGGz9untWzaaS743DFb9powUZKcj2rdyhTOb97VZz9rpTyMPl4retNHUY+QfiK3rbTAMfLWpDZBRnFcdXF9jqpYNLVmPbaYAB8uMVqw2QHUfWryQqnpUigt90Z964Z12zvhRSIVgVV6VIq5GFHNW4bKSZsAE1rQaZFCm+YjjnHauKriYQWrOmFJsxY7SSU9CcVow6YqJvuGCIOuTWN4m8eaR4ZjVAyPcNwiDkn6AcmuK1DWvEXiW3EkrrpOnkZeSRhuI+navDxWbqC93+v68j0cPl8p7naar400/SMQaciTzM20Engn2HU/hWC2o3F8Dda5NiMHcsLHai/8B/xzXmureLNL8NwPbaH/AKTesMPeSHcfwrz3UfEOpaow+23cs+3pvPSvIlQxmOV3Llj+L+X+Z6N8PhdGrs9j8TfFGysrWS300rNPjCHqgrxC5vJbiWR3ckuxYgcDJOTxVcuSTk03qelelgcvpYSLUN3u2cOIxTquyVkIWJPU02iiu45gooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigBcGnKhNSpEW5qzHbnFddPDuRlKokV1hz2qzHB7Vcitd1X4bI8DFenQwRx1MSkUIrbPatCGy9q0YbHpxWlBZZ7Zr1aWEUVqebVxnYzoLDGOK0rexLYwua17TSHkwTwK6Gy0YKAAvFbudOmjk/e1Wc9aaS8mMjr2robLRwuPkFbtppgXtWrBZAL0riq4zsdlLBpasybbTQADtrUgslUD5avJAqCpAMjCjNcE6zkzvhSSIVhC9qfgk4UVYhtWlbGCfpWrb6WAN0pwPQVyTrxhuzeFNvYyYLKSZsBSTWtBpscSbpyMDt2rP8AEHi7RfCduTeXEcb4ysfc14V4s+Meq6xJLb6ahht+QCR29T/9evMqY2Um4wOynh0leR7J4h+I/h3wxG0UtyjygfcTk14x4m+Nuq6mZoNKjFtEx+WVh8wH06CvL7i4ku5ZJrqd5JW5JJzk1Vzmuf2PPrUd/wAjTn5fh0NmTWmmtnaUSS6g8m83jyksPYVXn1vUbi3S3lvZ3iUcIzkj8qzM0ma0VKO9g9tO1kxxcseTn6000mKK0sZ3uFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQBuQ2/tWhBZZI4q/b2PtWrbWROAAa+yo4RJXZ87WxfYzYLHHatOCyyOFJ/Cte00h3xlTiuhstFCj7vOPSuhyp00ci9pVZgWmku5GVrobLRgpHy/pW7aaYBj5a1oLEDnbXFVxnY66WDS1Zk2umgY+UflWrBYqB0rQjtwOwqVVHQA15867kd0KSRAkAUdKlC9lGfpVmKzd+oNaMGnY5kOB6CuOdaMTpjTbMuO1aU4wfoK0ItOSJC85CooyRnAA96z9b8X6H4at5jPdRefGOYVYFj/hXhfj74v3GvwtY2Aa3s2XEiBsmT6n0rgqYxydoHRGhy6s9k1r4keFvDkS/6dFcuRwlswf8AMjgVwXif47wbGt/Dtu0khGPOlGAD7DvXgE11LcPliTUaMUNc0oOfxM2jJLZGzrGp3ur3zXuqXjzzseQWzj2Hp+FVLrUmkiEMUSQxD+BB1+p71ntISab3q401pcp1Xql1AuT7UmaSirsZBRRRTAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA9jstMaXtj8K6Kx0YAfdrcs9LVcfL0rbtrAKvSvrq2N7HzdHB9ZGVaaWFxhRWvBYhR05q/FbBRmp9gFebUruR6EKSSII7cL2qdUAwKsR20kxAA61ow6eE5c81xTrJbnVGm2ZsVq8rYANacGnJGMvyagv9XsNITbJJmQ8LGg3Ox+lc34g8dWOg2vnapdLaAjKQJ80rfh2rysTmUIPlWr7Lc66eHbVzsJbmG3UqMbh/CK8t8efFi10MS2VpKs13ghljOQn1P9K8z8V/FjVdeLW+k+ZYWPIJB+d/qa86meMszFmlcnlmPU1yxjWrO9TRdl+rN7RgtNWWtb8QX2u3013cyFnkbJIrJ245OKc0n93H0qLJPWu6EUlZIwk23djiw6CmZooqhBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFACgZB5pKKKACiiigAooooAKKKKACiiigAooooA+yobVV7VbRAop6RlzhV/KtC304kbpDgV6E6ttzijTvsUo4WkOFWtGDTguDJ+VQanrWleHrVp7y4SJQO55NeYa18T9S1rfF4eaKztBw95OwGB689K86vjoxW52UsLKXQ9Q1HW9P0jbFJJm4f7lvEN0jfQf1PFc1rPiuSxtjc6pcJpdqRkRhgZG9s+v0/OvKJ/H1noMEzaU51DVJT+8v5uVz7Z5Neaavreoazetd6jdNcSnpluB7AV5SliMVf7Efxf+R3eyhS31Z3+vfFK4kung8OQ/Z4gfmuZuZGPrz0/nXnd5eyXlzLcXkr3NxISWdycZrPebC7RgY7CoTIWPNdlHCwp/Cv8zOddsmmuSxIBz71WLE9TSUV0qKRzuTe4UUUUxBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQB91XN5p+kQl55ETA7nk1wni34lW2j2O9jLbh/9WoX94/0B6fU1yWreMrfT5Wt7Gf8AtzWOd84OIofXnoB/nNeXardJdXclzfTi+vWOfl4ij9gO9eX7epiJa6R/F/5I7o4ZQjf/AIYva946n1+6JWBzFg/u95JYf7TensMCudubye5VftEoZI+VhTiNPwqpLcqoKqQB/dXgfjVJpncY6D0FddOklsjKVW2l7lua7J4JAx0A7VUeUk8VGTk5NJW0YJGMqjluFFFFWQFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAb1zqzeUYIQsMHeOP8Ai+p71kyzl+AeKgOTzmkrONNR2NaledTdi5pKKK0MgooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigApRjnP4UlFABRTipGOnIz1ptABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH//2Q==') center/cover no-repeat;
  opacity: 0.22;
  filter: saturate(1.4) brightness(0.8);
  z-index: 0;
}

.hero-gradient {
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(3,7,18,0.85) 40%, rgba(11,61,145,0.15) 100%);
  z-index: 1;
}

.hero-content { position: relative; z-index: 2; max-width: 780px; }

.mission-badge {
  display: inline-flex; align-items: center; gap: 8px;
  font-family: var(--mono); font-size: 10px; letter-spacing: 0.18em;
  color: var(--accent-cyan);
  background: rgba(0,180,216,0.08);
  border: 1px solid rgba(0,180,216,0.3);
  padding: 6px 16px; border-radius: 2px;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
}

.mission-badge::before {
  content: '▶'; font-size: 8px; color: var(--nasa-red);
}

.hero-callsign {
  font-family: var(--mono); font-size: 11px;
  color: var(--nasa-red); letter-spacing: 0.3em;
  text-transform: uppercase; margin-bottom: 0.6rem;
}

.hero-name {
  font-family: var(--display);
  font-size: clamp(52px, 9vw, 100px);
  font-weight: 900; line-height: 0.92;
  text-transform: uppercase; letter-spacing: -0.01em;
  color: var(--nasa-white);
  margin-bottom: 1rem;
}

.hero-name .accent { color: var(--accent-cyan); }

.hero-title-bar {
  display: flex; align-items: center; gap: 12px;
  margin-bottom: 1.5rem;
}

.hero-title-line {
  width: 40px; height: 2px;
  background: var(--nasa-red);
}

.hero-title {
  font-family: var(--display);
  font-size: 18px; font-weight: 400;
  letter-spacing: 0.18em; text-transform: uppercase;
  color: rgba(180,215,240,0.8);
}

.hero-desc {
  font-size: 15px; font-weight: 300;
  color: var(--text-secondary); line-height: 1.8;
  margin-bottom: 2rem; max-width: 520px;
}

.hero-specs {
  display: flex; gap: 20px; flex-wrap: wrap;
  margin-bottom: 2.5rem;
}

.spec-item {
  font-family: var(--mono); font-size: 11px;
  color: var(--text-muted); letter-spacing: 0.08em;
  display: flex; align-items: center; gap: 6px;
}

.spec-item::before {
  content: '//'; color: var(--nasa-red); font-size: 10px;
}

.hero-ctas {
  display: flex; gap: 12px; flex-wrap: wrap;
}

.btn-primary {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.2em; text-transform: uppercase;
  background: var(--nasa-blue);
  color: var(--nasa-white);
  border: none; padding: 14px 32px;
  cursor: pointer; text-decoration: none;
  clip-path: polygon(0 0, calc(100% - 10px) 0, 100% 10px, 100% 100%, 0 100%);
  transition: all 0.2s;
  display: inline-flex; align-items: center; gap: 8px;
}

.btn-primary:hover { background: #0d4ab0; transform: translateY(-1px); }

.btn-outline {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.2em; text-transform: uppercase;
  background: transparent;
  color: var(--accent-cyan);
  border: 1px solid rgba(0,180,216,0.5);
  padding: 13px 32px;
  cursor: pointer; text-decoration: none;
  clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
  transition: all 0.2s;
  display: inline-flex; align-items: center; gap: 8px;
}

.btn-outline:hover { background: rgba(0,180,216,0.1); border-color: var(--accent-cyan); }

.btn-yt {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.2em; text-transform: uppercase;
  background: transparent;
  color: #ff4040;
  border: 1px solid rgba(255,64,64,0.4);
  padding: 13px 28px;
  cursor: pointer; text-decoration: none;
  clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
  transition: all 0.2s;
  display: inline-flex; align-items: center; gap: 8px;
}

.btn-yt:hover { background: rgba(255,64,64,0.1); border-color: #ff4040; }

.btn-ig {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.2em; text-transform: uppercase;
  background: transparent;
  color: #e1306c;
  border: 1px solid rgba(225,48,108,0.4);
  padding: 13px 28px;
  cursor: pointer; text-decoration: none;
  clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
  transition: all 0.2s;
  display: inline-flex; align-items: center; gap: 8px;
}
.btn-ig:hover { background: rgba(225,48,108,0.1); border-color: #e1306c; }

/* ═══ SCROLLING TICKER ═══ */
.ticker-wrap {
  background: var(--nasa-blue);
  overflow: hidden; white-space: nowrap;
  padding: 10px 0;
  border-top: 1px solid rgba(255,255,255,0.1);
  border-bottom: 1px solid rgba(255,255,255,0.1);
}

.ticker-inner {
  display: inline-block;
  animation: ticker 30s linear infinite;
}

@keyframes ticker {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

.ticker-item {
  display: inline-flex; align-items: center; gap: 24px;
  font-family: var(--mono); font-size: 11px;
  color: rgba(255,255,255,0.85); letter-spacing: 0.12em;
  margin-right: 60px;
}

.ticker-item::before { content: '◆'; color: var(--nasa-red); font-size: 7px; }

/* ═══ SECTION WRAPPER ═══ */
.section {
  padding: 5rem 5%;
  position: relative; z-index: 1;
}

.section-alt { background: rgba(11,61,145,0.04); }

.section-header {
  display: flex; align-items: center; gap: 16px;
  margin-bottom: 3rem;
}

.section-num {
  font-family: var(--mono); font-size: 11px;
  color: var(--nasa-red); letter-spacing: 0.2em;
}

.section-title {
  font-family: var(--display);
  font-size: 13px; font-weight: 700;
  letter-spacing: 0.3em; text-transform: uppercase;
  color: var(--accent-cyan);
}

.section-line {
  flex: 1; height: 1px;
  background: linear-gradient(90deg, rgba(0,180,216,0.4), transparent);
}

/* ═══ MISSION CARDS (Projects) ═══ */
.missions-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1px;
  background: rgba(0,180,216,0.1);
  border: 1px solid var(--border);
}

.mission-card {
  background: var(--panel-bg);
  padding: 2rem; position: relative;
  overflow: hidden; transition: background 0.3s;
}

.mission-card:hover { background: rgba(11,61,145,0.25); }

.mission-card::after {
  content: '';
  position: absolute; bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--nasa-red), var(--accent-cyan), transparent);
  transform: scaleX(0); transform-origin: left;
  transition: transform 0.4s;
}

.mission-card:hover::after { transform: scaleX(1); }

.mission-id {
  font-family: var(--mono); font-size: 10px;
  color: var(--nasa-red); letter-spacing: 0.2em;
  margin-bottom: 1rem;
}

.mission-name {
  font-family: var(--display);
  font-size: 20px; font-weight: 700;
  letter-spacing: 0.05em; text-transform: uppercase;
  color: var(--nasa-white); margin-bottom: 0.75rem;
}

.mission-desc {
  font-size: 13px; color: var(--text-secondary);
  line-height: 1.75; margin-bottom: 1.25rem;
}

.mission-tags {
  display: flex; flex-wrap: wrap; gap: 6px;
}

.mission-tag {
  font-family: var(--mono); font-size: 9px;
  letter-spacing: 0.15em; text-transform: uppercase;
  padding: 3px 10px;
  background: rgba(11,61,145,0.3);
  border: 1px solid rgba(0,180,216,0.2);
  color: var(--accent-cyan);
}

/* ═══ EXPERIENCE ═══ */
.exp-block {
  border: 1px solid var(--border);
  background: var(--panel-bg);
  position: relative; overflow: hidden;
}

.exp-header {
  display: flex; align-items: stretch;
  border-bottom: 1px solid var(--border);
}

.exp-color-bar {
  width: 4px;
  background: linear-gradient(180deg, var(--nasa-red), var(--nasa-blue));
}

.exp-header-content {
  padding: 2rem;
  flex: 1;
  display: flex; justify-content: space-between;
  align-items: flex-start; flex-wrap: wrap; gap: 12px;
}

.exp-org {
  font-family: var(--display);
  font-size: 26px; font-weight: 900;
  letter-spacing: 0.08em; text-transform: uppercase;
  color: var(--nasa-white);
}

.exp-role {
  font-family: var(--display);
  font-size: 14px; font-weight: 400;
  letter-spacing: 0.12em; text-transform: uppercase;
  color: var(--accent-cyan); margin-top: 4px;
}

.exp-date {
  font-family: var(--mono); font-size: 11px;
  color: var(--text-muted); letter-spacing: 0.1em;
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  padding: 6px 14px;
  align-self: flex-start;
}

.exp-body { padding: 2rem; }

.exp-bullets {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 12px;
}

.exp-bullet {
  display: flex; gap: 12px; align-items: flex-start;
  font-size: 13px; color: var(--text-secondary); line-height: 1.7;
}

.bullet-marker {
  width: 20px; height: 20px; flex-shrink: 0;
  background: rgba(11,61,145,0.4);
  border: 1px solid rgba(0,180,216,0.3);
  display: flex; align-items: center; justify-content: center;
  margin-top: 2px;
}

.bullet-marker::after {
  content: ''; width: 6px; height: 6px;
  background: var(--accent-cyan);
}

/* ═══ SKILLS ═══ */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
}

.skill-group {
  background: var(--panel-bg);
  padding: 1.75rem;
}

.skill-group-label {
  font-family: var(--mono); font-size: 9px;
  letter-spacing: 0.25em; text-transform: uppercase;
  color: var(--nasa-red); margin-bottom: 1rem;
}

.skill-chips {
  display: flex; flex-wrap: wrap; gap: 6px;
}

.skill-chip {
  font-family: var(--display);
  font-size: 12px; font-weight: 600;
  letter-spacing: 0.08em; text-transform: uppercase;
  padding: 5px 12px;
  background: rgba(11,61,145,0.2);
  border: 1px solid rgba(0,180,216,0.15);
  color: rgba(200,230,255,0.75);
  transition: all 0.2s;
}

.skill-chip:hover {
  background: rgba(11,61,145,0.45);
  border-color: rgba(0,180,216,0.4);
  color: var(--accent-cyan);
}

.skill-chip.hot {
  background: rgba(252,61,33,0.1);
  border-color: rgba(252,61,33,0.3);
  color: rgba(255,150,120,0.9);
}

.currently-learning {
  margin-top: 1rem; padding: 12px 14px;
  background: rgba(0,180,216,0.06);
  border: 1px solid rgba(0,180,216,0.2);
  border-left: 3px solid var(--accent-cyan);
}

.cl-label {
  font-family: var(--mono); font-size: 9px;
  color: var(--accent-cyan); letter-spacing: 0.2em;
  text-transform: uppercase; margin-bottom: 4px;
}

.cl-value {
  font-family: var(--display);
  font-size: 15px; font-weight: 600;
  color: var(--nasa-white);
}

/* ═══ EDUCATION ═══ */
.edu-timeline {
  position: relative; padding-left: 2rem;
}

.edu-timeline::before {
  content: ''; position: absolute;
  left: 0; top: 0; bottom: 0; width: 1px;
  background: linear-gradient(180deg, var(--nasa-blue), var(--accent-cyan), transparent);
}

.edu-item {
  position: relative; margin-bottom: 2.5rem;
  padding-left: 1.5rem;
}

.edu-item::before {
  content: ''; position: absolute;
  left: -2rem; top: 6px;
  width: 10px; height: 10px;
  background: var(--nasa-blue);
  border: 2px solid var(--accent-cyan);
  box-shadow: 0 0 12px rgba(0,180,216,0.5);
}

.edu-deg {
  font-family: var(--display);
  font-size: 18px; font-weight: 700;
  letter-spacing: 0.04em; text-transform: uppercase;
  color: var(--nasa-white); margin-bottom: 4px;
}

.edu-school {
  font-size: 13px; color: var(--text-secondary); margin-bottom: 8px;
}

.edu-meta { display: flex; gap: 8px; flex-wrap: wrap; }

.edu-badge {
  font-family: var(--mono); font-size: 10px;
  padding: 3px 10px;
  border: 1px solid var(--border);
  color: var(--text-muted); letter-spacing: 0.1em;
}

/* ═══ CERTIFICATIONS ═══ */
.cert-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1px; background: var(--border);
  border: 1px solid var(--border);
}

.cert-card {
  background: var(--panel-bg);
  padding: 1.75rem;
  display: flex; gap: 16px; align-items: flex-start;
  transition: background 0.3s;
}

.cert-card:hover { background: rgba(11,61,145,0.2); }

.cert-icon {
  width: 40px; height: 40px; flex-shrink: 0;
  background: rgba(11,61,145,0.3);
  border: 1px solid var(--border);
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
}

.cert-name {
  font-family: var(--display);
  font-size: 16px; font-weight: 700;
  letter-spacing: 0.05em; text-transform: uppercase;
  color: var(--nasa-white); margin-bottom: 4px;
}

.cert-sub {
  font-size: 12px; color: var(--text-secondary);
}

/* ═══ YOUTUBE SECTION ═══ */
.yt-section {
  background: rgba(252,61,33,0.05);
  border: 1px solid rgba(252,61,33,0.2);
  padding: 3rem;
  display: flex; gap: 3rem; align-items: center;
  flex-wrap: wrap;
}

.yt-icon-big {
  width: 80px; height: 56px; flex-shrink: 0;
  background: #ff0000;
  border-radius: 12px;
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 0 40px rgba(255,0,0,0.3);
}

.yt-icon-big::after {
  content: '▶';
  font-size: 28px; color: white;
  margin-left: 4px;
}

.yt-content { flex: 1; min-width: 240px; }

.yt-label {
  font-family: var(--mono); font-size: 10px;
  color: #ff4040; letter-spacing: 0.25em;
  text-transform: uppercase; margin-bottom: 8px;
}

.yt-channel {
  font-family: var(--display);
  font-size: 28px; font-weight: 900;
  letter-spacing: 0.05em; text-transform: uppercase;
  color: var(--nasa-white); margin-bottom: 8px;
}

.yt-desc {
  font-size: 14px; color: var(--text-secondary);
  margin-bottom: 1.25rem;
}

/* ═══ FOOTER ═══ */
.footer {
  background: rgba(11,61,145,0.15);
  border-top: 1px solid rgba(11,61,145,0.4);
  padding: 2rem 5%;
  display: flex; justify-content: space-between; align-items: center;
  flex-wrap: wrap; gap: 12px;
}

.footer-left {
  font-family: var(--mono); font-size: 11px;
  color: var(--text-muted); letter-spacing: 0.1em;
}

.footer-right {
  font-family: var(--mono); font-size: 11px;
  color: var(--text-muted);
}

/* ═══ SCROLLBAR ═══ */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--space-black); }
::-webkit-scrollbar-thumb { background: var(--nasa-blue); }

/* ═══ RESPONSIVE ═══ */
@media (max-width: 640px) {
  .nasa-bar-nav { display: none; }
  .hero { padding: 5rem 1.5rem 3rem; }
  .section { padding: 3rem 1.5rem; }
  .yt-section { padding: 2rem; }
  .exp-bullets { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<canvas id="starfield"></canvas>

<!-- NASA TOP BAR -->
<nav class="nasa-bar">
  <div class="nasa-bar-left">
    <img class="nasa-logo-img" src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAKAAoADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD5/ooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAFxjrSUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRinYAopwU0oTNUoNiuMpQDUqxn0qRYjjpVxotkuaKtFFFYlhRRRQAUUoxzn8KSgAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAoopSMY5oASiiigAooooAKKKKACiiigAooooAKKKKACijFLg07MQlFPCHNOWM01BsXMR0oQmp1hOKlWEkc1vGg2Q6iRWVDTxFVxLck1MtvXVTwjZlKskUVgOalWD2q8sOD0p4ix2rshgu5i65TS39qeIKtYC9arvcqmRnNa+xp017xKlKWxiUUUV82ekFFFGaACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKULmmk2ISinqhNPWI1SptickRYpwQntVhYamWAnrW8MO2ZuokVFjNSrEfSrqW3tU6W2O1ddPCMxlXRQWAntUy25x0rQW19qnWAY6V2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rUduT2NWorTPauunhHIxlWSKKQn0qzHbH0rRisz6VdisvavRpYI5KmKSMyK056Vcis/atWKz9qtx2ntXo0sIkefUxhmRWftVyO046VqR2hOBircVh3PSuqNOMTkdac9jLjtcc4q1Hat/d+vFaKwIg561HLcwwrgHv0zV3SIUJS3IhbALyQKR5I4VO7A+tVZb5pD8mcVQnmSJx59wqMRnbnmuepjKdNb3Oingpy8i3NqChiIxnniqUsski7nYInck4rLvNdtLT5bch29etYFzrVzcPuDFfQ5yRXj4jNm9Inp0MvjHodNNc20K7pHA46vx+Q71j3muxkNHbhmHr90VgSSPI5aRizHqSc0yvJqYqpPyPQhQjEkkmeViWbr2qOiiuU3sFFFFMAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAHbfk3cdcdefyptFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFKBmnBDVRi2K4ynheAT3qVYqnSAmt4UJMzdRIrLFntUyQk9qux2p9KuRWWeMV3UsG2c88QkZ0cGatxWhPUVqQ2XtV6Gyx2r0qWCSOGpi0jLhs/arsdmPStSOzz2q9BYM/RTiu+GHjE8+eKb2MuKzwOlXorNjgbTWzDpg6EEn0NXks1QFeMVfNGOxnyVJ7mJDY5GcfpV+LT1TnvV9vLiHOMetUri+UNhOTSlVtvoaQw3zJtkceehHeqkt6ig7Rkj0qu3nzk5JAz3OKpzS2ttGXmlU7epY8CuKrjoU0dlPBt7j3mlm4HC9sdKz7m5trRcTy7pD0jQZP6VBd+IbVELO7JGR8oXgt9K5S78QSyl1tYlt1Y8sOXP415FfNJT0jqejSwcYdC/qXia4QmG3h8j3b71c1NcSzyF5JGZj1JNMLFiSxJJ7k02vNnVnP4mdcYRjsFFFFZlhRRRQAUUUUAFFFFABRRRQAUYoooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKaQgpcUoUmpFjJq402xOViMKTT1TNWEgzzViO2J4xXTTwzZlKqkU0iz2q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fxHc6IVPZ/ArHs998X7KK1EdpbvcSFeWk+UZ+leea94w1TxDJ/pE5SD+GFOFH+Nc4c5oXIPWuWhl2HoS54q77vU2qYyrNWbsvITPWkooruOUKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAopcGnBCelUotiuNAzTglSpCSeBVmK3PpXRSw8pGcqiRWSImrEcOauxWxz0q9DZk9q9GjgWclTEJGfHbegq9BZ56itKGyz2rRhsvavVo4NLc86rjDMhshWhFZYHStW205n6LW3aaLnBZc8d667Qpo4nVqVH7phW2nu5wFP5Vs2mjZxuGfwrorbSlX+HitSGxVQDjmuapiktjanhG9ZGJa6UEHStWCxA/hH4VorAq+lOHXCiuSddyO+FBRIVgCD7tOLYBAGTUqxO56E1ettIkkGX4WuSpiIwV5M6oUW9jJCPIePyFXrfSpHwXGAa2Vt7e1TCqGesLxP4gGj6Lc3jr5hjGRChxu+vtXz2M4gpU5ezp6yeyPQoZfKe5YvbzS9DtjNcyjC9hyWPoAOSa8h+IvjrVr3Tmsl0qWwsJzgSTjDuB7dhTPF/wATWe5t4tHkEUShWkZANxP93J7V5pq+t3msXTXFzKzuc8scnFcWHnisTJVK6su1/wCv1O2cKFGDjF+8UJG3HrgVCGx0FITk0leikcApJPWkoopjCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKXFPCZqlFsTZGKeq5qZIcmrMdtntXRTw7kZSqJFVIie1Wo7firkdpwOKvw2WR0r06GBOSpiUihFan0q9DaZ7VpQ2XTitGCy/2TXq0sIo7nm1cYZsFl7Vow2Wei5rYtdJdmGVIFblpoq8Hbz610XhTRyc1Sq9Dn7XS5ZOinityz0XbgkVv2ulhf4f0rVgsgo6Vy1MX0R00sHfVmRbaYF/h/StWGxA7VeWBUHNSAE8AVwTrykd8KEYkCQhOuKXknCirUdq8zAY3H0FasOkpFGZLp1RV5OTgD61yVcTCmveZ0wouWxiQ20kxwqkn2rTg0Yqu6U477RUq6vZoCLJBIq/elPCD6HvXk+sfGWeLUWEWn79PEhTziThsHk+9eLVzfnbjQV2j0KeCtrPQ9bRLeFfkAYj8qq3mrQW8ZMkqgAZIzgCvLdd+LVhb24+w/6RIw5P3QteTaz4x1PV7iZ3mZVlxlVOBXzzjmWYv957kfxPRVOhh/jevZHrvjH4nQWlpLb6ZOrXR6MvIFePa34t1bW5WN1dOVP8AOAPwrBaRn+8c0wmvUweWUMKtFd93uc1bFynpBWQpYsSScmkBwaSivROQKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAopQKcq5HSrjFsTY0c09Vz2qVYcnpVmO39q6KeHcjKVRIrLFntVmODParsVoW7VfgsvavTo4I5KmJSKENtk9Kvw2RPatKGx9q0rexJ4Ck/hXq0sJGO55lXGdjMgsPatGGz9untWzaaS743DFb9powUZKcj2rdyhTOb97VZz9rpTyMPl4retNHUY+QfiK3rbTAMfLWpDZBRnFcdXF9jqpYNLVmPbaYAB8uMVqw2QHUfWryQqnpUigt90Z964Z12zvhRSIVgVV6VIq5GFHNW4bKSZsAE1rQaZFCm+YjjnHauKriYQWrOmFJsxY7SSU9CcVow6YqJvuGCIOuTWN4m8eaR4ZjVAyPcNwiDkn6AcmuK1DWvEXiW3EkrrpOnkZeSRhuI+navDxWbqC93+v68j0cPl8p7naar400/SMQaciTzM20Engn2HU/hWC2o3F8Dda5NiMHcsLHai/8B/xzXmureLNL8NwPbaH/AKTesMPeSHcfwrz3UfEOpaow+23cs+3pvPSvIlQxmOV3Llj+L+X+Z6N8PhdGrs9j8TfFGysrWS300rNPjCHqgrxC5vJbiWR3ckuxYgcDJOTxVcuSTk03qelelgcvpYSLUN3u2cOIxTquyVkIWJPU02iiu45gooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigBcGnKhNSpEW5qzHbnFddPDuRlKokV1hz2qzHB7Vcitd1X4bI8DFenQwRx1MSkUIrbPatCGy9q0YbHpxWlBZZ7Zr1aWEUVqebVxnYzoLDGOK0rexLYwua17TSHkwTwK6Gy0YKAAvFbudOmjk/e1Wc9aaS8mMjr2robLRwuPkFbtppgXtWrBZAL0riq4zsdlLBpasybbTQADtrUgslUD5avJAqCpAMjCjNcE6zkzvhSSIVhC9qfgk4UVYhtWlbGCfpWrb6WAN0pwPQVyTrxhuzeFNvYyYLKSZsBSTWtBpscSbpyMDt2rP8AEHi7RfCduTeXEcb4ysfc14V4s+Meq6xJLb6ahht+QCR29T/9evMqY2Um4wOynh0leR7J4h+I/h3wxG0UtyjygfcTk14x4m+Nuq6mZoNKjFtEx+WVh8wH06CvL7i4ku5ZJrqd5JW5JJzk1Vzmuf2PPrUd/wAjTn5fh0NmTWmmtnaUSS6g8m83jyksPYVXn1vUbi3S3lvZ3iUcIzkj8qzM0ma0VKO9g9tO1kxxcseTn6000mKK0sZ3uFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQBuQ2/tWhBZZI4q/b2PtWrbWROAAa+yo4RJXZ87WxfYzYLHHatOCyyOFJ/Cte00h3xlTiuhstFCj7vOPSuhyp00ci9pVZgWmku5GVrobLRgpHy/pW7aaYBj5a1oLEDnbXFVxnY66WDS1Zk2umgY+UflWrBYqB0rQjtwOwqVVHQA15867kd0KSRAkAUdKlC9lGfpVmKzd+oNaMGnY5kOB6CuOdaMTpjTbMuO1aU4wfoK0ItOSJC85CooyRnAA96z9b8X6H4at5jPdRefGOYVYFj/hXhfj74v3GvwtY2Aa3s2XEiBsmT6n0rgqYxydoHRGhy6s9k1r4keFvDkS/6dFcuRwlswf8AMjgVwXif47wbGt/Dtu0khGPOlGAD7DvXgE11LcPliTUaMUNc0oOfxM2jJLZGzrGp3ur3zXuqXjzzseQWzj2Hp+FVLrUmkiEMUSQxD+BB1+p71ntISab3q401pcp1Xql1AuT7UmaSirsZBRRRTAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA9jstMaXtj8K6Kx0YAfdrcs9LVcfL0rbtrAKvSvrq2N7HzdHB9ZGVaaWFxhRWvBYhR05q/FbBRmp9gFebUruR6EKSSII7cL2qdUAwKsR20kxAA61ow6eE5c81xTrJbnVGm2ZsVq8rYANacGnJGMvyagv9XsNITbJJmQ8LGg3Ox+lc34g8dWOg2vnapdLaAjKQJ80rfh2rysTmUIPlWr7Lc66eHbVzsJbmG3UqMbh/CK8t8efFi10MS2VpKs13ghljOQn1P9K8z8V/FjVdeLW+k+ZYWPIJB+d/qa86meMszFmlcnlmPU1yxjWrO9TRdl+rN7RgtNWWtb8QX2u3013cyFnkbJIrJ245OKc0n93H0qLJPWu6EUlZIwk23djiw6CmZooqhBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFACgZB5pKKKACiiigAooooAKKKKACiiigAooooA+yobVV7VbRAop6RlzhV/KtC304kbpDgV6E6ttzijTvsUo4WkOFWtGDTguDJ+VQanrWleHrVp7y4SJQO55NeYa18T9S1rfF4eaKztBw95OwGB689K86vjoxW52UsLKXQ9Q1HW9P0jbFJJm4f7lvEN0jfQf1PFc1rPiuSxtjc6pcJpdqRkRhgZG9s+v0/OvKJ/H1noMEzaU51DVJT+8v5uVz7Z5Neaavreoazetd6jdNcSnpluB7AV5SliMVf7Efxf+R3eyhS31Z3+vfFK4kung8OQ/Z4gfmuZuZGPrz0/nXnd5eyXlzLcXkr3NxISWdycZrPebC7RgY7CoTIWPNdlHCwp/Cv8zOddsmmuSxIBz71WLE9TSUV0qKRzuTe4UUUUxBRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQB91XN5p+kQl55ETA7nk1wni34lW2j2O9jLbh/9WoX94/0B6fU1yWreMrfT5Wt7Gf8AtzWOd84OIofXnoB/nNeXardJdXclzfTi+vWOfl4ij9gO9eX7epiJa6R/F/5I7o4ZQjf/AIYva946n1+6JWBzFg/u95JYf7TensMCudubye5VftEoZI+VhTiNPwqpLcqoKqQB/dXgfjVJpncY6D0FddOklsjKVW2l7lua7J4JAx0A7VUeUk8VGTk5NJW0YJGMqjluFFFFWQFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAb1zqzeUYIQsMHeOP8Ai+p71kyzl+AeKgOTzmkrONNR2NaledTdi5pKKK0MgooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigApRjnP4UlFABRTipGOnIz1ptABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH//2Q==" alt="Nebula Logo">
    <div class="nasa-bar-title">HARI<span>RAJAN</span> · M</div>
  </div>
  <div class="nasa-bar-nav">
    <a href="#missions" class="nav-link">Projects</a>
    <a href="#experience" class="nav-link">Experience</a>
    <a href="#systems" class="nav-link">Skills</a>
    <a href="#channel" class="nav-link">Channel</a>
    <a href="#contact" class="nav-link">Contact</a>
  </div>
  <div style="display:flex;align-items:center;gap:8px;">
    <div class="status-dot"></div>
    <span class="status-label">OPEN TO OPPORTUNITIES</span>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg-img"></div>
  <div class="hero-gradient"></div>
  <div class="hero-content">
    <div class="mission-badge">Mission Status: Active · Design Trainee</div>
    <div class="hero-callsign">// AE-DESIGN · PROPULSION SYSTEMS</div>
    <h1 class="hero-name">HARI<span class="accent">RAJAN</span><br>M</h1>
    <div class="hero-title-bar">
      <div class="hero-title-line"></div>
      <div class="hero-title">Aerospace &amp; Propulsion Design Engineer</div>
    </div>
    <p class="hero-desc">
      Mechanical design engineer specializing in rocket and missile systems. 
      Creating production-ready hardware from nozzles to airframes — where precision engineering meets the edge of the atmosphere.
    </p>
    <div class="hero-specs">
      <div class="spec-item">SolidWorks · CATIA V5</div>
      <div class="spec-item">Propulsion Hardware</div>
      <div class="spec-item">Structures &amp; Airframes</div>
      <div class="spec-item">Madurai, India</div>
    </div>
    <div class="hero-ctas">
      <a href="mailto:iamharirajan2002@gmail.com" class="btn-primary">✉ Contact Mission Control</a>
      <a href="#missions" class="btn-outline">↓ View Projects</a>
      <a href="https://www.youtube.com/@nebulaspacetime" target="_blank" class="btn-yt">▶ Nebula Spacetime</a>
      <a href="https://www.instagram.com/nebulaspacetime" target="_blank" class="btn-ig">◈ Instagram</a>
    </div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker-wrap">
  <div class="ticker-inner">
    <span class="ticker-item">SOLIDWORKS DESIGN</span>
    <span class="ticker-item">CATIA V5 · PROPULSION SYSTEMS</span>
    <span class="ticker-item">ROCKET NOZZLE ENGINEERING</span>
    <span class="ticker-item">CUBESAT PROTOTYPES</span>
    <span class="ticker-item">STATIC FIRE TEST OPERATIONS</span>
    <span class="ticker-item">SPACE ZONE AEROSPACE · DESIGN TRAINEE</span>
    <span class="ticker-item">IELTS B2 · NCC C CERTIFICATE</span>
    <span class="ticker-item">CFD LEARNING IN PROGRESS</span>
    <span class="ticker-item">NEBULA SPACETIME · YOUTUBE CHANNEL</span>
    <span class="ticker-item">INSTAGRAM · @NEBULASPACETIME</span>
    <!-- repeat for seamless loop -->
    <span class="ticker-item">SOLIDWORKS DESIGN</span>
    <span class="ticker-item">CATIA V5 · PROPULSION SYSTEMS</span>
    <span class="ticker-item">ROCKET NOZZLE ENGINEERING</span>
    <span class="ticker-item">CUBESAT PROTOTYPES</span>
    <span class="ticker-item">STATIC FIRE TEST OPERATIONS</span>
    <span class="ticker-item">SPACE ZONE AEROSPACE · DESIGN TRAINEE</span>
    <span class="ticker-item">IELTS B2 · NCC C CERTIFICATE</span>
    <span class="ticker-item">CFD LEARNING IN PROGRESS</span>
    <span class="ticker-item">NEBULA SPACETIME · YOUTUBE CHANNEL</span>
    <span class="ticker-item">INSTAGRAM · @NEBULASPACETIME</span>
  </div>
</div>

<!-- PROJECTS -->
<section class="section" id="missions">
  <div class="section-header">
    <span class="section-num">01</span>
    <span class="section-title">Mission Manifest / Projects</span>
    <div class="section-line"></div>
  </div>
  <div style="margin-bottom:1.5rem;padding:14px 20px;background:rgba(252,61,33,0.06);border:1px solid rgba(252,61,33,0.25);border-left:3px solid var(--nasa-red);display:flex;align-items:center;gap:12px;">
    <span style="font-size:18px;">🔒</span>
    <div>
      <div style="font-family:var(--mono);font-size:10px;color:var(--nasa-red);letter-spacing:0.2em;text-transform:uppercase;margin-bottom:2px;">Confidentiality Notice</div>
      <div style="font-size:13px;color:var(--text-secondary);">Due to confidentiality agreements, specific design data, drawings, and test details are not displayed. Project descriptions reflect scope only.</div>
    </div>
  </div>
  <div class="missions-grid">
    <div class="mission-card">
      <div class="mission-id">MISSION-001 · PROPULSION</div>
      <div class="mission-name">Propulsion Component Design</div>
      <div class="mission-desc">
        Full design packages for nozzles, injectors, pyrotechnic valves, fins, airframes, and fuel grains — complete with tolerances and material callouts for manufacturing release.
      </div>
      <div class="mission-tags">
        <span class="mission-tag">Hybrid Systems</span>
        <span class="mission-tag">Solid Propulsion</span>
        <span class="mission-tag">SolidWorks</span>
      </div>
    </div>
    <div class="mission-card">
      <div class="mission-id">MISSION-002 · STRUCTURES</div>
      <div class="mission-name">Rocket Engine Static Test Bed</div>
      <div class="mission-desc">
        Structural design engineered to withstand engine thrust loads; supported live static fire operations end-to-end. Present during actual test execution.
      </div>
      <div class="mission-tags">
        <span class="mission-tag">Structures</span>
        <span class="mission-tag">Test Systems</span>
        <span class="mission-tag">Live Operations</span>
      </div>
    </div>
    <div class="mission-card">
      <div class="mission-id">MISSION-003 · SATELLITE</div>
      <div class="mission-name">CubeSat / NanoSat Prototypes</div>
      <div class="mission-desc">
        3D-printed satellite structural frames to validate fit and assembly — reducing iteration time before machined production using Ultimaker Cura and PrusaSlicer.
      </div>
      <div class="mission-tags">
        <span class="mission-tag">FDM Printing</span>
        <span class="mission-tag">Cura</span>
        <span class="mission-tag">PrusaSlicer</span>
      </div>
    </div>
    <div class="mission-card">
      <div class="mission-id">MISSION-004 · INNOVATION</div>
      <div class="mission-name">Solar-Powered Mobile Case</div>
      <div class="mission-desc">
        PV-integrated mobile case designed in CATIA V5. Selected for the state-level Naan Mudhalvan innovation program — recognized statewide for engineering excellence.
      </div>
      <div class="mission-tags">
        <span class="mission-tag">CATIA V5</span>
        <span class="mission-tag">State Selected</span>
        <span class="mission-tag">Naan Mudhalvan</span>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section class="section section-alt" id="experience">
  <div class="section-header">
    <span class="section-num">02</span>
    <span class="section-title">Flight Log / Experience</span>
    <div class="section-line"></div>
  </div>
  <div class="exp-block">
    <div class="exp-header">
      <div class="exp-color-bar"></div>
      <div class="exp-header-content">
        <div>
          <div class="exp-org">Space Zone Aerospace</div>
          <div class="exp-role">Design Trainee · Chengalpattu, Tamil Nadu</div>
        </div>
        <div class="exp-date">DEC 2025 – PRESENT</div>
      </div>
    </div>
    <div class="exp-body">
      <div class="exp-bullets">
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Designed nozzles, injectors, pyrotechnic valves (hybrid), fins, airframe sections, and fuel grains — delivering production-ready drawings in SolidWorks.</span>
        </div>
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Designed static test bed structures for engine static fire operations; present during live test execution supporting real propulsion testing.</span>
        </div>
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Involved in engine assembly and disassembly on propulsion hardware, gaining direct hands-on understanding of fit and function.</span>
        </div>
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Fabricated fuel grains and 3D printed prototype components including CubeSat/NanoSat models using Ultimaker Cura and PrusaSlicer.</span>
        </div>
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Handled full procurement workflow — prepared specs and BOMs, coordinated with vendors on materials and parts procurement.</span>
        </div>
        <div class="exp-bullet">
          <div class="bullet-marker"></div>
          <span>Produced mechanical drawings to aerospace standards; conducted DFM assessments before manufacturing release across multiple component types.</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="section" id="systems">
  <div class="section-header">
    <span class="section-num">03</span>
    <span class="section-title">Systems &amp; Capabilities</span>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-group">
      <div class="skill-group-label">// CAD Software</div>
      <div class="skill-chips">
        <span class="skill-chip hot">SolidWorks</span>
        <span class="skill-chip hot">CATIA V5</span>
        <span class="skill-chip">Parts &amp; Assemblies</span>
        <span class="skill-chip">Sheet Metal</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">// Aerospace Design</div>
      <div class="skill-chips">
        <span class="skill-chip">Nozzles</span>
        <span class="skill-chip">Injectors</span>
        <span class="skill-chip">Pyro Valves</span>
        <span class="skill-chip">Fins</span>
        <span class="skill-chip">Airframes</span>
        <span class="skill-chip">Fuel Grains</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">// Manufacturing</div>
      <div class="skill-chips">
        <span class="skill-chip">3D Printing</span>
        <span class="skill-chip">DFM</span>
        <span class="skill-chip">BOM</span>
        <span class="skill-chip">GD&amp;T</span>
        <span class="skill-chip">Procurement</span>
      </div>
    </div>
    <div class="skill-group">
      <div class="skill-group-label">// Additional</div>
      <div class="skill-chips">
        <span class="skill-chip">C Programming</span>
        <span class="skill-chip">Technical Drawing</span>
        <span class="skill-chip">Vendor Coordination</span>
      </div>
      <div class="currently-learning">
        <div class="cl-label">// Currently Learning</div>
        <div class="cl-value">Computational Fluid Dynamics (CFD)</div>
      </div>
    </div>
  </div>
</section>

<!-- EDUCATION & CERTS -->
<section class="section section-alt">
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:4rem;flex-wrap:wrap;">
    <div>
      <div class="section-header" style="margin-bottom:2rem;">
        <span class="section-num">04</span>
        <span class="section-title">Education</span>
        <div class="section-line"></div>
      </div>
      <div class="edu-timeline">
        <div class="edu-item">
          <div class="edu-deg">B.E. Mechanical Engineering</div>
          <div class="edu-school">Anna University Regional Campus, Madurai</div>
          <div class="edu-meta">
            <span class="edu-badge">2020–2024</span>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-deg">Diploma — Mechanical Eng.</div>
          <div class="edu-school">Latha Mathavan Polytechnic College</div>
          <div class="edu-meta">
            <span class="edu-badge">2018–2021</span>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-deg">SSLC</div>
          <div class="edu-school">EBG Matriculation Hr. Secondary School</div>
          <div class="edu-meta">
            <span class="edu-badge">2018</span>
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="section-header" style="margin-bottom:2rem;">
        <span class="section-num">05</span>
        <span class="section-title">Achievements</span>
        <div class="section-line"></div>
      </div>
      <div class="cert-grid" style="grid-template-columns:1fr;">
        <div class="cert-card">
          <div class="cert-icon">🌐</div>
          <div>
            <div class="cert-name">IELTS — B2 Level</div>
            <div class="cert-sub">Upper Intermediate English Proficiency</div>
          </div>
        </div>
        <div class="cert-card">
          <div class="cert-icon">🏅</div>
          <div>
            <div class="cert-name">NCC C Certificate</div>
            <div class="cert-sub">National Cadet Corps — Leadership &amp; National Service</div>
          </div>
        </div>
        <div class="cert-card">
          <div class="cert-icon">🚀</div>
          <div>
            <div class="cert-name">Naan Mudhalvan — State Level</div>
            <div class="cert-sub">Solar-powered mobile case innovation selected statewide</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- YOUTUBE -->
<section class="section" id="channel">
  <div class="section-header">
    <span class="section-num">06</span>
    <span class="section-title">Transmissions / YouTube</span>
    <div class="section-line"></div>
  </div>
  <div class="yt-section">
    <div class="yt-icon-big"></div>
    <div class="yt-content">
      <div class="yt-label">// YouTube Channel · Space Content Creator</div>
      <div class="yt-channel">Nebula Spacetime</div>
      <div class="yt-desc">
        Videos and Shorts exploring space science, aerospace engineering, rocket technology, and the universe. From propulsion to planets — demystifying the cosmos one mission at a time.
      </div>
      <a href="https://www.youtube.com/@nebulaspacetime" target="_blank" class="btn-yt">▶ Visit @nebulaspacetime</a>
      <a href="https://www.instagram.com/nebulaspacetime" target="_blank" class="btn-ig" style="margin-left:10px;">◈ @nebulaspacetime</a>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="section section-alt" id="contact">
  <div class="section-header">
    <span class="section-num">07</span>
    <span class="section-title">Open Channel / Contact</span>
    <div class="section-line"></div>
  </div>
  <div style="display:flex;gap:1.5rem;flex-wrap:wrap;align-items:stretch;">
    <div style="flex:1;min-width:260px;background:var(--panel-bg);border:1px solid var(--border);padding:2rem;">
      <div style="font-family:var(--mono);font-size:10px;color:var(--nasa-red);letter-spacing:0.2em;margin-bottom:1rem;">// PRIMARY COMM LINK</div>
      <div style="font-family:var(--display);font-size:22px;font-weight:700;text-transform:uppercase;color:var(--nasa-white);margin-bottom:4px;">Email</div>
      <div style="font-size:14px;color:var(--accent-cyan);margin-bottom:1.5rem;">iamharirajan2002@gmail.com</div>
      <a href="mailto:iamharirajan2002@gmail.com" class="btn-primary" style="font-size:12px;padding:10px 24px;">Send Message</a>
    </div>
    <div style="flex:1;min-width:260px;background:var(--panel-bg);border:1px solid var(--border);padding:2rem;">
      <div style="font-family:var(--mono);font-size:10px;color:var(--nasa-red);letter-spacing:0.2em;margin-bottom:1rem;">// LOCATION</div>
      <div style="font-family:var(--display);font-size:22px;font-weight:700;text-transform:uppercase;color:var(--nasa-white);margin-bottom:4px;">Base of Operations</div>
      <div style="font-size:14px;color:var(--text-secondary);">Madurai, Tamil Nadu, India</div>
    </div>
    <div style="flex:1;min-width:260px;background:var(--panel-bg);border:1px solid var(--border);padding:2rem;">
      <div style="font-family:var(--mono);font-size:10px;color:var(--nasa-red);letter-spacing:0.2em;margin-bottom:1rem;">// BROADCAST CHANNEL</div>
      <div style="font-family:var(--display);font-size:22px;font-weight:700;text-transform:uppercase;color:var(--nasa-white);margin-bottom:4px;">YouTube</div>
      <div style="font-size:14px;color:var(--text-secondary);margin-bottom:1.5rem;">@nebulaspacetime</div>
      <a href="https://www.youtube.com/@nebulaspacetime" target="_blank" class="btn-yt" style="font-size:12px;padding:10px 24px;">Subscribe</a>
    </div>
    <div style="flex:1;min-width:260px;background:var(--panel-bg);border:1px solid var(--border);padding:2rem;">
      <div style="font-family:var(--mono);font-size:10px;color:var(--nasa-red);letter-spacing:0.2em;margin-bottom:1rem;">// INSTAGRAM</div>
      <div style="font-family:var(--display);font-size:22px;font-weight:700;text-transform:uppercase;color:var(--nasa-white);margin-bottom:4px;">Instagram</div>
      <div style="font-size:14px;color:var(--text-secondary);margin-bottom:1.5rem;">@nebulaspacetime</div>
      <a href="https://www.instagram.com/nebulaspacetime" target="_blank" class="btn-ig" style="font-size:12px;padding:10px 24px;">Follow</a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer class="footer">
  <div class="footer-left">
    HARIRAJAN M · AEROSPACE &amp; PROPULSION DESIGN ENGINEER · MADURAI, INDIA
  </div>
  <div class="footer-right">
    DESIGNED &amp; ENGINEERED TO REACH ORBIT · 2025
  </div>
</footer>

<!-- STARFIELD + SPACE EFFECTS -->
<script>
const canvas = document.getElementById('starfield');
const ctx = canvas.getContext('2d');
let W, H, stars = [], nebulas = [], shootingStars = [];
let t = 0;

function resize() {
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
window.addEventListener('resize', () => { resize(); init(); });
resize();

function rnd(a, b) { return a + Math.random() * (b - a); }

function init() {
  stars = [];
  for (let i = 0; i < 320; i++) {
    stars.push({
      x: rnd(0, W), y: rnd(0, H),
      r: rnd(0.2, 1.8),
      o: rnd(0.15, 0.85),
      tw: rnd(0, Math.PI * 2),
      spd: rnd(0.008, 0.035),
      col: Math.random() > 0.92 ? '#a0c8ff' : '#cce4ff'
    });
  }

  nebulas = [
    { x: W * 0.1, y: H * 0.08, rx: 220, ry: 100, c: 'rgba(11,61,145,0.08)' },
    { x: W * 0.85, y: H * 0.2, rx: 180, ry: 90, c: 'rgba(0,100,200,0.06)' },
    { x: W * 0.5, y: H * 0.5, rx: 260, ry: 120, c: 'rgba(252,61,33,0.04)' },
    { x: W * 0.15, y: H * 0.8, rx: 170, ry: 80, c: 'rgba(0,180,216,0.05)' },
    { x: W * 0.9, y: H * 0.75, rx: 140, ry: 75, c: 'rgba(11,61,145,0.07)' },
  ];
}

function spawnShootingStar() {
  if (Math.random() > 0.005) return;
  shootingStars.push({
    x: rnd(W * 0.2, W),
    y: rnd(0, H * 0.3),
    len: rnd(80, 180),
    spd: rnd(8, 16),
    angle: rnd(0.6, 0.9),
    alpha: 1
  });
}

function draw() {
  ctx.clearRect(0, 0, W, H);

  // Nebulas
  nebulas.forEach(n => {
    ctx.save();
    const g = ctx.createRadialGradient(n.x, n.y, 0, n.x, n.y, Math.max(n.rx, n.ry));
    g.addColorStop(0, n.c);
    g.addColorStop(1, 'transparent');
    ctx.fillStyle = g;
    ctx.scale(n.rx / Math.max(n.rx, n.ry), n.ry / Math.max(n.rx, n.ry));
    ctx.beginPath();
    ctx.arc(n.x * Math.max(n.rx, n.ry) / n.rx, n.y * Math.max(n.rx, n.ry) / n.ry, Math.max(n.rx, n.ry), 0, Math.PI * 2);
    ctx.fill();
    ctx.restore();
  });

  // Stars
  stars.forEach(s => {
    s.tw += s.spd;
    const f = 0.5 + 0.5 * Math.sin(s.tw);
    ctx.fillStyle = s.col.replace('1)', `${s.o * f})`).replace('#cce4ff', `rgba(204,228,255,${s.o * f})`).replace('#a0c8ff', `rgba(160,200,255,${s.o * f})`);
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fill();
  });

  // Shooting stars
  spawnShootingStar();
  shootingStars = shootingStars.filter(ss => ss.alpha > 0);
  shootingStars.forEach(ss => {
    ctx.save();
    ctx.translate(ss.x, ss.y);
    ctx.rotate(ss.angle);
    const g = ctx.createLinearGradient(0, 0, ss.len, 0);
    g.addColorStop(0, `rgba(255,255,255,${ss.alpha})`);
    g.addColorStop(0.3, `rgba(0,180,216,${ss.alpha * 0.6})`);
    g.addColorStop(1, 'transparent');
    ctx.strokeStyle = g;
    ctx.lineWidth = 1.5;
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.lineTo(ss.len, 0);
    ctx.stroke();
    ctx.restore();
    ss.x -= ss.spd * Math.cos(ss.angle);
    ss.y += ss.spd * Math.sin(ss.angle) * 0.5;
    ss.alpha -= 0.012;
  });

  // Earth horizon glow (bottom)
  const horizGrad = ctx.createLinearGradient(0, H * 0.88, 0, H);
  horizGrad.addColorStop(0, 'transparent');
  horizGrad.addColorStop(0.5, 'rgba(11,61,145,0.04)');
  horizGrad.addColorStop(1, 'rgba(0,180,216,0.06)');
  ctx.fillStyle = horizGrad;
  ctx.fillRect(0, H * 0.88, W, H * 0.12);

  t++;
  requestAnimationFrame(draw);
}

init();
draw();
</script>
</body>
</html>
