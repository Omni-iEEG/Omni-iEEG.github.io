---
layout: page-notitle
title: Leaderboard
permalink: /leaderboard/
description: Official Omni-iEEG benchmark baselines from the ICLR 2026 paper.
nav: false
nav_order: 1
---

<style>
.leaderboard-page {
  width: min(1080px, calc(100vw - 48px));
  margin-left: 50%;
  transform: translateX(-50%);
}

.leaderboard-page h3 {
  text-align: left;
}

.leaderboard-hero {
  margin: 2.8rem 0 1.5rem;
}

.leaderboard-contact {
  margin: 2rem 0 0;
  padding: 0.75rem 0.95rem;
  border: 1px solid rgba(39, 116, 174, 0.22);
  border-radius: 8px;
  background: rgba(39, 116, 174, 0.07);
  color: var(--global-text-color);
  font-size: 0.98rem;
}

.leaderboard-contact a {
  font-weight: 700;
}

.leaderboard-hero h1 {
  margin: 0 0 0.75rem;
  font-size: clamp(2.7rem, 5vw, 4.5rem);
  line-height: 1.05;
}

.leaderboard-hero p {
  max-width: 820px;
  margin: 0;
  font-size: clamp(1.05rem, 1.6vw, 1.35rem);
  line-height: 1.45;
}

.leaderboard-intro {
  max-width: 900px;
  margin: 0 0 1.6rem;
  text-align: left;
  color: var(--global-text-color-light);
}

.leaderboard-summary {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 0;
  margin: 1.25rem 0 2rem;
  border: 1px solid var(--global-divider-color);
  border-radius: 8px;
  overflow: hidden;
}

.leaderboard-summary-item {
  padding: 1rem;
  border-right: 1px solid var(--global-divider-color);
  background: var(--global-bg-color);
}

.leaderboard-summary-item:last-child {
  border-right: 0;
}

.leaderboard-summary-item span {
  display: block;
  margin-bottom: 0.3rem;
  color: var(--global-text-color-light);
  font-size: 0.9rem;
}

.leaderboard-summary-item strong {
  display: block;
  color: var(--global-theme-color);
  font-size: 1.35rem;
  line-height: 1.1;
}

.leaderboard-summary-item small {
  display: block;
  margin-top: 0.35rem;
  color: var(--global-text-color);
}

.leaderboard-panel {
  margin-top: 2rem;
}

.leaderboard-panel h3 {
  margin-bottom: 0.35rem;
}

.leaderboard-panel-note {
  max-width: 900px;
  margin: 0 0 0.9rem;
  text-align: left;
  color: var(--global-text-color-light);
  font-size: 0.95rem;
}

.leaderboard-table-wrap {
  width: 100%;
  max-width: 100%;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  border: 1px solid var(--global-divider-color);
  border-radius: 8px;
}

.leaderboard-table {
  width: max-content;
  min-width: 100%;
  max-width: none;
  border-collapse: collapse;
  background: var(--global-bg-color);
}

.leaderboard-table th,
.leaderboard-table td {
  padding: 0.64rem 0.78rem;
  border-bottom: 1px solid var(--global-divider-color);
  font-size: 0.95rem;
  line-height: 1.35;
  text-align: right;
  white-space: nowrap;
}

.leaderboard-table th {
  background: rgba(39, 116, 174, 0.1);
  font-weight: 700;
}

.leaderboard-table tr:last-child td {
  border-bottom: 0;
}

.leaderboard-table .leaderboard-model,
.leaderboard-table .leaderboard-task,
.leaderboard-table .leaderboard-type,
.leaderboard-table th:nth-child(2),
.leaderboard-table th:nth-child(3) {
  text-align: left;
}

.leaderboard-rank {
  width: 56px;
  text-align: center !important;
  font-weight: 700;
}

.leaderboard-primary {
  color: var(--global-theme-color);
  font-weight: 800;
}

.leaderboard-best {
  background: rgba(255, 199, 44, 0.18);
  font-weight: 800;
}

.leaderboard-row-top td {
  background: rgba(39, 116, 174, 0.06);
}

.leaderboard-caption {
  margin: 0.55rem 0 0;
  color: var(--global-text-color-light);
  font-size: 0.9rem;
}

.leaderboard-subtables {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.1rem;
}

.leaderboard-subtask h4 {
  margin: 0 0 0.45rem;
  font-size: 1.05rem;
}

@media (max-width: 900px) {
  .leaderboard-page {
    width: 100%;
    margin-left: 0;
    transform: none;
  }

  .leaderboard-summary {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .leaderboard-summary-item:nth-child(2) {
    border-right: 0;
  }

  .leaderboard-summary-item:nth-child(-n + 2) {
    border-bottom: 1px solid var(--global-divider-color);
  }

  .leaderboard-subtables {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 576px) {
  .leaderboard-page {
    width: 100%;
  }

  .leaderboard-hero {
    margin-top: 2.2rem;
  }

  .leaderboard-summary {
    grid-template-columns: 1fr;
  }

  .leaderboard-summary-item,
  .leaderboard-summary-item:nth-child(2) {
    border-right: 0;
    border-bottom: 1px solid var(--global-divider-color);
  }

  .leaderboard-summary-item:last-child {
    border-bottom: 0;
  }

  .leaderboard-table {
    min-width: 700px;
  }

  .leaderboard-table th,
  .leaderboard-table td {
    padding: 0.56rem 0.62rem;
    font-size: 0.88rem;
  }
}

@media (max-width: 700px) {
  .leaderboard-table-wrap {
    overflow-x: visible;
    border: 0;
    border-radius: 0;
  }

  .leaderboard-table {
    display: block;
    width: 100%;
    min-width: 0;
    max-width: 100%;
    background: transparent;
  }

  .leaderboard-table tbody,
  .leaderboard-table tr,
  .leaderboard-table td {
    display: block;
  }

  .leaderboard-table thead,
  .leaderboard-table thead tr,
  .leaderboard-table thead th {
    display: none !important;
  }

  .leaderboard-table tr {
    margin-bottom: 0.8rem;
    overflow: hidden;
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
    background: var(--global-bg-color);
  }

  .leaderboard-table tr:last-child {
    margin-bottom: 0;
  }

  .leaderboard-table td {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 1rem;
    width: 100%;
    border-bottom: 1px solid var(--global-divider-color);
    text-align: right !important;
    white-space: normal;
  }

  .leaderboard-table td:last-child {
    border-bottom: 0;
  }

  .leaderboard-table td::before {
    flex: 0 0 42%;
    color: var(--global-text-color-light);
    font-weight: 700;
    text-align: left;
    content: "";
  }

  .leaderboard-rank {
    width: auto;
  }

  .leaderboard-event-table td:nth-child(1)::before,
  .leaderboard-region-table td:nth-child(1)::before,
  .leaderboard-exploratory-table td:nth-child(1)::before {
    content: "Rank";
  }

  .leaderboard-event-table td:nth-child(2)::before,
  .leaderboard-region-table td:nth-child(2)::before,
  .leaderboard-exploratory-table td:nth-child(2)::before {
    content: "Model";
  }

  .leaderboard-event-table td:nth-child(3)::before,
  .leaderboard-region-table td:nth-child(4)::before {
    content: "Precision";
  }

  .leaderboard-event-table td:nth-child(4)::before,
  .leaderboard-region-table td:nth-child(5)::before {
    content: "Recall";
  }

  .leaderboard-event-table td:nth-child(5)::before,
  .leaderboard-region-table td:nth-child(6)::before,
  .leaderboard-exploratory-table td:nth-child(3)::before {
    content: "F1";
  }

  .leaderboard-event-table td:nth-child(6)::before {
    content: "AUC";
  }

  .leaderboard-region-table td:nth-child(3)::before {
    content: "Type";
  }

  .leaderboard-region-table td:nth-child(7)::before {
    content: "Specificity";
  }

  .leaderboard-region-table td:nth-child(8)::before {
    content: "Channel AUC";
  }

  .leaderboard-region-table td:nth-child(9)::before {
    content: "Outcome AUC";
  }

  .leaderboard-exploratory-table td:nth-child(4)::before {
    content: "Acc";
  }
}
</style>

<div class="leaderboard-page">
  <p class="leaderboard-contact">
    For leaderboard submissions, please <a href="mailto:chenda@ucla.edu">contact the authors</a>.
  </p>

  <header class="leaderboard-hero">
    <h1>Leaderboard</h1>
    <p>Official Omni-iEEG benchmark baselines from the ICLR 2026 paper.</p>
  </header>

  <p class="leaderboard-intro">
    Official baseline results for Omni-iEEG. Task 1 is ranked by macro-F1,
    Task 2 is ranked by pathological channel AUC, and exploratory tasks are ranked by macro-F1.
    Higher is better for all metrics.
  </p>

  <div class="leaderboard-summary" aria-label="Current benchmark leaders">
    <div class="leaderboard-summary-item">
      <span>Event Classification F1</span>
      <strong>0.8061</strong>
      <small>PyHFO-Omni</small>
    </div>
    <div class="leaderboard-summary-item">
      <span>Channel AUC</span>
      <strong>0.8061</strong>
      <small>TimeConv-CNN</small>
    </div>
    <div class="leaderboard-summary-item">
      <span>Outcome AUC</span>
      <strong>0.7438</strong>
      <small>PyHFO-Omni<sub>spkHFO</sub></small>
    </div>
    <div class="leaderboard-summary-item">
      <span>Ictal F1</span>
      <strong>0.9245</strong>
      <small>CLAP</small>
    </div>
  </div>

  <section class="leaderboard-panel">
    <h3>Task 1: Pathological Event Classification</h3>
    <p class="leaderboard-panel-note">Ranked by macro-F1 over artifact, non-spkHFO, and spkHFO event classes.</p>
    <div class="leaderboard-table-wrap">
      <table class="leaderboard-table leaderboard-event-table">
        <thead>
          <tr>
            <th class="leaderboard-rank">Rank</th>
            <th>Model</th>
            <th>Precision</th>
            <th>Recall</th>
            <th>F1</th>
            <th>AUC</th>
          </tr>
        </thead>
        <tbody>
          <tr class="leaderboard-row-top">
            <td class="leaderboard-rank">1</td>
            <td class="leaderboard-model">PyHFO-Omni</td>
            <td>0.8025</td>
            <td class="leaderboard-best">0.8110</td>
            <td class="leaderboard-primary">0.8061</td>
            <td class="leaderboard-best">0.9390</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">2</td>
            <td class="leaderboard-model">PatchTST Transformer</td>
            <td>0.7757</td>
            <td>0.7686</td>
            <td>0.7726</td>
            <td>0.9311</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">3</td>
            <td class="leaderboard-model">TimesNet</td>
            <td>0.7589</td>
            <td>0.7726</td>
            <td>0.7652</td>
            <td>0.9221</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">4</td>
            <td class="leaderboard-model">LSTM+Attention</td>
            <td>0.7352</td>
            <td>0.7359</td>
            <td>0.7338</td>
            <td>0.9109</td>
          </tr>
        </tbody>
      </table>
    </div>
    <p class="leaderboard-caption">Source: Table 4 in the Omni-iEEG paper.</p>
  </section>

  <section class="leaderboard-panel">
    <h3>Task 2: Pathological Brain Region Identification</h3>
    <p class="leaderboard-panel-note">Ranked by pathological channel classification AUC; outcome AUC evaluates resection-ratio outcome prediction.</p>
    <div class="leaderboard-table-wrap">
      <table class="leaderboard-table leaderboard-region-table">
        <thead>
          <tr>
            <th class="leaderboard-rank">Rank</th>
            <th>Model</th>
            <th>Type</th>
            <th>Precision</th>
            <th>Recall</th>
            <th>F1</th>
            <th>Specificity</th>
            <th>Channel AUC</th>
            <th>Outcome AUC</th>
          </tr>
        </thead>
        <tbody>
          <tr class="leaderboard-row-top">
            <td class="leaderboard-rank">1</td>
            <td class="leaderboard-model">TimeConv-CNN</td>
            <td class="leaderboard-type">Segment-based</td>
            <td class="leaderboard-best">0.6259</td>
            <td class="leaderboard-best">0.7454</td>
            <td class="leaderboard-best">0.6469</td>
            <td class="leaderboard-best">0.8230</td>
            <td class="leaderboard-primary">0.8061</td>
            <td>0.7380</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">2</td>
            <td class="leaderboard-model">SEEG-NET</td>
            <td class="leaderboard-type">Segment-based</td>
            <td>0.5790</td>
            <td>0.7169</td>
            <td>0.5259</td>
            <td>0.6049</td>
            <td>0.7850</td>
            <td>0.5952</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">3</td>
            <td class="leaderboard-model">CLAP</td>
            <td class="leaderboard-type">Segment-based</td>
            <td>0.5936</td>
            <td>0.6997</td>
            <td>0.6009</td>
            <td>0.7823</td>
            <td>0.7684</td>
            <td>0.6770</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">4</td>
            <td class="leaderboard-model">PyHFO-Omni<sub>spkHFO</sub></td>
            <td class="leaderboard-type">Event-based</td>
            <td>0.5799</td>
            <td>0.6991</td>
            <td>0.5635</td>
            <td>0.6951</td>
            <td>0.7351</td>
            <td class="leaderboard-best">0.7438</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">5</td>
            <td class="leaderboard-model">eHFO</td>
            <td class="leaderboard-type">Event-based</td>
            <td>0.6053</td>
            <td>0.6466</td>
            <td>0.6195</td>
            <td>0.4101</td>
            <td>0.6611</td>
            <td>0.4521</td>
          </tr>
          <tr>
            <td class="leaderboard-rank">6</td>
            <td class="leaderboard-model">PyHFO<sub>spkHFO</sub></td>
            <td class="leaderboard-type">Event-based</td>
            <td>0.6000</td>
            <td>0.6431</td>
            <td>0.6140</td>
            <td>0.4089</td>
            <td>0.6557</td>
            <td>0.4972</td>
          </tr>
        </tbody>
      </table>
    </div>
    <p class="leaderboard-caption">Source: Table 5 in the Omni-iEEG paper.</p>
  </section>

  <section class="leaderboard-panel">
    <h3>Exploratory Tasks</h3>
    <p class="leaderboard-panel-note">Ranked by macro-F1. Acc denotes balanced accuracy.</p>
    <div class="leaderboard-subtables">
      <div class="leaderboard-subtask">
        <h4>Anatomical Location (5-class)</h4>
        <div class="leaderboard-table-wrap">
          <table class="leaderboard-table leaderboard-exploratory-table">
            <thead>
              <tr>
                <th class="leaderboard-rank">Rank</th>
                <th>Model</th>
                <th>F1</th>
                <th>Acc</th>
              </tr>
            </thead>
            <tbody>
              <tr class="leaderboard-row-top">
                <td class="leaderboard-rank">1</td>
                <td class="leaderboard-model">TimeConv-CNN</td>
                <td class="leaderboard-primary">0.4788</td>
                <td>0.4708</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">2</td>
                <td class="leaderboard-model">CLAP</td>
                <td>0.4750</td>
                <td class="leaderboard-best">0.4894</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">3</td>
                <td class="leaderboard-model">SEEG-NET</td>
                <td>0.2520</td>
                <td>0.2550</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="leaderboard-subtask">
        <h4>Anatomical Location (12-class)</h4>
        <div class="leaderboard-table-wrap">
          <table class="leaderboard-table leaderboard-exploratory-table">
            <thead>
              <tr>
                <th class="leaderboard-rank">Rank</th>
                <th>Model</th>
                <th>F1</th>
                <th>Acc</th>
              </tr>
            </thead>
            <tbody>
              <tr class="leaderboard-row-top">
                <td class="leaderboard-rank">1</td>
                <td class="leaderboard-model">CLAP</td>
                <td class="leaderboard-primary">0.3540</td>
                <td class="leaderboard-best">0.3897</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">2</td>
                <td class="leaderboard-model">TimeConv-CNN</td>
                <td>0.3087</td>
                <td>0.3215</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">3</td>
                <td class="leaderboard-model">SEEG-NET</td>
                <td>0.1081</td>
                <td>0.1853</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="leaderboard-subtask">
        <h4>Ictal Period</h4>
        <div class="leaderboard-table-wrap">
          <table class="leaderboard-table leaderboard-exploratory-table">
            <thead>
              <tr>
                <th class="leaderboard-rank">Rank</th>
                <th>Model</th>
                <th>F1</th>
                <th>Acc</th>
              </tr>
            </thead>
            <tbody>
              <tr class="leaderboard-row-top">
                <td class="leaderboard-rank">1</td>
                <td class="leaderboard-model">CLAP</td>
                <td class="leaderboard-primary">0.9245</td>
                <td class="leaderboard-best">0.9323</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">2</td>
                <td class="leaderboard-model">TimeConv-CNN</td>
                <td>0.8533</td>
                <td>0.8720</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">3</td>
                <td class="leaderboard-model">SEEG-NET</td>
                <td>0.7526</td>
                <td>0.7624</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <div class="leaderboard-subtask">
        <h4>Sleep-Awake</h4>
        <div class="leaderboard-table-wrap">
          <table class="leaderboard-table leaderboard-exploratory-table">
            <thead>
              <tr>
                <th class="leaderboard-rank">Rank</th>
                <th>Model</th>
                <th>F1</th>
                <th>Acc</th>
              </tr>
            </thead>
            <tbody>
              <tr class="leaderboard-row-top">
                <td class="leaderboard-rank">1</td>
                <td class="leaderboard-model">CLAP</td>
                <td class="leaderboard-primary">0.7225</td>
                <td class="leaderboard-best">0.9331</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">2</td>
                <td class="leaderboard-model">TimeConv-CNN</td>
                <td>0.7118</td>
                <td>0.9291</td>
              </tr>
              <tr>
                <td class="leaderboard-rank">3</td>
                <td class="leaderboard-model">SEEG-NET</td>
                <td>0.6773</td>
                <td>0.6421</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <p class="leaderboard-caption">Source: Table 8 in the Omni-iEEG paper.</p>
  </section>
</div>
