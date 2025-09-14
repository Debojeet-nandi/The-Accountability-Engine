<!-- index.html (save & open in browser) -->
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Accountability Engine - Prototype</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
<style>
  body{font-family:Inter,system-ui,Arial; background:#f5f7fb; margin:0; padding:20px;}
  .card{background:white;padding:18px;border-radius:10px;box-shadow:0 6px 18px rgba(10,20,40,0.06); max-width:900px;margin:12px auto}
  input,textarea,select{width:100%;padding:8px;margin:6px 0;border:1px solid #ddd;border-radius:6px}
  button{background:#0B72B9;color:white;border:none;padding:10px 14px;border-radius:8px;cursor:pointer}
  .small{font-size:13px;color:#555}
  .tracking{background:#eef6ff;padding:10px;border-radius:8px;margin-top:10px}
  .stars span{font-size:28px;cursor:pointer;padding:0 6px}
</style>
</head>
<body>

<div class="card">
  <h2>Accountability Engine — Prototype</h2>
  <p class="small">Submit a sample file. This prototype generates a tracking id and lets you rate after closure.</p>

  <label>Name</label><input id="name" placeholder="Your name">
  <label>Department</label>
  <select id="dept">
    <option>Municipality</option><option>Electricity</option><option>Tehsil</option>
  </select>
  <label>Short note</label><textarea id="note" rows="3" placeholder="What do you need..."></textarea>

  <button id="submitBtn">Submit File</button>

  <div id="after" style="display:none" class="tracking">
    <p><strong>Tracking ID:</strong> <span id="trackId"></span></p>
    <p class="small">Status: <span id="status">Pending</span></p>
    <button id="simulateBtn">Simulate Auto-Clear (30 days)</button>
  </div>
</div>

<!-- Rating modal area -->
<div class="card" id="ratingCard" style="display:none">
  <h3>Rate the Service</h3>
  <p class="small">Give a rating (1-5). Avg below 70% triggers a review badge.</p>
  <div class="stars" id="stars"> 
    <span data-val="1">☆</span><span data-val="2">☆</span><span data-val="3">☆</span>
    <span data-val="4">☆</span><span data-val="5">☆</span>
  </div>
  <br>
  <button id="submitRating">Submit Rating</button>
  <p id="result" class="small"></p>
</div>

<div class="card" id="publicStats">
  <h3>Public Stats (simulated)</h3>
  <p class="small">Avg rating (all): <strong id="avgRating">—</strong></p>
  <p id="reviewBadge" style="display:none;color:#b00"><strong>UNDER REVIEW: Dept average below threshold</strong></p>
</div>

<script>
  // simple localStorage-backed simulation (no backend)
  const submitBtn=document.getElementById('submitBtn');
  const after=document.getElementById('after');
  const trackIdSpan=document.getElementById('trackId');
  const statusSpan=document.getElementById('status');
  const simulateBtn=document.getElementById('simulateBtn');
  const ratingCard=document.getElementById('ratingCard');
  const stars=document.getElementById('stars');
  const submitRating=document.getElementById('submitRating');
  const avgRatingSpan=document.getElementById('avgRating');
  const reviewBadge=document.getElementById('reviewBadge');

  function genId(){return 'AE-'+Math.random().toString(36).slice(2,9).toUpperCase()}

  submitBtn.onclick=()=>{
    const id=genId();
    trackIdSpan.textContent=id;
    after.style.display='block';
    statusSpan.textContent='Pending';
    // store ticket
    localStorage.setItem('ticket_'+id, JSON.stringify({id,dept:document.getElementById('dept').value, status:'Pending'}));
  }

  simulateBtn.onclick=()=>{
    const id=trackIdSpan.textContent;
    let t=JSON.parse(localStorage.getItem('ticket_'+id));
    t.status='Closed (Auto-Approved)';
    localStorage.setItem('ticket_'+id, JSON.stringify(t));
    statusSpan.textContent=t.status;
    // open rating prompt
    ratingCard.style.display='block';
  }

  // star selection
  let selected=0;
  stars.addEventListener('click', e=>{
    if(e.target.dataset && e.target.dataset.val){
      selected=Number(e.target.dataset.val);
      [...stars.children].forEach(s=> s.textContent = (Number(s.dataset.val) <= selected ? '★' : '☆'));
    }
  });

  submitRating.onclick=()=>{
    if(!selected){ alert('Choose 1-5 stars'); return; }
    // push to dept aggregate
    const dept=document.getElementById('dept').value;
    const key='ratings_'+dept;
    const arr= JSON.parse(localStorage.getItem(key) || '[]');
    arr.push(selected);
    localStorage.setItem(key, JSON.stringify(arr));
    updateStats();
    ratingCard.style.display='none';
    alert('Thanks! Your rating saved (simulated).');
  }

  function updateStats(){
    const dept='Municipality'; // for demo you can compute across all depts
    const keys=Object.keys(localStorage).filter(k=>k.startsWith('ratings_'));
    let all=[];
    keys.forEach(k=> all=all.concat(JSON.parse(localStorage.getItem(k))));
    if(all.length===0){ avgRatingSpan.textContent='—'; return; }
    const avg = (all.reduce((a,b)=>a+b,0) / all.length);
    avgRatingSpan.textContent=avg.toFixed(2)+' / 5';
    // threshold: 70% of 5 is 3.5
    if(avg < 3.5) reviewBadge.style.display='block'; else reviewBadge.style.display='none';
  }

  updateStats();
</script>

</body>
</html>