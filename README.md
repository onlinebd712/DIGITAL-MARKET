<script>
  // Sample data - replace with real data only through official APIs or user input.
  const sampleMatches = [
    {id:1,mode:"BR Classic",result:"Winner",kd:"6/2",date:"2025-10-28"},
    {id:2,mode:"Clash Squad",result:"Top 3",kd:"4/3",date:"2025-10-27"},
    {id:3,mode:"BR Classic",result:"Top 10",kd:"3/2",date:"2025-10-25"},
    {id:4,mode:"BR Classic",result:"Winner",kd:"8/1",date:"2025-10-23"}
  ];
  const leaderboardSample = [
    {rank:1,player:"AcePlayer",score:25830},
    {rank:2,player:"Ratul",score:24540},
    {rank:3,player:"Shadow",score:23820},
    {rank:4,player:"Nova",score:22770}
  ];

  function populate(){
    const recent = document.getElementById('recentMatches');
    recent.innerHTML = sampleMatches.map((m,i)=><tr><td>#${m.id}</td><td>${m.mode}</td><td>${m.result} (${m.kd})</td><td class="muted">${m.date}</td></tr>).join('');
    document.getElementById('matchList').innerHTML = sampleMatches.map((m,i)=><tr><td>${i+1}</td><td>${m.mode}</td><td>${m.kd}</td><td class="muted">${m.date}</td></tr>).join('');
    document.getElementById('leaderboard').innerHTML = leaderboardSample.map(l=><tr><td>${l.rank}</td><td>${l.player}</td><td>${l.score}</td></tr>).join('');
  }
  populate();

  function showTab(name){
    // hide all
    ['overview','matches','leader','tips','settings'].forEach(n=>{
      const el = document.getElementById(n + 'Tab');
      if(el) el.style.display = (n===name?'block':'none');
    });
  }

  function saveName(){
    const v = document.getElementById('inpName').value.trim();
    if(!v){ alert('নাম লিখো'); return; }
    document.getElementById('playerName').textContent = v;
    document.getElementById('avatar').textContent = v.charAt(0).toUpperCase();
    alert('নাম আপডেট হয়েছে (লোকালি)');
  }

  // default show
  showTab('overview');
</script>
</body>
</html>
