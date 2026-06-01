<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0"/>
<meta name="apple-mobile-web-app-capable" content="yes"/>
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent"/>
<title>Monitor Energético</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0a0f;
    --surface: #13131a;
    --surface2: #1c1c26;
    --border: rgba(255,255,255,0.07);
    --text: #f0f0f8;
    --muted: rgba(240,240,248,0.4);
    --hint: rgba(240,240,248,0.2);
    --volt-color: #5b8def;
    --curr-color: #3dd9a4;
    --pot-color: #f06a3a;
    --energ-color: #e0a93b;
    --normal: #3dd9a4;
    --alerta: #e0a93b;
    --critico: #f06a3a;
    --accent: #5b8def;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }
  html, body { height: 100%; background: var(--bg); font-family: 'Syne', sans-serif; color: var(--text); overscroll-behavior: none; }

  .app { max-width: 430px; margin: 0 auto; min-height: 100vh; padding: 0 0 2rem; }

  /* HEADER */
  .topbar {
    display: flex; align-items: center; justify-content: space-between;
    padding: 3rem 1.25rem 1rem;
    border-bottom: 1px solid var(--border);
    position: sticky; top: 0; background: var(--bg); z-index: 10;
  }
  .topbar-left { display: flex; flex-direction: column; gap: 2px; }
  .topbar-title { font-size: 18px; font-weight: 800; letter-spacing: -0.5px; }
  .topbar-sub { font-size: 11px; color: var(--muted); font-family: 'DM Mono', monospace; font-weight: 300; }
  .status-pill {
    font-size: 11px; font-weight: 600; padding: 4px 12px;
    border-radius: 999px; letter-spacing: 0.5px;
    text-transform: uppercase; display: flex; align-items: center; gap: 5px;
  }
  .pill-dot { width: 6px; height: 6px; border-radius: 50%; }
  .status-normal  { background: rgba(61,217,164,0.12); color: var(--normal); }
  .status-normal .pill-dot { background: var(--normal); animation: pulse-g 2s infinite; }
  .status-alerta  { background: rgba(224,169,59,0.12); color: var(--alerta); }
  .status-alerta .pill-dot { background: var(--alerta); animation: pulse-a 1.5s infinite; }
  .status-critico { background: rgba(240,106,58,0.12); color: var(--critico); }
  .status-critico .pill-dot { background: var(--critico); animation: pulse-r 1s infinite; }

  @keyframes pulse-g { 0%,100%{opacity:1} 50%{opacity:.3} }
  @keyframes pulse-a { 0%,100%{opacity:1} 50%{opacity:.3} }
  @keyframes pulse-r { 0%,100%{opacity:1} 50%{opacity:.2} }

  /* CONFIG */
  .config-panel {
    margin: 1rem 1.25rem 0;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
  }
  .config-toggle {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 16px; cursor: pointer; user-select: none;
  }
  .config-toggle-label { font-size: 12px; color: var(--muted); font-weight: 600; letter-spacing: 0.5px; text-transform: uppercase; }
  .config-arrow { color: var(--muted); font-size: 18px; transition: transform 0.2s; }
  .config-arrow.open { transform: rotate(180deg); }
  .config-fields { display: none; padding: 0 16px 16px; flex-direction: column; gap: 8px; }
  .config-fields.open { display: flex; }
  .cfg-label { font-size: 11px; color: var(--muted); font-family: 'DM Mono', monospace; margin-bottom: 2px; }
  .cfg-input {
    width: 100%; background: var(--surface2); border: 1px solid var(--border);
    border-radius: 10px; padding: 10px 12px; font-size: 13px; font-family: 'DM Mono', monospace;
    color: var(--text); outline: none; transition: border-color 0.2s;
  }
  .cfg-input:focus { border-color: var(--accent); }
  .cfg-input::placeholder { color: var(--hint); }
  .cfg-btn {
    width: 100%; background: var(--accent); border: none; border-radius: 10px;
    padding: 11px; font-size: 13px; font-family: 'Syne', sans-serif; font-weight: 700;
    color: #fff; cursor: pointer; transition: opacity 0.2s; margin-top: 4px;
    letter-spacing: 0.3px;
  }
  .cfg-btn:active { opacity: 0.7; }
  .api-help { font-size: 11px; color: var(--hint); font-family: 'DM Mono', monospace; }
  .api-help a { color: var(--volt-color); text-decoration: none; }

  /* METRICS */
  .metrics { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; padding: 1rem 1.25rem 0; }
  .metric-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 16px;
    position: relative;
    overflow: hidden;
  }
  .metric-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    border-radius: 16px 16px 0 0;
  }
  .card-volt::before  { background: var(--volt-color); }
  .card-curr::before  { background: var(--curr-color); }
  .card-pot::before   { background: var(--pot-color); }
  .card-energ::before { background: var(--energ-color); }

  .m-label {
    font-size: 10px; font-weight: 600; letter-spacing: 0.8px; text-transform: uppercase;
    color: var(--muted); margin-bottom: 6px; display: flex; align-items: center; gap: 4px;
  }
  .m-icon { width: 8px; height: 8px; border-radius: 50%; }
  .icon-volt  { background: var(--volt-color); }
  .icon-curr  { background: var(--curr-color); }
  .icon-pot   { background: var(--pot-color); }
  .icon-energ { background: var(--energ-color); }

  .m-value { font-size: 28px; font-weight: 800; letter-spacing: -1px; line-height: 1; }
  .m-unit  { font-size: 13px; font-weight: 400; color: var(--muted); margin-left: 2px; }
  .m-bar-bg { background: rgba(255,255,255,0.06); border-radius: 99px; height: 3px; margin-top: 10px; overflow: hidden; }
  .m-bar-fill { height: 100%; border-radius: 99px; transition: width 0.8s cubic-bezier(0.4,0,0.2,1); }
  .bar-volt  { background: var(--volt-color); }
  .bar-curr  { background: var(--curr-color); }
  .bar-pot   { background: var(--pot-color); }
  .bar-energ { background: var(--energ-color); }

  /* CHART */
  .chart-card {
    margin: 10px 1.25rem 0;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 16px;
  }
  .chart-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
  .chart-title { font-size: 11px; font-weight: 600; letter-spacing: 0.8px; text-transform: uppercase; color: var(--muted); }
  .chart-legend { display: flex; gap: 12px; }
  .legend-item { display: flex; align-items: center; gap: 5px; font-size: 10px; color: var(--muted); font-family: 'DM Mono', monospace; }
  .legend-dot { width: 6px; height: 6px; border-radius: 50%; }
  .chart-wrap { position: relative; width: 100%; height: 140px; }

  /* INFO ROW */
  .info-row {
    margin: 10px 1.25rem 0;
    display: grid; grid-template-columns: 1fr 1fr 1fr;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
  }
  .info-cell {
    padding: 14px 12px;
    text-align: center;
    border-right: 1px solid var(--border);
  }
  .info-cell:last-child { border-right: none; }
  .info-lbl { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.6px; margin-bottom: 4px; }
  .info-val { font-size: 15px; font-weight: 700; font-family: 'DM Mono', monospace; }

  /* FOOTER */
  .footer {
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 1.25rem 0;
  }
  .ts-label { font-size: 11px; color: var(--hint); font-family: 'DM Mono', monospace; }
  .refresh-indicator { display: flex; align-items: center; gap: 6px; font-size: 11px; color: var(--muted); font-family: 'DM Mono', monospace; }
  .ri-bar-bg { width: 60px; height: 3px; background: rgba(255,255,255,0.08); border-radius: 99px; overflow: hidden; }
  .ri-bar-fill { height: 100%; background: var(--accent); border-radius: 99px; width: 100%; transition: width linear; }

  /* ERROR */
  .err-msg { font-size: 12px; color: var(--critico); font-family: 'DM Mono', monospace; padding: 0.75rem 1.25rem; }

  /* LOADING OVERLAY */
  #loadingOverlay {
    position: fixed; inset: 0; background: var(--bg);
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 16px;
    z-index: 100;
  }
  .lo-title { font-size: 22px; font-weight: 800; }
  .lo-sub { font-size: 13px; color: var(--muted); font-family: 'DM Mono', monospace; }
  .lo-dots { display: flex; gap: 8px; }
  .lo-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--accent); animation: ldot 1.2s infinite; }
  .lo-dot:nth-child(2) { animation-delay: 0.2s; }
  .lo-dot:nth-child(3) { animation-delay: 0.4s; }
  @keyframes ldot { 0%,80%,100%{opacity:0.2;transform:scale(0.8)} 40%{opacity:1;transform:scale(1)} }

  /* COST CARD */
  .cost-card {
    margin: 10px 1.25rem 0;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
  }
  .cost-header {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 16px 10px;
    border-bottom: 1px solid var(--border);
  }
  .cost-header-left { display: flex; flex-direction: column; gap: 2px; }
  .cost-title { font-size: 11px; font-weight: 600; letter-spacing: 0.8px; text-transform: uppercase; color: var(--muted); }
  .cost-tariff-badge { font-size: 10px; color: var(--hint); font-family: 'DM Mono', monospace; }
  .cost-tariff-selector { display: flex; gap: 4px; }
  .tariff-btn {
    font-size: 10px; padding: 3px 8px; border-radius: 999px; cursor: pointer;
    border: 1px solid var(--border); background: transparent; color: var(--muted);
    font-family: 'DM Mono', monospace; transition: all 0.15s;
  }
  .tariff-btn.active { background: rgba(91,141,239,0.15); border-color: var(--accent); color: var(--accent); }
  .cost-grid { display: grid; grid-template-columns: 1fr 1fr; }
  .cost-cell {
    padding: 14px 16px;
    border-right: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }
  .cost-cell:nth-child(2), .cost-cell:nth-child(4) { border-right: none; }
  .cost-cell:nth-child(3), .cost-cell:nth-child(4) { border-bottom: none; }
  .cost-lbl { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.6px; margin-bottom: 5px; }
  .cost-val { font-size: 20px; font-weight: 800; letter-spacing: -0.5px; color: var(--text); }
  .cost-val.big { font-size: 24px; }
  .cost-unit { font-size: 11px; font-weight: 400; color: var(--muted); margin-left: 2px; }
  .cost-rate-row {
    padding: 10px 16px;
    border-top: 1px solid var(--border);
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 6px;
  }
  .rate-item { font-size: 10px; color: var(--hint); font-family: 'DM Mono', monospace; }
  .rate-item span { color: var(--muted); }
</style>
</head>
<body>

<div id="loadingOverlay">
  <div class="lo-title">Monitor Energético</div>
  <div class="lo-sub">iniciando...</div>
  <div class="lo-dots">
    <div class="lo-dot"></div>
    <div class="lo-dot"></div>
    <div class="lo-dot"></div>
  </div>
</div>

<div class="app">
  <div class="topbar">
    <div class="topbar-left">
      <div class="topbar-title">Monitor Energético</div>
      <div class="topbar-sub" id="topSub">—</div>
    </div>
    <div id="statusPill" class="status-pill status-normal">
      <div class="pill-dot"></div>
      <span id="statusText">Normal</span>
    </div>
  </div>

  <!-- CONFIG PANEL -->
  <div class="config-panel">
    <div class="config-toggle" onclick="toggleConfig()">
      <span class="config-toggle-label">⚙ Configuración</span>
      <span class="config-arrow" id="cfgArrow">▾</span>
    </div>
    <div class="config-fields" id="cfgFields">
      <div>
        <div class="cfg-label">ID del Google Sheet</div>
        <input class="cfg-input" id="sheetId" value="1XVFXpZZWyT_KLGFED71ZLCApSdcaB6lUGnRGgEtzuG8" placeholder="ID del Sheet"/>
      </div>
      <div>
        <div class="cfg-label">API Key de Google Sheets</div>
        <input class="cfg-input" id="apiKey" type="password" placeholder="AIza..."/>
        <div class="api-help" style="margin-top:6px;">
          Obtén tu key en <a href="https://console.cloud.google.com/apis/credentials" target="_blank">console.cloud.google.com</a>
        </div>
      </div>
      <button class="cfg-btn" onclick="applyConfig()">Conectar y monitorear</button>
    </div>
  </div>

  <div id="errMsg" class="err-msg" style="display:none;"></div>

  <!-- METRICS -->
  <div class="metrics">
    <div class="metric-card card-volt">
      <div class="m-label"><span class="m-icon icon-volt"></span>Voltaje</div>
      <div><span class="m-value" id="voltVal">—</span><span class="m-unit">V</span></div>
      <div class="m-bar-bg"><div class="m-bar-fill bar-volt" id="voltBar" style="width:0%"></div></div>
    </div>
    <div class="metric-card card-curr">
      <div class="m-label"><span class="m-icon icon-curr"></span>Corriente</div>
      <div><span class="m-value" id="corrVal">—</span><span class="m-unit">A</span></div>
      <div class="m-bar-bg"><div class="m-bar-fill bar-curr" id="corrBar" style="width:0%"></div></div>
    </div>
    <div class="metric-card card-pot">
      <div class="m-label"><span class="m-icon icon-pot"></span>Potencia</div>
      <div><span class="m-value" id="potVal">—</span><span class="m-unit">W</span></div>
      <div class="m-bar-bg"><div class="m-bar-fill bar-pot" id="potBar" style="width:0%"></div></div>
    </div>
    <div class="metric-card card-energ">
      <div class="m-label"><span class="m-icon icon-energ"></span>Energía</div>
      <div><span class="m-value" id="energVal">—</span><span class="m-unit">Wh</span></div>
      <div class="m-bar-bg"><div class="m-bar-fill bar-energ" id="energBar" style="width:0%"></div></div>
    </div>
  </div>

  <!-- CHART -->
  <div class="chart-card">
    <div class="chart-header">
      <div class="chart-title">Historial de potencia</div>
      <div class="chart-legend">
        <div class="legend-item"><div class="legend-dot" style="background:var(--pot-color)"></div>Potencia (W)</div>
        <div class="legend-item"><div class="legend-dot" style="background:var(--volt-color)"></div>Voltaje (V/10)</div>
      </div>
    </div>
    <div class="chart-wrap">
      <canvas id="histChart" role="img" aria-label="Gráfico de historial de potencia y voltaje"></canvas>
    </div>
  </div>

  <!-- INFO ROW -->
  <div class="info-row">
    <div class="info-cell">
      <div class="info-lbl">Límite V</div>
      <div class="info-val" id="limiteVal">—</div>
    </div>
    <div class="info-cell">
      <div class="info-lbl">V. Restante</div>
      <div class="info-val" id="restanteVal">—</div>
    </div>
    <div class="info-cell">
      <div class="info-lbl">kWh total</div>
      <div class="info-val" id="kwHTotal">—</div>
    </div>
  </div>

  <!-- COST CARD -->
  <div class="cost-card">
    <div class="cost-header">
      <div class="cost-header-left">
        <div class="cost-title">💸 Costo eléctrico</div>
        <div class="cost-tariff-badge" id="tariffLabel">Enel BT1 Santiago · con IVA</div>
      </div>
      <div class="cost-tariff-selector">
        <button class="tariff-btn active" onclick="setTariff('BT1_T1')" id="btn_BT1_T1">T1</button>
        <button class="tariff-btn" onclick="setTariff('BT1_T2')" id="btn_BT1_T2">T2</button>
        <button class="tariff-btn" onclick="setTariff('BT1_T3')" id="btn_BT1_T3">T3</button>
      </div>
    </div>
    <div class="cost-grid">
      <div class="cost-cell">
        <div class="cost-lbl">Costo instantáneo</div>
        <div><span class="cost-val" id="costInstant">—</span><span class="cost-unit">$/h</span></div>
      </div>
      <div class="cost-cell">
        <div class="cost-lbl">Sesión acumulada</div>
        <div><span class="cost-val" id="costSession">—</span><span class="cost-unit">CLP</span></div>
      </div>
      <div class="cost-cell">
        <div class="cost-lbl">Proyección diaria</div>
        <div><span class="cost-val" id="costDay">—</span><span class="cost-unit">$/día</span></div>
      </div>
      <div class="cost-cell">
        <div class="cost-lbl">Proyección mensual</div>
        <div><span class="cost-val big" id="costMonth">—</span><span class="cost-unit">$/mes</span></div>
      </div>
    </div>
    <div class="cost-rate-row">
      <div class="rate-item">Cargo energía: <span id="rateEnerg">—</span> $/kWh</div>
      <div class="rate-item">Transporte: <span id="rateTrans">—</span> $/kWh</div>
      <div class="rate-item">Cargo fijo: <span id="rateFixed">—</span> $/mes</div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="ts-label" id="tsLabel">última lectura: —</div>
    <div class="refresh-indicator">
      <div class="ri-bar-bg"><div class="ri-bar-fill" id="riFill"></div></div>
      <span id="riCount">5s</span>
    </div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<script>
  const REFRESH_INTERVAL = 5000;
  let histChart = null;
  let allRows = [];
  let refreshTimer = null;
  let countdownTimer = null;
  let countdown = 5;
  let configOpen = false;
  let currentTariff = 'BT1_T1';

  // Tarifas oficiales Enel Santiago - BT1 residencial con IVA (marzo 2026)
  // Fuente: Enel Distribución Chile S.A., Decreto 24T VAD 5T
  // cargo_energia + transporte + potencia + servicio_publico ($/kWh, con IVA)
  // cargo_fijo mensual ($/mes, con IVA)
  const TARIFAS = {
    BT1_T1: {
      label: 'BT1 T1 (0–150 kWh)',
      energia:    155.94,   // cargo por energía $/kWh c/IVA
      transporte:  15.96,   // transporte $/kWh c/IVA
      potencia:    22.86,   // cargo potencia BT_AA T1 $/kWh c/IVA
      servicio:     0.855,  // cargo servicio público $/kWh (exento IVA)
      fijo_mes:   709.54,   // cargo fijo mensual $/mes c/IVA
    },
    BT1_T2: {
      label: 'BT1 T2 (151–300 kWh)',
      energia:    155.94,
      transporte:  15.96,
      potencia:    23.81,   // BT_AA T2
      servicio:     0.855,
      fijo_mes:   709.54,
    },
    BT1_T3: {
      label: 'BT1 T3 (301–500 kWh)',
      energia:    155.94,
      transporte:  15.96,
      potencia:    24.75,   // BT_AA T3
      servicio:     0.855,
      fijo_mes:   709.54,
    },
  };

  function setTariff(id) {
    currentTariff = id;
    document.querySelectorAll('.tariff-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('btn_' + id).classList.add('active');
    if (allRows.length) renderCost(allRows);
  }

  function calcCostPerKwh(tariff) {
    return tariff.energia + tariff.transporte + tariff.potencia + tariff.servicio;
  }

  function renderCost(rows) {
    const tariff = TARIFAS[currentTariff];
    const rateKwh = calcCostPerKwh(tariff);

    const last = rows[rows.length - 1];
    const pot   = parseFloat(last[3]) || 0;   // W
    const energ = parseFloat(last[4]) || 0;   // Wh acumulado

    // Costo instantáneo = potencia actual × tarifa por hora
    const costInstant = (pot / 1000) * rateKwh;

    // Costo sesión = energía acumulada en kWh × tarifa
    const costSession = (energ / 1000) * rateKwh;

    // Proyección diaria (asume mismo consumo 24h)
    const costDay = costInstant * 24;

    // Proyección mensual = días × 30 + cargo fijo
    const costMonth = costDay * 30 + tariff.fijo_mes;

    document.getElementById('costInstant').textContent = Math.round(costInstant).toLocaleString('es-CL');
    document.getElementById('costSession').textContent = Math.round(costSession).toLocaleString('es-CL');
    document.getElementById('costDay').textContent     = Math.round(costDay).toLocaleString('es-CL');
    document.getElementById('costMonth').textContent   = Math.round(costMonth).toLocaleString('es-CL');
    document.getElementById('tariffLabel').textContent = 'Enel BT1 Santiago · ' + tariff.label;
    document.getElementById('rateEnerg').textContent   = tariff.energia.toFixed(2);
    document.getElementById('rateTrans').textContent   = tariff.transporte.toFixed(2);
    document.getElementById('rateFixed').textContent   = Math.round(tariff.fijo_mes).toLocaleString('es-CL');
  }

  const DEMO_ROWS = [
    ['2026-05-27 10:00:00','220','1.45','319.00','0.88','Normal','240','20'],
    ['2026-05-27 10:00:05','221','1.46','322.66','0.97','Normal','240','19'],
    ['2026-05-27 10:00:10','219','1.44','315.36','1.06','Normal','240','21'],
    ['2026-05-27 10:00:15','222','1.47','326.34','1.15','Normal','240','18'],
    ['2026-05-27 10:00:20','220','1.45','319.00','1.24','Normal','240','20'],
  ];

  function toggleConfig() {
    configOpen = !configOpen;
    document.getElementById('cfgFields').classList.toggle('open', configOpen);
    document.getElementById('cfgArrow').classList.toggle('open', configOpen);
  }

  function applyConfig() {
    toggleConfig();
    fetchData();
  }

  function getConfig() {
    return {
      sheetId: document.getElementById('sheetId').value.trim(),
      apiKey: document.getElementById('apiKey').value.trim()
    };
  }

  async function fetchData() {
    const { sheetId, apiKey } = getConfig();
    const errEl = document.getElementById('errMsg');

    if (!apiKey) {
      errEl.style.display = 'block';
      errEl.textContent = 'Sin API Key — mostrando datos de ejemplo. Ingresa tu API Key en Configuración.';
      renderDashboard(DEMO_ROWS);
      return;
    }

    try {
      const url = `https://sheets.googleapis.com/v4/spreadsheets/${sheetId}/values/A:H?key=${apiKey}`;
      const res = await fetch(url);
      const data = await res.json();
      if (data.error) throw new Error(data.error.message);
      const rows = (data.values || []).slice(1);
      if (!rows.length) throw new Error('Sheet sin datos');
      allRows = rows;
      errEl.style.display = 'none';
      renderDashboard(allRows);
    } catch (e) {
      errEl.style.display = 'block';
      errEl.textContent = 'Error: ' + e.message;
      renderDashboard(allRows.length ? allRows : DEMO_ROWS);
    }
  }

  function renderDashboard(rows) {
    document.getElementById('loadingOverlay').style.display = 'none';

    const last = rows[rows.length - 1];
    const volt   = parseFloat(last[1]) || 0;
    const corr   = parseFloat(last[2]) || 0;
    const pot    = parseFloat(last[3]) || 0;
    const energ  = parseFloat(last[4]) || 0;
    const estado = last[5] || 'Normal';
    const limV   = parseFloat(last[6]) || 240;
    const voltR  = parseFloat(last[7]) || 0;
    const ts     = last[0] || '';

    document.getElementById('voltVal').textContent   = volt.toFixed(0);
    document.getElementById('corrVal').textContent   = corr.toFixed(2);
    document.getElementById('potVal').textContent    = pot.toFixed(0);
    document.getElementById('energVal').textContent  = energ.toFixed(2);
    document.getElementById('limiteVal').textContent = limV + ' V';
    document.getElementById('restanteVal').textContent = voltR + ' V';
    document.getElementById('kwHTotal').textContent  = (energ / 1000).toFixed(4);
    document.getElementById('tsLabel').textContent   = 'última lectura: ' + ts.split(' ')[1];
    document.getElementById('topSub').textContent    = ts;

    document.getElementById('voltBar').style.width  = Math.min(100, (volt / limV) * 100).toFixed(1) + '%';
    document.getElementById('corrBar').style.width  = Math.min(100, (corr / 30)   * 100).toFixed(1) + '%';
    document.getElementById('potBar').style.width   = Math.min(100, (pot  / 5000) * 100).toFixed(1) + '%';
    document.getElementById('energBar').style.width = Math.min(100, (energ / 10)  * 100).toFixed(1) + '%';

    const pill = document.getElementById('statusPill');
    pill.className = 'status-pill';
    if (estado === 'Normal')  pill.classList.add('status-normal');
    else if (estado === 'Alerta') pill.classList.add('status-alerta');
    else pill.classList.add('status-critico');
    document.getElementById('statusText').textContent = estado;

    renderCost(rows);

    const labels   = rows.map((r, i) => r[0] ? r[0].split(' ')[1] || ('L'+(i+1)) : ('L'+(i+1)));
    const potData  = rows.map(r => parseFloat(r[3]) || 0);
    const voltData = rows.map(r => (parseFloat(r[1]) || 0) / 10);

    if (histChart) histChart.destroy();
    const ctx = document.getElementById('histChart').getContext('2d');
    histChart = new Chart(ctx, {
      type: 'line',
      data: {
        labels,
        datasets: [
          {
            label: 'Potencia (W)',
            data: potData,
            borderColor: '#f06a3a',
            backgroundColor: 'rgba(240,106,58,0.08)',
            borderWidth: 2, pointRadius: 3, tension: 0.4, fill: true,
            borderDash: []
          },
          {
            label: 'Voltaje /10',
            data: voltData,
            borderColor: '#5b8def',
            backgroundColor: 'transparent',
            borderWidth: 1.5, pointRadius: 2, tension: 0.4, fill: false,
            borderDash: [4, 3]
          }
        ]
      },
      options: {
        responsive: true, maintainAspectRatio: false,
        plugins: { legend: { display: false } },
        scales: {
          x: {
            ticks: { color: 'rgba(240,240,248,0.3)', font: { size: 9, family: 'DM Mono' }, autoSkip: true, maxTicksLimit: 5 },
            grid: { display: false }, border: { display: false }
          },
          y: {
            ticks: { color: 'rgba(240,240,248,0.3)', font: { size: 9, family: 'DM Mono' } },
            grid: { color: 'rgba(255,255,255,0.04)' }, border: { display: false }
          }
        }
      }
    });
  }

  function startCountdown() {
    countdown = REFRESH_INTERVAL / 1000;
    if (countdownTimer) clearInterval(countdownTimer);
    updateCountdownUI();
    countdownTimer = setInterval(() => {
      countdown--;
      if (countdown < 0) countdown = REFRESH_INTERVAL / 1000;
      updateCountdownUI();
    }, 1000);
  }

  function updateCountdownUI() {
    document.getElementById('riCount').textContent = countdown + 's';
    const pct = (countdown / (REFRESH_INTERVAL / 1000)) * 100;
    const fill = document.getElementById('riFill');
    fill.style.transition = 'none';
    fill.style.width = pct + '%';
  }

  function startRefresh() {
    fetchData();
    startCountdown();
    if (refreshTimer) clearInterval(refreshTimer);
    refreshTimer = setInterval(() => {
      fetchData();
      startCountdown();
    }, REFRESH_INTERVAL);
  }

  window.addEventListener('load', () => {
    setTimeout(() => startRefresh(), 500);
  });
</script>
</body>
</html>
