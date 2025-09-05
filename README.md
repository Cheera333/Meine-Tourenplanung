<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>🏔️ Angelos Hochtourenplaner</title>
  <style>
    body { font-family: sans-serif; background: #111827; color: #fff; margin: 0; padding: 1rem; }
    h1, h2 { margin-bottom: 0.5rem; }
    .card { background: #1f2937; border-radius: 1rem; padding: 1rem; margin-bottom: 1rem; }
    .input-group { display: flex; flex-direction: column; margin: 0.5rem 0; }
    label { margin-top: 0.25rem; }
    input[type="text"], input[type="number"], input[type="file"] { margin: 0.25rem 0; padding: 0.5rem; border-radius: 0.25rem; border: none; background: #374151; color: #fff; width: 100%; }
    table { width: 100%; border-collapse: collapse; margin-top: 0.5rem; }
    th, td { border: 1px solid #374151; padding: 0.5rem; text-align: center; }
    button { background: #16a34a; color: #fff; padding: 0.5rem 1rem; border: none; border-radius: 0.5rem; font-size: 1rem; margin-top: 0.5rem; cursor: pointer; }
    button:hover { background: #15803d; }
    input[type="checkbox"] { transform: scale(1.2); margin-right: 0.5rem; }
    .three-cols { display: flex; flex-wrap: wrap; gap: 0.5rem; }
    .three-cols label { flex: 1 1 calc(33% - 0.5rem); }
    .windrose { display: flex; flex-wrap: wrap; gap: 0.25rem; }
    .windrose label { display: flex; align-items: center; justify-content: center; width: 50px; height: 50px; border: 1px solid #374151; border-radius: 50%; }
    .file-group { display: flex; flex-wrap: wrap; gap: 1rem; }
    .file-group label { flex: 1 1 calc(20% - 1rem); }
  </style>
</head>
<body>
  <h1>🏔️ Angelos Hochtourenplaner</h1>

  <!-- Tourensteckbrief bleibt unverändert -->

  <div class="card">
    <h2>5) Zeitmanagement & Marschplanung</h2>
    <div class="input-group">
      <label>Anreise (Zeit ab Zuhause)<input type="text"></label>
      <label>Startzeit<input type="text"></label>
      <label>Geplanter Gipfel<input type="text"></label>
      <label>Geplanter Rückweg<input type="text"></label>
      <label>Umkehrzeit<input type="text"></label>
      <label>Erste Bahn<input type="text"></label>
      <label>Letzte Bahn<input type="text"></label>
      <label>Sonnenaufgang<input type="text"></label>
      <label>Sonnenuntergang<input type="text"></label>
    </div>
    <table id="sectionTable">
      <thead>
        <tr><th>Schlüsselstelle</th><th>Abschnitt</th><th>von – nach</th><th>Hm↑</th><th>Hm↓</th><th>MüM↓</th><th>Distanz</th><th>Dauer</th><th>Uhrzeit</th></tr>
      </thead>
      <tbody>
        <tr>
          <td><input type="checkbox"></td><td><input type="text"></td><td><input type="text"></td>
          <td><input type="number"></td>
          <td><input type="number"></td><td><input type="number"></td>
          <td><input type="text"></td><td><input type="text"></td><td><input type="text"></td>
        </tr>
      </tbody>
    </table>
    <button onclick="addRow()">➕ Abschnitt hinzufügen</button>
  </div>

  <script>
    function addRow() {
      const table = document.getElementById("sectionTable").getElementsByTagName('tbody')[0];
      const newRow = table.rows[0].cloneNode(true);
      newRow.querySelectorAll('input').forEach(input => { input.value = input.type === 'checkbox' ? false : ''; });
      table.appendChild(newRow);
    }
  </script>

  <div class="card">
    <h2>7) Navigation & GPX / Bilder</h2>
    <div class="file-group">
      <label>GPX Datei 1<input type="file"></label>
      <label>GPX Datei 2<input type="file"></label>
      <label>GPX Datei 3<input type="file"></label>
      <label>GPX Datei 4<input type="file"></label>
      <label>GPX Datei 5<input type="file"></label>
    </div>
    <div class="file-group">
      <label>Bild 1<input type="file"></label>
      <label>Bild 2<input type="file"></label>
      <label>Bild 3<input type="file"></label>
      <label>Bild 4<input type="file"></label>
      <label>Bild 5<input type="file"></label>
    </div>
    <div class="input-group">
      <label>Kurzbeschreibung<input type="text"></label>
    </div>
  </div>

  <div class="card">
    <h2>8) Risikomanagement (3x3 Methode)</h2>
    <table>
      <thead><tr><th>Ebene</th><th>Zu Hause / Planung</th><th>Vor Ort / Gebiet</th><th>Einzelhang / Schlüsselstelle</th></tr></thead>
      <tbody>
        <tr>
          <td>Verhältnisse</td>
          <td>
            Verhältnisse/zu Hause: 1. Lawinenlagebericht<br>2. Wetterprognose<br>3. Auskünfte von Locals und Experten
          </td>
          <td>
            Lokal/verhältnisse: 1. Schneeverfrachtungen<br>2. Alarmzeichen<br>3. Kritische Neuschneemengen<br>4. Wellen/Dünen/Windgangeln<br>5. Lawinenlagebericht prüfen<br>6. Gefährliche Stellen
          </td>
          <td>
            Hang/verhältnisse: 1. Neuschneemenge<br>2. Frische Triebschneeansammlungen<br>3. Sonneneinstrahlung<br>4. Wo könnte ein Schneebrett abgehen?
          </td>
        </tr>
        <tr>
          <td>Gelände</td>
          <td>
            Gelände/zu Hause: 1. Karte 1:25.000<br>2. Tourenführer<br>3. Eigene Geländekenntnisse
          </td>
          <td>
            Lokal/gelände: 1. Geländeformen/Steilheit<br>2. Exposition(en)<br>3. Spuren anderer Freerider angepasst?<br>4. Sicht, Bewölkung, Wind, Niederschlag, Temperatur
          </td>
          <td>
            Hang/Gelände: 1. Wer/was über mir?<br>2. Wer/was unter mir?<br>3. Steilste Hangstelle?<br>4. Exposition<br>5. Typisches Lawinengelände<br>6. Hangform<br>7. Höhenlage<br>8. Befahrungshäufigkeit
          </td>
        </tr>
        <tr>
          <td>Mensch</td>
          <td>
            Mensch/zu Hause: 1. Wer kommt mit?<br>2. Ausbildung/Erfahrung der Kollegen?<br>3. Ausrüstung<br>4. Kondition
          </td>
          <td>
            Lokal/mensch: 1. Mit wem unterwegs?<br>2. LVS-Kontrolle<br>3. Andere Freerider? Absprachen?<br>4. Zeitplan (Soll/Ist)
          </td>
          <td>
            Hang/Mensch & Vorsichtsmaßnahmen: 1. Können, Disziplin, Müdigkeit<br>2. Abstände<br>3. Einzelfahrten<br>4. Sichere Sammelplätze<br>5. Ggf. Hang umgehen/Abfahrt verzichten
          </td>
        </tr>
      </tbody>
    </table>
  </div>

</body>
</html>
