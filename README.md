# index.html.

<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Certificado de Capacitação Corporativa — OASIS</title>

  <style>
    @page {
      size: A4 landscape;
      margin: 0;
    }

    :root {
      --navy: #0b1f3a;
      --navy-deep: #07152a;
      --cobalt: #1557a6;
      --sky: #8cc9ed;
      --silver: #aebdca;
      --light: #f5f8fb;
      --ink: #1e2b3c;
      --muted: #647386;
      --white: #ffffff;
    }

    * {
      box-sizing: border-box;
    }

    html,
    body {
      margin: 0;
      padding: 0;
      width: 100%;
      min-height: 100%;
      background: #dfe5eb;
      font-family: "Segoe UI", Arial, Helvetica, sans-serif;
      color: var(--ink);
    }

    body {
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 18px;
    }

    .certificate {
      position: relative;
      width: 297mm;
      height: 210mm;
      min-width: 297mm;
      min-height: 210mm;
      overflow: hidden;
      background:
        radial-gradient(circle at 86% 14%, rgba(21, 87, 166, 0.08), transparent 28%),
        linear-gradient(135deg, #ffffff 0%, #ffffff 69%, #f1f6fa 100%);
      box-shadow: 0 12px 35px rgba(7, 21, 42, 0.22);
      padding: 17mm 20mm 15mm;
      -webkit-print-color-adjust: exact;
      print-color-adjust: exact;
    }

    /* Moldura externa */
    .certificate::before {
      content: "";
      position: absolute;
      inset: 7mm;
      border: 1.2mm solid var(--navy);
      pointer-events: none;
    }

    .certificate::after {
      content: "";
      position: absolute;
      inset: 10mm;
      border: 0.35mm solid var(--silver);
      pointer-events: none;
    }

    /* Elementos geométricos decorativos */
    .shape {
      position: absolute;
      pointer-events: none;
      z-index: 0;
    }

    .shape.top-left {
      top: 7mm;
      left: 7mm;
      width: 41mm;
      height: 24mm;
      border-top: 2mm solid var(--cobalt);
      border-left: 2mm solid var(--cobalt);
    }

    .shape.top-left::after {
      content: "";
      position: absolute;
      top: 7mm;
      left: 7mm;
      width: 25mm;
      height: 13mm;
      border-top: 0.55mm solid var(--sky);
      border-left: 0.55mm solid var(--sky);
    }

    .shape.top-right {
      top: 7mm;
      right: 7mm;
      width: 45mm;
      height: 30mm;
      background:
        linear-gradient(135deg, transparent 49%, var(--cobalt) 50%, var(--cobalt) 53%, transparent 54%);
      opacity: 0.9;
    }

    .shape.bottom-left {
      bottom: 7mm;
      left: 7mm;
      width: 50mm;
      height: 30mm;
      background:
        linear-gradient(315deg, transparent 49%, var(--sky) 50%, var(--sky) 52%, transparent 53%);
      opacity: 0.7;
    }

    .shape.bottom-right {
      right: 7mm;
      bottom: 7mm;
      width: 45mm;
      height: 27mm;
      border-right: 2mm solid var(--navy);
      border-bottom: 2mm solid var(--navy);
    }

    .content {
      position: relative;
      z-index: 2;
      height: 100%;
      display: flex;
      flex-direction: column;
    }

    .header {
      display: grid;
      grid-template-columns: 1fr 2.2fr 1fr;
      align-items: start;
      column-gap: 10mm;
      padding: 1mm 4mm 0;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 3mm;
      color: var(--navy);
    }

    .brand-mark {
      position: relative;
      width: 17mm;
      height: 17mm;
      flex: 0 0 auto;
      border: 1.6mm solid var(--cobalt);
      border-radius: 50%;
    }

    .brand-mark::before,
    .brand-mark::after {
      content: "";
      position: absolute;
      background: var(--cobalt);
      border-radius: 5px;
    }

    .brand-mark::before {
      width: 2.5mm;
      height: 11mm;
      left: 6mm;
      top: 1.6mm;
      transform: rotate(38deg);
    }

    .brand-mark::after {
      width: 2.5mm;
      height: 11mm;
      left: 8.4mm;
      top: 4mm;
      transform: rotate(-38deg);
    }

    .brand-name {
      font-size: 17pt;
      font-weight: 800;
      letter-spacing: 0.16em;
      line-height: 1;
    }

    .brand-subtitle {
      margin-top: 2mm;
      color: var(--muted);
      font-size: 6.6pt;
      font-weight: 600;
      letter-spacing: 0.07em;
      text-transform: uppercase;
    }

    .issuer {
      text-align: center;
      padding-top: 1mm;
    }

    .issuer-label {
      color: var(--cobalt);
      font-size: 7.5pt;
      font-weight: 700;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    .issuer-name {
      margin-top: 1.7mm;
      color: var(--navy);
      font-size: 10pt;
      font-weight: 700;
      letter-spacing: 0.04em;
      text-transform: uppercase;
    }

    .header-meta {
      text-align: right;
      color: var(--muted);
      font-size: 7pt;
      line-height: 1.65;
      padding-top: 1mm;
    }

    .header-meta strong {
      color: var(--navy);
      font-size: 7.3pt;
    }

    .title-area {
      text-align: center;
      margin-top: 8mm;
    }

    .eyebrow {
      color: var(--cobalt);
      font-size: 8pt;
      font-weight: 700;
      letter-spacing: 0.32em;
      text-transform: uppercase;
    }

    h1 {
      margin: 3mm 0 2mm;
      color: var(--navy);
      font-family: Georgia, "Times New Roman", serif;
      font-size: 28pt;
      font-weight: 700;
      letter-spacing: 0.06em;
      line-height: 1.05;
    }

    .title-rule {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 4mm;
    }

    .title-rule::before,
    .title-rule::after {
      content: "";
      width: 35mm;
      height: 0.4mm;
      background: var(--silver);
    }

    .title-diamond {
      width: 3mm;
      height: 3mm;
      background: var(--cobalt);
      transform: rotate(45deg);
    }

    .statement {
      max-width: 215mm;
      margin: 6mm auto 0;
      text-align: center;
      color: #26384d;
      font-family: Georgia, "Times New Roman", serif;
      font-size: 13pt;
      line-height: 1.65;
    }

    .statement strong {
      color: var(--navy);
      font-size: 15pt;
    }

    .details {
      display: grid;
      grid-template-columns: 1.18fr 0.82fr;
      gap: 8mm;
      margin: 7mm 5mm 0;
    }

    .panel {
      position: relative;
      min-height: 40mm;
      padding: 5mm 6mm;
      border: 0.35mm solid #c7d2dc;
      background: rgba(255, 255, 255, 0.76);
    }

    .panel::before {
      content: "";
      position: absolute;
      top: -0.35mm;
      left: -0.35mm;
      width: 20mm;
      height: 1.1mm;
      background: var(--cobalt);
    }

    .panel-title {
      margin-bottom: 4mm;
      color: var(--navy);
      font-size: 8pt;
      font-weight: 800;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }

    .program-name {
      color: var(--cobalt);
      font-size: 15pt;
      font-weight: 800;
      line-height: 1.2;
    }

    .program-description {
      margin-top: 2mm;
      color: var(--muted);
      font-size: 8.7pt;
      line-height: 1.45;
    }

    .info-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 4mm;
      margin-top: 5mm;
    }

    .info-label {
      color: var(--muted);
      font-size: 6.7pt;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .info-value {
      margin-top: 1.4mm;
      color: var(--navy);
      font-size: 9pt;
      font-weight: 700;
    }

    .competencies {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2.5mm 6mm;
      margin: 0;
      padding: 0;
      list-style: none;
    }

    .competencies li {
      position: relative;
      padding-left: 4mm;
      color: #33465b;
      font-size: 8.5pt;
      line-height: 1.3;
    }

    .competencies li::before {
      content: "";
      position: absolute;
      left: 0;
      top: 1.8mm;
      width: 1.6mm;
      height: 1.6mm;
      background: var(--cobalt);
      transform: rotate(45deg);
    }

    .bottom-area {
      display: grid;
      grid-template-columns: 1.25fr 1fr;
      gap: 8mm;
      align-items: end;
      margin: auto 5mm 0;
      padding-bottom: 1mm;
    }

    .governance {
      color: var(--muted);
      font-size: 7.2pt;
      line-height: 1.7;
    }

    .governance-title {
      margin-bottom: 2mm;
      color: var(--navy);
      font-size: 7.8pt;
      font-weight: 800;
      letter-spacing: 0.14em;
      text-transform: uppercase;
    }

    .governance-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1mm 7mm;
    }

    .governance strong {
      color: var(--navy);
      font-weight: 700;
    }

    .signatures {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 9mm;
    }

    .signature {
      text-align: center;
    }

    .signature-line {
      height: 10mm;
      border-bottom: 0.35mm solid var(--navy);
      margin-bottom: 2mm;
    }

    .signature-name {
      color: var(--navy);
      font-size: 8.2pt;
      font-weight: 800;
    }

    .signature-role {
      margin-top: 0.7mm;
      color: var(--muted);
      font-size: 6.8pt;
      line-height: 1.25;
    }

    .footer-note {
      position: absolute;
      left: 20mm;
      bottom: 9mm;
      color: #718193;
      font-size: 5.8pt;
      letter-spacing: 0.04em;
    }

    [contenteditable="true"] {
      outline: none;
      border-radius: 2px;
    }

    [contenteditable="true"]:focus {
      box-shadow: 0 0 0 1px var(--sky);
      background: rgba(140, 201, 237, 0.12);
    }

    @media print {
      html,
      body {
        width: 297mm;
        height: 210mm;
        background: #ffffff;
      }

      body {
        display: block;
        padding: 0;
      }

      .certificate {
        box-shadow: none;
        margin: 0;
      }
    }
  </style>
</head>

<body>
  <main class="certificate">
    <div class="shape top-left"></div>
    <div class="shape top-right"></div>
    <div class="shape bottom-left"></div>
    <div class="shape bottom-right"></div>

    <section class="content">
      <header class="header">
        <div class="brand">
          <div class="brand-mark" aria-label="Símbolo gráfico OASIS"></div>

          <div>
            <div class="brand-name">OASIS</div>
            <div class="brand-subtitle">Excelência que transforma</div>
          </div>
        </div>

        <div class="issuer">
          <div class="issuer-label">Departamento emissor</div>
          <div class="issuer-name">
            Universidade Corporativa OASIS
          </div>
        </div>

        <div class="header-meta">
          <div><strong>Registro:</strong> <span contenteditable="true">OASIS-2026-000000</span></div>
          <div><strong>Emissão:</strong> <span contenteditable="true">31 de agosto de 2026</span></div>
        </div>
      </header>

      <section class="title-area">
        <div class="eyebrow">Reconhecimento institucional</div>

        <h1>CERTIFICADO DE CAPACITAÇÃO CORPORATIVA</h1>

        <div class="title-rule">
          <span class="title-diamond"></span>
        </div>

        <p class="statement">
          Certificamos que
          <strong contenteditable="true">[NOME DO COLABORADOR]</strong>,
          ocupante do cargo de
          <strong contenteditable="true">[CARGO]</strong>,
          matrícula nº
          <strong contenteditable="true">[Nº DE MATRÍCULA]</strong>,
          concluiu com êxito o programa de treinamento descrito abaixo,
          atendendo aos requisitos de participação e aproveitamento
          estabelecidos pela OASIS.
        </p>
      </section>

      <section class="details">
        <article class="panel">
          <div class="panel-title">Detalhes da capacitação</div>

          <div class="program-name" contenteditable="true">
            [NOME DO PROGRAMA OU MÓDULO]
          </div>

          <div class="program-description" contenteditable="true">
            Programa desenvolvido para fortalecer competências profissionais,
            ampliar a capacidade de execução e apoiar a evolução contínua dos
            colaboradores da OASIS.
          </div>

          <div class="info-grid">
            <div>
              <div class="info-label">Carga horária total</div>
              <div class="info-value" contenteditable="true">[00 horas]</div>
            </div>

            <div>
              <div class="info-label">Período de realização</div>
              <div class="info-value" contenteditable="true">[dd/mm/aaaa a dd/mm/aaaa]</div>
            </div>

            <div>
              <div class="info-label">Modalidade</div>
              <div class="info-value" contenteditable="true">[Presencial / Online / Híbrida]</div>
            </div>
          </div>
        </article>

        <article class="panel">
          <div class="panel-title">Competências desenvolvidas</div>

          <ul class="competencies">
            <li contenteditable="true">[Competência ou conhecimento 01]</li>
            <li contenteditable="true">[Competência ou conhecimento 02]</li>
            <li contenteditable="true">[Competência ou conhecimento 03]</li>
            <li contenteditable="true">[Competência ou conhecimento 04]</li>
            <li contenteditable="true">[Competência ou conhecimento 05]</li>
            <li contenteditable="true">[Competência ou conhecimento 06]</li>
          </ul>
        </article>
      </section>

      <section class="bottom-area">
        <div class="governance">
          <div class="governance-title">Governança e rastreabilidade</div>

          <div class="governance-grid">
            <div>
              <strong>Código de validação:</strong><br />
              <span contenteditable="true">[OASIS-VAL-000000]</span>
            </div>

            <div>
              <strong>Número de registro:</strong><br />
              <span contenteditable="true">[REG-000000]</span>
            </div>

            <div>
              <strong>Data oficial de emissão:</strong><br />
              <span contenteditable="true">[dd de mês de aaaa]</span>
            </div>

            <div>
              <strong>Unidade responsável:</strong><br />
              <span contenteditable="true">[Área / Unidade OASIS]</span>
            </div>
          </div>
        </div>

        <div class="signatures">
          <div class="signature">
            <div class="signature-line"></div>
            <div class="signature-name" contenteditable="true">
              [NOME DO DIRETOR OU EXECUTIVO]
            </div>
            <div class="signature-role">
              Diretor(a) de Recursos Humanos<br />
              Liderança Executiva OASIS
            </div>
          </div>

          <div class="signature">
            <div class="signature-line"></div>
            <div class="signature-name" contenteditable="true">
              [NOME DO FACILITADOR]
            </div>
            <div class="signature-role">
              Facilitador(a) do Treinamento<br />
              Universidade Corporativa OASIS
            </div>
          </div>
        </div>
      </section>
    </section>

    <div class="footer-note">
      Documento institucional — sua autenticidade pode ser confirmada por meio do código de validação informado.
    </div>
  </main>
</body>
</html>
