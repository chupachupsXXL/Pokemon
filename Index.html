<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>포켓몬 랜덤 뽑기</title>
    <style>
        body { font-family: sans-serif; text-align: center; background: #f8f9fa; padding: 20px; margin: 0; }
        .card { background: white; border-radius: 12px; padding: 20px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); max-width: 400px; margin: 0 auto; }
        h1 { color: #ff5350; font-size: 22px; }
        .controls { margin: 20px 0; display: flex; flex-direction: column; gap: 12px; align-items: center; }
        label { font-size: 15px; font-weight: bold; }
        input[type="number"] { width: 60px; padding: 5px; text-align: center; font-size: 16px; }
        button { background: #ff5350; color: white; border: none; padding: 12px 24px; font-size: 16px; font-weight: bold; border-radius: 8px; width: 100%; cursor: pointer; }
        button:disabled { background: #ccc; }
        .result { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; margin-top: 20px; }
        .pokemon-item { background: #f1f3f5; padding: 10px; border-radius: 8px; text-align: center; }
        .pokemon-item img { width: 80px; height: 80px; }
        .tag { font-size: 11px; background: #ffd43b; color: #333; padding: 2px 6px; border-radius: 4px; display: inline-block; margin-top: 4px; }
    </style>
</head>
<body>

<div class="card">
    <h1>🎲 포켓몬 랜덤 뽑기</h1>
    
    <div class="controls">
        <label>
            <input type="checkbox" id="includeLegendary" checked> 전설/환상 포켓몬 포함
        </label>
        <label>
            뽑을 수: <input type="number" id="drawCount" value="4" min="1" max="10"> 마리
        </label>
        <button id="drawBtn" onclick="drawPokemon()">뽑기 시작!</button>
    </div>

    <div id="status"></div>
    <div id="result" class="result"></div>
</div>

<script>
async function drawPokemon() {
    const btn = document.getElementById('drawBtn');
    const status = document.getElementById('status');
    const resultDiv = document.getElementById('result');
    const includeLegendary = document.getElementById('includeLegendary').checked;
    const count = parseInt(document.getElementById('drawCount').value);

    btn.disabled = true;
    resultDiv.innerHTML = '';
    status.innerText = '추첨 중입니다...';

    const drawnList = [];
    const drawnIds = new Set();

    while (drawnList.length < count) {
        const randomId = Math.floor(Math.random() * 1025) + 1;
        if (drawnIds.has(randomId)) continue;

        try {
            const res = await fetch(`https://pokeapi.co/api/v2/pokemon-species/${randomId}/`);
            if (!res.ok) continue;
            const data = await res.json();

            const isLegendary = data.is_legendary || data.is_mythical;
            if (!includeLegendary && isLegendary) continue;

            const nameObj = data.names.find(n => n.language.name === 'ko');
            const name = nameObj ? nameObj.name : data.name;

            drawnIds.add(randomId);
            drawnList.push({
                id: randomId,
                name: name,
                isLegendary: isLegendary,
                sprite: `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${randomId}.png`
            });
        } catch (e) {
            console.error(e);
        }
    }

    status.innerText = '';
    resultDiv.innerHTML = drawnList.map(p => `
        <div class="pokemon-item">
            <img src="${p.sprite}" alt="${p.name}">
            <div><strong>No.${p.id}</strong></div>
            <div>${p.name}</div>
            ${p.isLegendary ? '<span class="tag">전설/환상</span>' : ''}
        </div>
    `).join('');

    btn.disabled = false;
}
</script>

</body>
</html>
