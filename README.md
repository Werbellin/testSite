<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>BetterBrain client example: Linda</title>
<style>
  body {
    margin: 40px;
    font-family: 'Inter', sans-serif;
    background: #f2f2f8;
    color: #333;
  }

  h1 {
    font-size: 1.3rem;
    font-weight: 600;
    text-align: center;
    margin-bottom: 40px;
    color: #004253;
  }

  .card {
    background: #fff;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    margin-bottom: 40px;
    padding: 20px 30px;
    width: 900px;
    margin-left: auto;
    margin-right: auto;
  }

  .section-header {
    font-weight: 600;
    font-size: 1.1rem;
    color: #004253;
    margin-bottom: 20px;
  }

  .grid-row, .grid-sub-row {
    display: grid;
    grid-template-columns: 200px repeat(8,80px);
    align-items: center;
    gap: 10px;
    margin-bottom: 15px;
  }

  .category-title {
    font-weight: 600;
    font-size: 0.95rem;
    color: #004253;
    margin: 30px 0 15px 0;
    border-bottom: 1px solid #eee;
    padding-bottom: 6px;
  }

  .grid-row div:first-child,
  .grid-sub-row div:first-child {
    font-size: 0.9rem;
    font-weight: 500;
    color: #333;
  }

  .grid-sub-row div:first-child {
    padding-left: 20px;
    color: #555;
  }

  .circle {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    margin: 0 auto;
  }
  .green { background-color: #A6BE87; }
  .yellow { background-color: #D2C36E; }
  .red { background-color: #B67B5E; }

  details {
    margin-bottom: 15px;
  }

  details summary {
    display: grid;
    grid-template-columns: 200px repeat(8,80px);
    align-items: center;
    gap: 10px;
    cursor: pointer;
    margin-bottom: 10px;
    font-size: 0.9rem;
    font-weight: 500;
    color: #333;
  }

  details summary div:first-child {
    display: inline-flex;
    align-items: center;
  }

  .arrow {
    margin-left: 5px;
    display: inline-block;
    transition: transform 0.2s ease;
  }

  details:not([open]) .arrow {
    transform: rotate(0deg);
  }

  details[open] .arrow {
    transform: rotate(90deg);
  }

  details[open] .grid-sub-row {
    margin-top: 10px;
  }

  .chart-container {
    position: relative;
    width: 900px;
    height: 200px; 
    margin-bottom: 20px;
  }

  .q-labels {
    font-size: 16px;
    font-weight: 600;
    fill: #004253;
    text-anchor: middle;
  }

  .line {
    stroke: #004253;
    stroke-width: 2;
    fill: none;
  }

  .point {
    fill: #004253;
  }

  .value-label {
    font-size: 10px;
    fill: #333;
    font-weight: 500;
    text-anchor: middle;
    dominant-baseline: hanging;
  }
</style>
</head>
<body>

<h1>BetterBrain client example: Linda</h1>

<!-- My Health Card -->
<div class="card">
  <div class="section-header">My Health</div>
  <div class="chart-container">
    <svg width="900" height="200">
      <!-- Q labels at y=30 -->
      <text x="240" y="30" class="q-labels">Q1</text>
      <text x="320" y="30" class="q-labels">Q2</text>
      <text x="400" y="30" class="q-labels">Q3</text>
      <text x="480" y="30" class="q-labels">Q4</text>
      <text x="560" y="30" class="q-labels">Q5</text>
      <text x="640" y="30" class="q-labels">Q6</text>
      <text x="720" y="30" class="q-labels">Q7</text>
      <text x="800" y="30" class="q-labels">Q8</text>

      <!-- My Health line chart:
           min=40,max=70
           bottom=150
           42→147.33,49→138,50→136.67,56→128.67,61→122,64→118,65→116.67,67→114
      -->
      <path class="line" d="
        M240,147.33
        L320,138
        L400,136.67
        L480,128.67
        L560,122
        L640,118
        L720,116.67
        L800,114
      "></path>

      <circle cx="240" cy="147.33" r="3" class="point"/>
      <text x="240" y="147.33" class="value-label" dy="-15">42</text>

      <circle cx="320" cy="138" r="3" class="point"/>
      <text x="320" y="138" class="value-label" dy="-15">49</text>

      <circle cx="400" cy="136.67" r="3" class="point"/>
      <text x="400" y="136.67" class="value-label" dy="-15">50</text>

      <circle cx="480" cy="128.67" r="3" class="point"/>
      <text x="480" y="128.67" class="value-label" dy="-15">56</text>

      <circle cx="560" cy="122" r="3" class="point"/>
      <text x="560" y="122" class="value-label" dy="-15">61</text>

      <circle cx="640" cy="118" r="3" class="point"/>
      <text x="640" y="118" class="value-label" dy="-15">64</text>

      <circle cx="720" cy="116.67" r="3" class="point"/>
      <text x="720" y="116.67" class="value-label" dy="-15">65</text>

      <circle cx="800" cy="114" r="3" class="point"/>
      <text x="800" y="114" class="value-label" dy="-15">67</text>
    </svg>
  </div>

  <div class="category-title">Health Systems</div>
  <div class="grid-row">
    <div>Vascular</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Metabolic</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Inflammation</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle red"></div>
  </div>
  <div class="grid-row">
    <div>Non-Modifiable</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Gut Health</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Mental Health</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Toxin</div>
    <div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Cognitive Reserve</div>
    <div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Hormonal</div>
    <div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Musculoskeletal</div>
    <div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>

  <div class="category-title">Cognitive Function</div>
  <div class="grid-row">
    <div>Memory</div>
    <div class="circle yellow"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Executive function</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>

  <div class="category-title">Daily Function</div>
  <div class="grid-row">
    <div>Energy</div>
    <div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Physical function</div>
    <div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Cognitive Function</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Mood</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Concerning symptoms</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>

</div>

<!-- My Protocol Card -->
<div class="card">
  <div class="section-header">My Protocol</div>
  <div class="chart-container">
    <svg width="900" height="200">
      <text x="240" y="30" class="q-labels">Q1</text>
      <text x="320" y="30" class="q-labels">Q2</text>
      <text x="400" y="30" class="q-labels">Q3</text>
      <text x="480" y="30" class="q-labels">Q4</text>
      <text x="560" y="30" class="q-labels">Q5</text>
      <text x="640" y="30" class="q-labels">Q6</text>
      <text x="720" y="30" class="q-labels">Q7</text>
      <text x="800" y="30" class="q-labels">Q8</text>

      <!-- My Protocol line (32,56,61,57,70,74,74,78)
           min=30,max=80,range=50
           bottom=150
           32→148.4,56→129.2,61→125.2,57→128.4,70→118,74→114.8,74→114.8,78→111.6
      -->
      <path class="line" d="
        M240,148.4
        L320,129.2
        L400,125.2
        L480,128.4
        L560,118
        L640,114.8
        L720,114.8
        L800,111.6
      "></path>

      <circle cx="240" cy="148.4" r="3" class="point"/>
      <text x="240" y="148.4" class="value-label" dy="-15">32</text>

      <circle cx="320" cy="129.2" r="3" class="point"/>
      <text x="320" y="129.2" class="value-label" dy="-15">56</text>

      <circle cx="400" cy="125.2" r="3" class="point"/>
      <text x="400" y="125.2" class="value-label" dy="-15">61</text>

      <circle cx="480" cy="128.4" r="3" class="point"/>
      <text x="480" y="128.4" class="value-label" dy="-15">57</text>

      <circle cx="560" cy="118" r="3" class="point"/>
      <text x="560" y="118" class="value-label" dy="-15">70</text>

      <circle cx="640" cy="114.8" r="3" class="point"/>
      <text x="640" y="114.8" class="value-label" dy="-15">74</text>

      <circle cx="720" cy="114.8" r="3" class="point"/>
      <text x="720" y="114.8" class="value-label" dy="-15">74</text>

      <circle cx="800" cy="111.6" r="3" class="point"/>
      <text x="800" y="111.6" class="value-label" dy="-15">78</text>
    </svg>
  </div>

  <div class="category-title">Protocol</div>
  <details>
    <summary>
      <div>Sleep<span class="arrow">▶</span></div>
      <div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
    </summary>
    <div class="grid-sub-row">
      <div>> Prepare Body For Sleep</div>
      <div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
    </div>
    <div class="grid-sub-row">
      <div>> Reduce Light Exposure</div>
      <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle yellow"></div>
    </div>
    <div class="grid-sub-row">
      <div>> Maintain A Consistent Sleep Schedule</div>
      <div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div>
    </div>
    <div class="grid-sub-row">
      <div>> Optimize Sleep Environment Temperature</div>
      <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div>
    </div>
    <div class="grid-sub-row">
      <div>> Reduce Potential Nighttime Distractions</div>
      <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
    </div>
  </details>

  <div class="grid-row">
    <div>Move</div>
    <div class="circle red"></div><div class="circle red"></div><div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Supplement</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Eat</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Defend</div>
    <div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Environment</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Relate</div>
    <div class="circle red"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>
  <div class="grid-row">
    <div>Learn</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>De-stress</div>
    <div class="circle red"></div><div class="circle yellow"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Drugs</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle green"></div>
  </div>
  <div class="grid-row">
    <div>Therapy</div>
    <div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div><div class="circle yellow"></div>
  </div>

</div>

</body>
</html>
