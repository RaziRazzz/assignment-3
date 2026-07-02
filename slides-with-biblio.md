---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>

:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}

### Statistical Analysis: ANOVA Results

Using ANOVA, we assessed the impact of Pressure (P) and Temperature (T) on Part Resistance for Machine 1. A significance level ($lpha$) of 0.05 was used.

**Key Findings:**

- **Pressure (P):**
  - Pr(>F): 0.0000
  - Conclusion: Significant
- **Temperature (T):**
  - Pr(>F): 0.0005
  - Conclusion: Significant
- **Interaction (P*T):**
  - Pr(>F): 0.5558
  - Conclusion: Not Significant

**ANOVA Summary Table:**
```
                           Df Sum Sq Mean Sq  F value   Pr(>F)    
Pressure_f                  2  507.8  253.91 3066.480  < 2e-16 ***
Temperature_f               2    1.3    0.63    7.611 0.000511 ***
Pressure_f:Temperature_f    4    0.2    0.06    0.753 0.555837    
Residuals                1791  148.3    0.08                      
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```

::: {.notes}
- Both pressure and temperature individually have a statistically significant effect on the part resistance.
- The interaction between pressure and temperature is not statistically significant, meaning their combined effect isn't more or less than their individual effects combined.
- The very low p-value for pressure (< 2e-16) suggests a strong influence.
:::

:::

::: {.column width="50%"}

### Part Resistance by Temperature and Pressure

<iframe 
  data-src="media/plots/boxplot_resistance_machine1.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>

:::
::::


---
# Bibliography
<div id="refs"></div>
