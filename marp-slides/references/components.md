# HTML Component Patterns

Add the following CSS and HTML as needed. All font sizes use `em` relative to the base.

## Table of Contents

- [Pipeline (Process Flow)](#pipeline-process-flow)
- [Progress Bar (Stage Indicator)](#progress-bar-stage-indicator)
- [Color-coded Cards (Category Comparison)](#color-coded-cards-category-comparison)
- [Before/After 2-Column](#beforeafter-2-column)
- [KPI Cards (Side-by-side Metrics)](#kpi-cards-side-by-side-metrics)
- [Flow Diagram (Causal/Cyclic)](#flow-diagram-causalcyclic)
- [Checklist](#checklist)
- [Action Cards (Dark Background)](#action-cards-dark-background)

---

## Pipeline (Process Flow)

```css
.pipeline { display: flex; gap: 6px; margin: 8px 0 20px; }
.pipeline .step {
  flex: 1; text-align: center; padding: 12px 4px; border-radius: 6px;
  font-size: 0.85em; font-weight: 600; background: #e8f4e8; color: #2d6a2d;
}
.pipeline .step.warn {
  background: #fff0e0; color: #c45e00; border-bottom: 3px solid #e8820c;
}
```
```html
<div class="pipeline">
  <div class="step warn">Step 1</div>
  <div class="step">Step 2</div>
  <div class="step warn">Step 3</div>
</div>
```

## Progress Bar (Stage Indicator)

```css
.progress { display: flex; gap: 0; margin: 8px 0 20px; }
.progress .state {
  flex: 1; text-align: center; padding: 16px 8px; font-size: 0.82em; font-weight: 600;
  background: #f0f0f0; color: #999; border-right: 2px solid #fff;
}
.progress .state.active {
  background: linear-gradient(135deg, #ff9a56, #e8820c); color: #fff; border-radius: 6px;
}
.progress .state.next {
  background: linear-gradient(135deg, #ffd89b, #ff9a56); color: #fff; border-radius: 6px;
}
```

## Color-coded Cards (Category Comparison)

```css
.cards { display: flex; gap: 14px; margin: 8px 0 20px; }
.cards .card { flex: 1; padding: 18px; border-radius: 8px; }
.cards .card.green { background: #e8f5e9; border-left: 4px solid #4caf50; }
.cards .card.yellow { background: #fff8e1; border-left: 4px solid #ff9800; }
.cards .card.red { background: #fce4ec; border-left: 4px solid #e53935; }
.cards .card strong { display: block; margin-bottom: 6px; font-size: 0.95em; }
.cards .card span { font-size: 0.88em; color: #444; }
```

## Before/After 2-Column

```css
.compare { display: flex; gap: 20px; margin: 8px 0 16px; }
.compare .col { flex: 1; padding: 16px 20px; border-radius: 8px; }
.compare .before { background: #fce4ec; }
.compare .after { background: #e8f5e9; }
.compare .col h3 { margin: 0 0 10px; font-size: 0.95em; }
.compare .col ul { margin: 0; padding-left: 20px; }
.compare .col li { margin-bottom: 6px; font-size: 0.9em; }
```

## KPI Cards (Side-by-side Metrics)

```css
.kpi-row { display: flex; gap: 14px; margin: 8px 0; }
.kpi-row .kpi {
  flex: 1; text-align: center; padding: 14px 8px; border-radius: 8px; background: #e3f2fd;
}
.kpi-row .kpi strong { display: block; font-size: 0.9em; color: #1565c0; margin-bottom: 4px; }
.kpi-row .kpi span { font-size: 0.85em; color: #333; }
```

## Flow Diagram (Causal/Cyclic)

```css
.flow { display: flex; align-items: center; justify-content: center; gap: 0; margin: 16px 0; flex-wrap: wrap; }
.flow .node { padding: 8px 16px; border-radius: 6px; font-weight: 600; font-size: 0.85em; background: #fce4ec; color: #c62828; }
.flow .arrow { font-size: 1.1em; color: #999; margin: 0 8px; }
```

## Checklist

```css
.checklist .item {
  display: flex; gap: 16px; padding: 10px 0;
  border-bottom: 1px solid #eee; align-items: baseline;
}
.checklist .item:last-child { border-bottom: none; }
.checklist .task { font-weight: 600; min-width: 260px; flex-shrink: 0; }
.checklist .done { color: #666; }
```

## Action Cards (Dark Background)

```css
.actions { display: flex; gap: 20px; margin-top: 32px; }
.actions .action {
  flex: 1; padding: 28px 20px; border-radius: 12px; background: #fff;
  text-align: center; color: #1a1a2e;
}
.actions .action .num { display: block; font-size: 1.8em; font-weight: 700; color: #1a1a2e; margin-bottom: 10px; }
.actions .action .text { font-size: 0.95em; color: #333; line-height: 1.5; }
```
