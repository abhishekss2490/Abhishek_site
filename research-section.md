# Research section (removed from site 2026-07-05 — saved for future re-add)

Removed from `index.html` at Abhishek's request. He likes how this section was
presented, so everything needed to restore it exactly is preserved below.

## Content (as it read on the site)

> ### I work where *control theory meets learning* — provably safe, empirically fast, on real hardware.
>
> **Themes:** event-triggered control · multi-agent RL · safe learning-based control · robot fleets · hybrid systems
>
> **Now:** coordinating real multi-robot fleets at IISc, a quadrant-token coordinator validated across 100+ live OptiTrack runs.
>
> **Questions I'm chasing**
> - Can we *learn* an event-trigger's parameters without breaking its stability guarantees?
> - How do fleets of real robots coordinate in real time under conflict?
> - Where can learning safely replace hand-tuned control?

## Presentation

Two-column grid (`1.2fr 1fr`): left column has the numbered mono label, a large
`.big` headline with the saffron `<em>` accent, theme pills, and the mono "Now:" line;
right column is the warm-wash `.qbox` card with saffron arrows on each question.

## How to restore

1. The CSS is still in `index.html` (`#research .inner` grid rule, `.themes`, `.qbox`,
   plus the mobile override `@media` rule) — nothing to re-add there.
2. Re-insert the HTML block below between the Publications and Experience sections.
3. Re-add the nav link `<a data-go="research">Research</a>` after the Publications link.
4. Renumber the `.label` section numbers (`<span class="ln">NN</span>`) so they stay
   sequential: this section takes 03, and Experience/Projects/Education shift back to 04/05/06.

```html
  <!-- RESEARCH -->
  <section class="sec" id="research">
    <div class="inner">
      <div>
        <div class="label"><span class="ln">03</span>Research</div>
        <h2 class="big">I work where <em>control theory meets learning</em> — provably safe, empirically fast, on real hardware.</h2>
        <div class="themes"><span>event-triggered control</span><span>multi-agent RL</span><span>safe learning-based control</span><span>robot fleets</span><span>hybrid systems</span></div>
        <p class="now"><span class="k">Now:</span>coordinating real multi-robot fleets at IISc, a quadrant-token coordinator validated across 100+ live OptiTrack runs.</p>
      </div>
      <div class="qbox">
        <div class="k">Questions I'm chasing</div>
        <ul>
          <li>Can we <em>learn</em> an event-trigger's parameters without breaking its stability guarantees?</li>
          <li>How do fleets of real robots coordinate in real time under conflict?</li>
          <li>Where can learning safely replace hand-tuned control?</li>
        </ul>
      </div>
    </div>
  </section>
```
