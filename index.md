Here is the complete solution for your Assignment 6.2 — Backgrounds, Borders & Display. It includes the external stylesheet (styles.css) and the sample webpage (index.html) featuring three distinct card designs (Basic, Standard, Premium) and a practical demonstration of display properties and sizing constraints.

1. The Stylesheet (styles.css)
Save this file as styles.css. It defines distinct backgrounds, borders, border-radius, sizing (width, height, max-width), and the requested display property examples.

CSS
/* ==========================================
   Global & Base Styles
   ================================---------- */
body {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background-color: #f8fafc;
  color: #1e293b;
  margin: 0;
  padding: 2rem;
  line-height: 1.5;
}

h1, h2 {
  text-align: center;
  color: #0f172a;
}

h1 {
  margin-bottom: 2rem;
}

/* ==========================================
   Steps 1, 2, 3, 4 & 6: Cards Container & Sizing
   ================================---------- */
.cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 3rem;
}

/* Base Card Styles (Shared properties, border-radius, width/max-width) */
.card {
  width: 100%;                  /* Fluid base */
  max-width: 320px;             /* Step 6: max-width constraint */
  min-height: 380px;            /* Step 6: height constraint */
  padding: 2rem;
  border-radius: 16px;          /* Step 4: Rounded corners */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  transition: transform 0.2s ease;
}

.card:hover {
  transform: translateY(-4px);
}

.card h3 {
  margin-top: 0;
  font-size: 1.5rem;
}

.card p {
  color: #64748b;
  font-size: 0.95rem;
}

/* Card Buttons */
.card-btn {
  background-color: #0f172a;
  color: #ffffff;
  border: none;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  font-weight: 600;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  transition: background-color 0.2s;
}

.card-btn:hover {
  background-color: #334155;
}

/* Step 3: Distinct Backgrounds and Borders for Each Card */

/* 1. Basic Card */
.card-basic {
  background-color: #ffffff;
  border: 2px solid #cbd5e1;    /* Subtle grey border */
}

/* 2. Standard Card */
.card-standard {
  background-color: #f0fdf4;    /* Light mint background */
  border: 2px solid #10b981;    /* Emerald green border */
}
.card-standard .card-btn {
  background-color: #10b981;
}
.card-standard .card-btn:hover {
  background-color: #059669;
}

/* 3. Premium Card */
.card-premium {
  background-color: #faf5ff;    /* Light purple background */
  border: 2px solid #8b5cf6;    /* Vibrant purple border */
}
.card-premium .card-btn {
  background-color: #8b5cf6;
}
.card-premium .card-btn:hover {
  background-color: #7c3aed;
}


/* ==========================================
   Step 5: Display Property Demonstration
   ================================---------- */
.display-demo-section {
  background-color: #ffffff;
  padding: 2rem;
  border-radius: 12px;
  max-width: 900px;
  margin: 0 auto;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  border: 1px solid #e2e8f0;
}

.demo-box-container {
  margin-top: 1rem;
  padding: 1rem;
  background-color: #f8fafc;
  border-radius: 8px;
  border: 1px dashed #cbd5e1;
}

/* 1. Display: Block */
.demo-block {
  display: block;
  background-color: #fee2e2;
  border: 1px solid #ef4444;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
}

/* 2. Display: Inline */
.demo-inline {
  display: inline;
  background-color: #e0f2fe;
  border: 1px solid #0ea5e9;
  padding: 0.2rem 0.5rem;
  /* Note: width and height are ignored on inline elements */
}

/* 3. Display: Inline-Block */
.demo-inline-block {
  display: inline-block;
  width: 180px;                   /* Width respected */
  height: 50px;                   /* Height respected */
  background-color: #fef3c7;
  border: 1px solid #f59e0b;
  text-align: center;
  line-height: 50px;
  margin-right: 10px;
}
2. The Webpage (index.html)
Save this file as index.html in the same folder as styles.css.

HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 6.2 — Backgrounds, Borders & Display</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <h1>Subscription Plans & Layout Demo</h1>

  <!-- Steps 1, 2, 3, 4, 6: Three Styled Cards -->
  <div class="cards-container">
    
    <!-- Basic Card -->
    <section class="card card-basic">
      <div>
        <h3>Basic Plan</h3>
        <p>Essential features for personal use. Includes basic community access and standard updates.</p>
      </div>
      <a href="#" class="card-btn">Choose Basic</a>
    </section>

    <!-- Standard Card -->
    <section class="card card-standard">
      <div>
        <h3>Standard Plan</h3>
        <p>Great for professionals. Features priority support, advanced tools, and custom settings.</p>
      </div>
      <a href="#" class="card-btn">Choose Standard</a>
    </section>

    <!-- Premium Card -->
    <section class="card card-premium">
      <div>
        <h3>Premium Plan</h3>
        <p>Enterprise-grade power. Ultimate bandwidth, dedicated account manager, and all addons.</p>
      </div>
      <a href="#" class="card-btn">Choose Premium</a>
    </section>

  </div>

  <!-- Step 5: Display Property Practical Examples -->
  <section class="display-demo-section">
    <h2>Understanding Display Properties</h2>
    <p>Observe how different <code>display</code> values control element layout behavior:</p>

    <div class="demo-box-container">
      <h3>1. <code>display: block</code></h3>
      <p>Takes up the full available width, forcing a new line before and after.</p>
      <div class="demo-block">Block Element 1</div>
      <div class="demo-block">Block Element 2</div>

      <h3>2. <code>display: inline</code></h3>
      <p>Flows naturally with text content. Width and height properties are ignored.</p>
      <span class="demo-inline">Inline Span A</span>
      <span class="demo-inline">Inline Span B</span>

      <h3>3. <code>display: inline-block</code></h3>
      <p>Flows inline like text, but respects custom width, height, padding, and margins!</p>
      <div class="demo-inline-block">Box A (180px)</div>
      <div class="demo-inline-block">Box B (180px)</div>
    </div>
  </section>

</body>
</html>