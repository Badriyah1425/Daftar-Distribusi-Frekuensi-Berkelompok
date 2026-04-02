# Daftar-Distribusi-Frekuensi-Berkelompok
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Media Pembelajaran — Distribusi Frekuensi Kelompok</title>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: system-ui, sans-serif; background: #eaf6f6; color: #1a2e2e; min-height: 100vh; }

/* ── Header ── */
.header {
  background: linear-gradient(135deg, #0e7c7b 0%, #17a5a3 60%, #1dd3c8 100%);
  padding: 1.5rem 2rem;
  color: #fff;
  display: flex; align-items: center; gap: 16px;
}
.header-icon {
  width: 50px; height: 50px; background: rgba(255,255,255,0.2);
  border-radius: 14px; display: flex; align-items: center;
  justify-content: center; font-size: 26px; flex-shrink: 0;
}
.header-title { font-size: 18px; font-weight: 700; letter-spacing: -0.01em; }
.header-sub { font-size: 12px; opacity: 0.8; margin-top: 3px; }

/* ── Container ── */
.container { max-width: 900px; margin: 0 auto; padding: 1.5rem; }

/* ── Card ── */
.card {
  background: #fff;
  border: 1px solid #b2e0df;
  border-radius: 14px;
  padding: 1.5rem;
  margin-bottom: 1.25rem;
  box-shadow: 0 2px 8px rgba(14,124,123,0.06);
}
.card-title {
  font-size: 11px; font-weight: 700; color: #0e7c7b;
  letter-spacing: 0.08em; text-transform: uppercase;
  margin-bottom: 1rem;
  display: flex; align-items: center; gap: 8px;
}
.card-title::before {
  content: ''; display: inline-block;
  width: 4px; height: 16px;
  background: #17a5a3; border-radius: 2px;
}

/* ── Preset ── */
.preset-label { font-size: 12px; color: #5a8f8f; margin-bottom: 6px; }
.preset-row { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 1rem; }
.preset-btn {
  font-size: 12px; padding: 6px 13px;
  border: 1px solid #a0d8d8; border-radius: 20px;
  background: #eaf6f6; cursor: pointer; color: #0e7c7b;
  font-weight: 500; transition: all 0.15s;
}
.preset-btn:hover { background: #0e7c7b; color: #fff; border-color: #0e7c7b; }

/* ── Input data chips ── */
.input-row { display: flex; gap: 8px; align-items: center; margin-bottom: 10px; flex-wrap: wrap; }
.input-row input[type=number] {
  padding: 7px 12px; border: 1px solid #b2e0df; border-radius: 8px;
  font-size: 13px; width: 110px; outline: none; background: #f5fdfd;
}
.input-row input[type=number]:focus { border-color: #17a5a3; background: #fff; }
.data-grid { display: flex; flex-wrap: wrap; gap: 5px; margin-bottom: 6px; min-height: 30px; }
.chip {
  background: #dff4f4; border: 1px solid #a0d8d8;
  border-radius: 20px; padding: 3px 11px;
  font-size: 12px; font-weight: 600; color: #0e7c7b;
  cursor: pointer; transition: all 0.15s;
}
.chip:hover { background: #ffe0e0; border-color: #f09595; color: #A32D2D; }
.data-hint { font-size: 11px; color: #aaa; }

/* ── Buttons ── */
.btn {
  padding: 7px 16px; border: 1px solid #b2e0df; border-radius: 8px;
  font-size: 13px; cursor: pointer; background: #fff; color: #0e7c7b;
  font-weight: 500; transition: all 0.15s;
}
.btn:hover { background: #eaf6f6; }
.btn-primary {
  background: linear-gradient(135deg, #0e7c7b, #17a5a3);
  color: #fff; border: none; padding: 9px 24px;
  font-size: 14px; border-radius: 9px; font-weight: 600;
  box-shadow: 0 3px 10px rgba(14,124,123,0.25);
  transition: all 0.15s;
}
.btn-primary:hover { background: linear-gradient(135deg, #085857, #0e7c7b); box-shadow: 0 4px 14px rgba(14,124,123,0.35); }
.btn-danger { border-color: #f09595; color: #A32D2D; }
.btn-danger:hover { background: #fcebeb; }
.btn-sm { padding: 5px 12px; font-size: 12px; }

/* ── Steps ── */
.steps-wrapper { display: flex; flex-direction: column; gap: 1rem; }
.step-card {
  border: 1px solid #b2e0df; border-radius: 12px; overflow: hidden;
  transition: box-shadow 0.2s;
}
.step-card:hover { box-shadow: 0 4px 16px rgba(14,124,123,0.1); }
.step-header {
  display: flex; align-items: center; gap: 12px;
  background: linear-gradient(90deg, #e0f5f5, #f0fafa);
  padding: 12px 16px; border-bottom: 1px solid #c8e8e8;
}
.step-badge {
  min-width: 32px; height: 32px; border-radius: 50%;
  background: linear-gradient(135deg, #0e7c7b, #17a5a3);
  display: flex; align-items: center; justify-content: center;
  font-size: 13px; font-weight: 700; color: #fff; flex-shrink: 0;
}
.step-title { font-size: 14px; font-weight: 600; color: #0a5454; }
.step-subtitle { font-size: 11px; color: #5a8f8f; margin-top: 2px; }
.step-body { padding: 14px 16px; font-size: 13px; line-height: 1.75; color: #2a3d3d; }
.formula {
  background: linear-gradient(90deg, #eaf6f6, #f5fdfd);
  border-left: 4px solid #17a5a3;
  border-radius: 0 8px 8px 0;
  padding: 10px 14px;
  font-family: monospace; font-size: 13px;
  color: #0a5454; font-weight: 600;
  margin: 8px 0;
}
.calc-box {
  background: #f5fdfd; border: 1px solid #c8e8e8;
  border-radius: 8px; padding: 10px 14px;
  font-family: monospace; font-size: 12px;
  color: #1a3d3d; white-space: pre; line-height: 1.9;
  margin: 8px 0;
}
.result-pill {
  display: inline-block;
  background: linear-gradient(135deg, #0e7c7b, #17a5a3);
  color: #fff; border-radius: 20px;
  padding: 5px 16px; font-size: 13px; font-weight: 700;
  margin-top: 6px; box-shadow: 0 2px 8px rgba(14,124,123,0.2);
}
.highlight-row { background: #dff4f4; font-weight: 600; }

/* ── Result Table ── */
.section-divider {
  display: flex; align-items: center; gap: 12px;
  margin: 0.5rem 0 1rem;
}
.section-divider span {
  font-size: 12px; font-weight: 700; color: #17a5a3;
  letter-spacing: 0.06em; text-transform: uppercase; white-space: nowrap;
}
.section-divider::before, .section-divider::after {
  content: ''; flex: 1; height: 1px; background: #b2e0df;
}

.tbl { width: 100%; border-collapse: collapse; font-size: 13px; }
.tbl thead tr { background: linear-gradient(90deg, #0e7c7b, #17a5a3); }
.tbl th { padding: 10px 12px; color: #fff; font-size: 11px; font-weight: 600; text-align: left; letter-spacing: 0.04em; }
.tbl td { padding: 9px 12px; border-bottom: 1px solid #e8f5f5; }
.tbl tbody tr:nth-child(even) td { background: #f5fdfd; }
.tbl tbody tr:hover td { background: #dff4f4; }
.tbl tfoot td { background: #eaf6f6; font-weight: 700; color: #0a5454; border-top: 2px solid #b2e0df; padding: 9px 12px; }

/* ── Info Box ── */
.info-box {
  background: #e0f5f5; border: 1px solid #a0d8d8; border-radius: 10px;
  padding: 10px 14px; font-size: 12px; color: #0a5454;
  margin-bottom: 1rem; display: flex; gap: 8px; align-items: flex-start;
}
.info-icon { font-size: 16px; flex-shrink: 0; margin-top: 1px; }

/* ── Summary Cards ── */
.summary-grid { display: grid; grid-template-columns: repeat(4, minmax(0,1fr)); gap: 10px; margin-bottom: 1.25rem; }
.summary-card {
  background: linear-gradient(135deg, #eaf6f6, #f5fdfd);
  border: 1px solid #b2e0df; border-radius: 10px; padding: 12px;
  text-align: center;
}
.summary-label { font-size: 10px; color: #5a8f8f; font-weight: 600; text-transform: uppercase; letter-spacing: 0.05em; margin-bottom: 4px; }
.summary-value { font-size: 20px; font-weight: 700; color: #0e7c7b; }
.summary-sub { font-size: 10px; color: #8ab0b0; margin-top: 3px; }

/* ── Empty ── */
.empty { text-align: center; padding: 2.5rem; color: #9abcbc; font-size: 13px; }

/* ── Footer ── */
.footer { text-align: center; font-size: 11px; color: #a0bcbc; margin-top: 0.5rem; padding-bottom: 1.5rem; }

@media (max-width: 560px) {
  .summary-grid { grid-template-columns: repeat(2, 1fr); }
  .header { padding: 1rem 1.25rem; }
  .header-title { font-size: 15px; }
}
</style>
</head>
<body>

<div class="header">
  <div class="header-icon">📊</div>
  <div>
    <div class="header-title">Distribusi Frekuensi Kelompok</div>
    <div class="header-sub">Media Pembelajaran Interaktif · SMA / MA / SMK · Langkah demi Langkah</div>
  </div>
</div>

<div class="container">

  <!-- INPUT -->
  <div class="card">
    <div class="card-title">Input Data Mentah</div>
    <div class="info-box">
      <span class="info-icon">💡</span>
      <span>Masukkan data satu per satu, atau pilih contoh data di bawah. Aplikasi akan otomatis membuat tabel distribusi frekuensi lengkap beserta langkah-langkahnya.</span>
    </div>

    <p class="preset-label">Pilih contoh data:</p>
    <div class="preset-row">
      <button class="preset-btn" onclick="loadPreset('nilai')">📝 Nilai ujian (n=40)</button>
      <button class="preset-btn" onclick="loadPreset('tinggi')">📏 Tinggi badan (n=30)</button>
      <button class="preset-btn" onclick="loadPreset('umur')">🎂 Usia siswa (n=35)</button>
      <button class="preset-btn" onclick="loadPreset('berat')">⚖️ Berat badan (n=32)</button>
    </div>

    <div class="input-row">
      <input type="number" id="addVal" placeholder="Ketik nilai..." onkeydown="if(event.key==='Enter') addData()">
      <button class="btn" onclick="addData()">+ Tambah</button>
      <button class="btn btn-danger btn-sm" onclick="clearData()">Hapus Semua</button>
    </div>

    <div class="data-grid" id="dataGrid">
      <span style="font-size:13px;color:#9abcbc;">Pilih contoh atau ketik data di atas.</span>
    </div>
    <div class="data-hint" id="dataCount"></div>

    <div style="margin-top:1rem; text-align:right;">
      <button class="btn btn-primary" onclick="compute()">Buat Tabel Distribusi →</button>
    </div>
  </div>

  <!-- RESULT -->
  <div id="resultArea" style="display:none;">

    <!-- Summary -->
    <div class="card">
      <div class="card-title">Ringkasan Data</div>
      <div class="summary-grid">
        <div class="summary-card">
          <div class="summary-label">Jumlah Data</div>
          <div class="summary-value" id="sN">—</div>
          <div class="summary-sub">n</div>
        </div>
        <div class="summary-card">
          <div class="summary-label">Jangkauan</div>
          <div class="summary-value" id="sR">—</div>
          <div class="summary-sub">R = Xmaks − Xmin</div>
        </div>
        <div class="summary-card">
          <div class="summary-label">Banyak Kelas</div>
          <div class="summary-value" id="sK">—</div>
          <div class="summary-sub">k (Sturges)</div>
        </div>
        <div class="summary-card">
          <div class="summary-label">Panjang Kelas</div>
          <div class="summary-value" id="sP">—</div>
          <div class="summary-sub">p = R / k</div>
        </div>
      </div>
    </div>

    <!-- Langkah-langkah -->
    <div class="card">
      <div class="card-title">Langkah-langkah Pembuatan Tabel</div>
      <div class="steps-wrapper" id="stepsArea"></div>
    </div>

    <!-- Tabel Hasil -->
    <div class="card">
      <div class="card-title">Tabel Distribusi Frekuensi Kelompok</div>
      <div style="overflow-x:auto;">
        <table class="tbl" id="distTable"></table>
      </div>
    </div>

  </div>

  <div class="footer">Media Pembelajaran Statistika · SMA/MA/SMK · HTML5 &amp; Vanilla JS</div>

</div>

<script>
// ── Data ──────────────────────────────────────────────────
let rawData = [];

const presets = {
  nilai:   [45,50,52,55,56,58,60,61,62,63,64,65,65,66,67,68,68,69,70,70,71,72,73,73,74,75,75,76,77,78,78,79,80,81,82,84,85,87,90,95],
  tinggi:  [148,150,151,152,153,154,155,155,156,157,158,158,159,160,160,161,162,163,163,164,165,165,166,167,168,170,172,173,175,178],
  umur:    [14,14,15,15,15,15,16,16,16,16,16,17,17,17,17,17,17,18,18,18,18,18,18,18,19,19,19,19,20,20,20,21,21,22,23],
  berat:   [42,44,45,46,47,48,48,49,50,51,51,52,52,53,53,54,54,55,55,56,56,57,57,58,58,59,60,61,62,63,65,68]
};

// ── Preset ────────────────────────────────────────────────
function loadPreset(key) {
  rawData = [...presets[key]];
  renderChips();
  compute();
}

function addData() {
  const v = parseFloat(document.getElementById('addVal').value);
  if (isNaN(v)) return;
  rawData.push(v);
  rawData.sort((a, b) => a - b);
  document.getElementById('addVal').value = '';
  renderChips();
}

function removeItem(idx) {
  rawData.splice(idx, 1);
  renderChips();
}

function clearData() {
  rawData = [];
  renderChips();
  document.getElementById('resultArea').style.display = 'none';
}

function renderChips() {
  const g = document.getElementById('dataGrid');
  const count = document.getElementById('dataCount');
  if (!rawData.length) {
    g.innerHTML = '<span style="font-size:13px;color:#9abcbc;">Belum ada data.</span>';
    count.textContent = '';
    return;
  }
  g.innerHTML = rawData.map((v, i) =>
    `<span class="chip" title="Klik untuk hapus" onclick="removeItem(${i})">${v}</span>`
  ).join('');
  count.textContent = `${rawData.length} data · klik nilai untuk menghapus`;
}

// ── Compute ───────────────────────────────────────────────
function compute() {
  if (rawData.length < 5) {
    alert('Masukkan minimal 5 data terlebih dahulu.');
    return;
  }

  const data = [...rawData].sort((a, b) => a - b);
  const n    = data.length;
  const xMin = data[0];
  const xMax = data[n - 1];
  const R    = xMax - xMin;
  const k    = Math.round(1 + 3.322 * Math.log10(n));
  const p    = Math.ceil(R / k);

  // Summary cards
  document.getElementById('sN').textContent = n;
  document.getElementById('sR').textContent = R;
  document.getElementById('sK').textContent = k;
  document.getElementById('sP').textContent = p;

  // Build classes
  let classes = [];
  let lo = xMin;
  for (let i = 0; i < k; i++) {
    const hi   = lo + p - 1;
    const tbB  = +(lo - 0.5).toFixed(1);
    const tbA  = +(lo + p - 0.5).toFixed(1);
    const xi   = +((lo + lo + p - 1) / 2).toFixed(2);
    const freq = data.filter(v => i < k - 1 ? v >= lo && v <= hi : v >= lo).length;
    classes.push({ lo, hi: i < k - 1 ? hi : Math.max(hi, xMax), tbB, tbA, xi, freq, fk: 0 });
    lo = lo + p;
  }
  let cum = 0;
  classes.forEach(c => { cum += c.freq; c.fk = cum; });

  // Render
  renderSteps(data, n, xMin, xMax, R, k, p, classes);
  renderTable(classes, n);

  document.getElementById('resultArea').style.display = '';
  setTimeout(() => {
    document.getElementById('resultArea').scrollIntoView({ behavior: 'smooth', block: 'start' });
  }, 100);
}

// ── Steps ─────────────────────────────────────────────────
function renderSteps(data, n, xMin, xMax, R, k, p, classes) {
  const logVal   = Math.log10(n).toFixed(4);
  const kRaw     = (1 + 3.322 * Math.log10(n)).toFixed(4);
  const pRaw     = (R / k).toFixed(4);

  // Data terurut preview (maks 20 tampil)
  const sorted   = [...data];
  const preview  = sorted.length > 20
    ? sorted.slice(0, 10).join(', ') + ` ... (${sorted.length - 20} data lainnya) ... ` + sorted.slice(-10).join(', ')
    : sorted.join(', ');

  // Interval list
  const intervalLines = classes.map((c, i) =>
    `  Kelas ${i + 1}: ${c.lo} – ${c.hi}`
  ).join('\n');

  // Tepi kelas list
  const tepiLines = classes.map((c, i) =>
    `  Kelas ${i + 1}: ${c.tbB} – ${c.tbA}`
  ).join('\n');

  // Titik tengah list
  const xiLines = classes.map((c, i) =>
    `  Kelas ${i + 1}: (${c.lo} + ${c.hi}) / 2 = ${c.xi}`
  ).join('\n');

  document.getElementById('stepsArea').innerHTML = `

    <!-- Langkah 1 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">1</div>
        <div>
          <div class="step-title">Urutkan data dan tentukan nilai minimum & maksimum</div>
          <div class="step-subtitle">Langkah awal sebelum membuat tabel distribusi</div>
        </div>
      </div>
      <div class="step-body">
        <p>Urutkan seluruh data dari nilai terkecil ke terbesar, kemudian tentukan nilai minimum (X<sub>min</sub>) dan nilai maksimum (X<sub>max</sub>).</p>
        <div class="calc-box">Data terurut:
${preview}

X min  = ${xMin}
X maks = ${xMax}
n      = ${n} data</div>
        <span class="result-pill">X min = ${xMin} &nbsp;|&nbsp; X maks = ${xMax}</span>
      </div>
    </div>

    <!-- Langkah 2 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">2</div>
        <div>
          <div class="step-title">Menentukan Jangkauan (Range)</div>
          <div class="step-subtitle">Selisih antara data terbesar dan terkecil</div>
        </div>
      </div>
      <div class="step-body">
        <p>Jangkauan atau <em>range</em> adalah selisih antara nilai terbesar dan nilai terkecil dalam data.</p>
        <div class="formula">R = X maks − X min</div>
        <div class="calc-box">R = ${xMax} − ${xMin}
  = ${R}</div>
        <span class="result-pill">Jangkauan (R) = ${R}</span>
      </div>
    </div>

    <!-- Langkah 3 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">3</div>
        <div>
          <div class="step-title">Menentukan Banyak Kelas (k)</div>
          <div class="step-subtitle">Menggunakan aturan Sturges</div>
        </div>
      </div>
      <div class="step-body">
        <p>Banyak kelas ditentukan menggunakan <strong>Aturan Sturges</strong>. Aturan ini memberikan jumlah kelas yang optimal berdasarkan jumlah data.</p>
        <div class="formula">k = 1 + 3,322 × log(n)</div>
        <div class="calc-box">k = 1 + 3,322 × log(${n})
  = 1 + 3,322 × ${logVal}
  = 1 + ${(3.322 * Math.log10(n)).toFixed(4)}
  = ${kRaw}
  ≈ ${k}  (dibulatkan ke bilangan bulat terdekat)</div>
        <span class="result-pill">Banyak kelas (k) = ${k}</span>
      </div>
    </div>

    <!-- Langkah 4 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">4</div>
        <div>
          <div class="step-title">Menentukan Panjang Interval Kelas (p)</div>
          <div class="step-subtitle">Lebar setiap kelas interval</div>
        </div>
      </div>
      <div class="step-body">
        <p>Panjang kelas interval dihitung dengan membagi jangkauan dengan banyak kelas, kemudian <strong>dibulatkan ke atas</strong> agar semua data dapat masuk ke dalam tabel.</p>
        <div class="formula">p = R / k  (dibulatkan ke atas)</div>
        <div class="calc-box">p = ${R} / ${k}
  = ${pRaw}
  ≈ ${p}  (dibulatkan ke atas)</div>
        <span class="result-pill">Panjang kelas (p) = ${p}</span>
      </div>
    </div>

    <!-- Langkah 5 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">5</div>
        <div>
          <div class="step-title">Menentukan Kelas Interval</div>
          <div class="step-subtitle">Dimulai dari X min, selang p satuan</div>
        </div>
      </div>
      <div class="step-body">
        <p>Kelas pertama dimulai dari nilai X<sub>min</sub> = <strong>${xMin}</strong>. Setiap kelas berikutnya dimulai dari akhir kelas sebelumnya + 1, dengan lebar p = <strong>${p}</strong>.</p>
        <div class="calc-box">${intervalLines}</div>
        <span class="result-pill">${k} kelas interval berhasil dibuat</span>
      </div>
    </div>

    <!-- Langkah 6 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">6</div>
        <div>
          <div class="step-title">Menentukan Tepi Kelas</div>
          <div class="step-subtitle">Batas bawah dikurang 0,5 · Batas atas ditambah 0,5</div>
        </div>
      </div>
      <div class="step-body">
        <p>Tepi kelas digunakan untuk menghindari celah antara kelas yang berdekatan, terutama saat menghitung median dan modus.</p>
        <div class="formula">Tepi bawah = batas bawah − 0,5
Tepi atas  = batas atas  + 0,5</div>
        <div class="calc-box">${tepiLines}</div>
      </div>
    </div>

    <!-- Langkah 7 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">7</div>
        <div>
          <div class="step-title">Menentukan Titik Tengah Kelas (xᵢ)</div>
          <div class="step-subtitle">Rata-rata dari batas bawah dan batas atas</div>
        </div>
      </div>
      <div class="step-body">
        <p>Titik tengah digunakan dalam perhitungan rata-rata data kelompok (mean).</p>
        <div class="formula">xᵢ = (batas bawah + batas atas) / 2</div>
        <div class="calc-box">${xiLines}</div>
      </div>
    </div>

    <!-- Langkah 8 -->
    <div class="step-card">
      <div class="step-header">
        <div class="step-badge">8</div>
        <div>
          <div class="step-title">Menghitung Frekuensi & Frekuensi Kumulatif</div>
          <div class="step-subtitle">Cacah data di setiap kelas interval</div>
        </div>
      </div>
      <div class="step-body">
        <p>Hitung berapa banyak data yang masuk ke setiap kelas interval. Frekuensi kumulatif adalah jumlah frekuensi dari kelas pertama sampai kelas tersebut.</p>
        <div class="calc-box">${classes.map((c, i) =>
          `  Kelas ${i + 1} (${c.lo}–${c.hi}): ${c.freq} data   →   fk = ${c.fk}`
        ).join('\n')}

Total frekuensi = ${n} (harus = n, sebagai pengecekan ✓)</div>
        <span class="result-pill">Total = ${n} data ✓</span>
      </div>
    </div>

  `;
}

// ── Table ─────────────────────────────────────────────────
function renderTable(classes, n) {
  const rows = classes.map((c, i) => `
    <tr>
      <td style="text-align:center;color:#5a8f8f;font-weight:600;">${i + 1}</td>
      <td>${c.lo} – ${c.hi}</td>
      <td>${c.tbB} – ${c.tbA}</td>
      <td style="text-align:center;">${c.xi}</td>
      <td style="text-align:center;font-weight:600;color:#0e7c7b;">${c.freq}</td>
      <td style="text-align:center;">${c.fk}</td>
      <td style="text-align:center;">
        <div style="background:#b2e0df;border-radius:4px;height:8px;width:100%;max-width:80px;overflow:hidden;display:inline-block;vertical-align:middle;">
          <div style="background:#0e7c7b;height:100%;width:${Math.round((c.freq/n)*100)}%;"></div>
        </div>
        <span style="font-size:11px;color:#5a8f8f;margin-left:4px;">${Math.round((c.freq/n)*100)}%</span>
      </td>
    </tr>
  `).join('');

  document.getElementById('distTable').innerHTML = `
    <thead>
      <tr>
        <th>No</th>
        <th>Kelas Interval</th>
        <th>Tepi Kelas</th>
        <th>Titik Tengah (xᵢ)</th>
        <th>Frekuensi (fᵢ)</th>
        <th>F. Kumulatif</th>
        <th>Proporsi</th>
      </tr>
    </thead>
    <tbody>${rows}</tbody>
    <tfoot>
      <tr>
        <td colspan="4" style="font-weight:700;">Total</td>
        <td style="text-align:center;font-weight:700;">${n}</td>
        <td style="text-align:center;">—</td>
        <td style="text-align:center;font-size:11px;">100%</td>
      </tr>
    </tfoot>
  `;
}
</script>
</body>
</html>
