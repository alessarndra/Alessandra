---
layout: default
title: Research
permalink: /research/
---

<div class="container">
  <h2>Selected research</h2>
  <p class="lead">Plain-language summaries; contact me for protocols or code.</p>

  <div class="cards-3">
    <div class="card proj">
      <h3>Photoprotective proteins in early-diverging chlorophytes</h3>
      <p class="meta">Kromdijk Group · Cambridge Plant Sciences</p>
      <ul>
        <li>Functional diversity of <strong>PsbS</strong> homologues and their role in <em>NPQ</em> under fluctuating light.</li>
        <li>Chlorophyll fluorescence, qPCR, protein modelling, R/Python.</li>
        <li>Variation in photoprotective capacity → implications for crop light-use efficiency.</li>
      </ul>
    </div>

    <div class="card proj">
      <h3>Behavioural ecology of Damaraland mole-rats</h3>
      <p class="meta">Kuruman River Reserve (with Prof. Tim Clutton-Brock)</p>
      <ul>
        <li>Observed social structure & cooperative behaviour; added to long-term dataset.</li>
        <li>Division of labour follows energetic constraints in cooperative breeders.</li>
      </ul>
    </div>

    <div class="card proj">
      <h3>Leaf-trapping fungi in Borneo forests</h3>
      <p class="meta">Danum Valley Field Centre, Sabah</p>
      <ul>
        <li>Canopy surveys in logged vs primary forest; ImageJ quantification; R stats.</li>
        <li>Higher prevalence in disturbed areas; arthropod microhabitats supported.</li>
      </ul>
    </div>
  </div>

  <div class="cards-2" style="margin-top:16px">
    <div class="card proj">
      <h3>Critical review: what do we mean by “ecosystem health”?</h3>
      <p>Context-specific, multi-metric framing rather than a single index; clearer definitions improve policy relevance.</p>
    </div>

    <div class="card proj">
      <h3>Soil microbiome (PhD preview)</h3>
      <p>Long-read workflows (Oxford Nanopore) for community profiling and linking compositional shifts to soil function, with reproducible analysis.</p>
    </div>
  </div>

  <h3 style="margin-top:26px">Field sites map</h3>
  <div id="field-map"></div>

  <h3 style="margin-top:26px">Example data snapshot</h3>
  <div class="chart-wrap">
    <canvas id="psbsChart" height="120"></canvas>
  </div>
</div>

<script>
// --- Leaflet map (edit coordinates or add more markers) ---
document.addEventListener('DOMContentLoaded', function(){
  if(typeof L !== 'undefined'){
    const map = L.map('field-map',{scrollWheelZoom:false}).setView([10.5, 78], 5);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution:'&copy; OpenStreetMap'
    }).addTo(map);

    const sites = [
      {name:'Danum Valley, Borneo (DVFC)', coords:[5.025,117.743], note:'Leaf-trapping fungi / canopy surveys'},
      {name:'Kuruman River Reserve, Kalahari', coords:[-26.983,21.833], note:'Damaraland mole-rats'},
      {name:'Cambridge, UK', coords:[52.205,0.119], note:'Photoprotection & PsbS'},
    ];
    sites.forEach(s=>{
      L.marker(s.coords).addTo(map).bindPopup(`<b>${s.name}</b><br>${s.note}`);
    });
  }

  // --- Chart.js demo (replace labels/data with your results) ---
  const ctx = document.getElementById('psbsChart');
  if(ctx && typeof Chart !== 'undefined'){
    new Chart(ctx,{
      type:'bar',
      data:{
        labels:['PsbS-A','PsbS-B','PsbS-C','PsbS-D'],
        datasets:[{
          label:'Relative NPQ capacity',
          data:[0.8,1.0,0.65,0.9],  // <— replace with your values
        }]
      },
      options:{
        responsive:true,
        plugins:{legend:{display:false}},
        scales:{y:{beginAtZero:true,max:1.2}}
      }
    });
  }
});
</script>
