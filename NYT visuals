Plot = require("@observablehq/plot")

topXG = [
  { PlayerId: "Y. Salech", xG: 17.391132 },
  { PlayerId: "N. Vasić", xG: 16.500718 },
  { PlayerId: "I. Kiese Thelin", xG: 14.697440 },
  { PlayerId: "I. Pittas", xG: 13.669651 },
  { PlayerId: "J. Bergström", xG: 11.098570 },
  { PlayerId: "E. Botheim", xG: 11.098303 },
  { PlayerId: "D. Islamović", xG: 11.005373 },
  { PlayerId: "A. Ahl-Holmström", xG: 10.550455 },
  { PlayerId: "C. Nyman", xG: 9.640865 },
  { PlayerId: "A. Boudah", xG: 8.731070 }
]

Plot.plot({
  width: 800,
  height: 540,
  marginTop: 70,
  marginLeft: 150,
  marginBottom: 60,
  x: {
    label: "Expected Goals (xG)",
    labelAnchor: "center",
    ticks: 5,
    tickFormat: d => d.toFixed(1)
  },
  y: {
    domain: topXG.map(d => d.PlayerId),
    label: null
  },
  style: {
    fontFamily: "Helvetica Neue, Arial, sans-serif",
    fontSize: 13,
    background: "#ffffff",
    color: "#222"
  },
  marks: [
    // Bars: flat, NYT-style neutral gray
    Plot.barX(topXG, {
      x: "xG",
      y: "PlayerId",
      fill: "#444",
      rx: 0
    }),

    // Clean text just after bar
    Plot.text(topXG, {
      x: d => d.xG + 0.5,
      y: "PlayerId",
      text: d => d.xG.toFixed(2),
      dy: 3,
      anchor: "start",
      fill: "#111"
    }),

    // Title: plain, bold, and top-left
    Plot.text([null], {
      text: ["Top xG Performers — Allsvenskan 2024"],
      frameAnchor: "top",
      fontSize: 18,
      fontWeight: "bold",
      dy: -40,
      anchor: "start"
    }),

    // Subtitle: subtle, smaller, tighter line height
    Plot.text([null], {
      text: ["Expected goals accumulated by players through December 2024"],
      frameAnchor: "top",
      fontSize: 13,
      dy: -20,
      fill: "#555",
      anchor: "start"
    }),

    // Source note: classic NYT positioning, bottom-left
    Plot.text([null], {
      text: ["Source: Opta/StatsPerform, own xG-model · Chart: Marc Lamberts"],
      frameAnchor: "bottom-left",
      fontSize: 11,
      dy: 30,
      dx: 5,
      fill: "#888"
    })
  ]
})

