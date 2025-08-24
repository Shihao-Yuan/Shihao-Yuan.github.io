---
layout: page
title: Full Waveform Inversion (FWI)
description: Localized FWI algorithm for high-frequency seismic inversion with reduced computational cost
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

## Project Overview

I have developed a **localized Full Waveform Inversion (FWI) algorithm** that performs iterative modeling locally, allowing us to extend inversions for higher frequencies with minimal computational effort. This approach is particularly valuable for **time-lapse seismic applications** where changes in elastic parameters are localized due to fluid extraction and injection in the subsurface.

## Motivation

Seismic full-waveform inversion (FWI) is a powerful method used to estimate the elastic properties of the subsurface. To mitigate the nonlinearity and cycle-skipping problems, in a hierarchical manner, one first inverts the low-frequency content to determine long- and medium wavelength structures and then increases the frequency content to obtain detailed information.

However, the inversion of higher frequencies can be computationally very expensive, especially when the target of interest, such as oil/gas reservoirs and axial melt lens, is at a great depth, far away from source and receiver arrays.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="Baseline survey" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="Time-lapse survey" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    **Figure 1. Target-oriented full waveform inversion.** Left: Baseline survey with full receiver coverage. Right: Time-lapse survey with reduced target area for small-scale structures.
</div>

## Methodology

The proposed localized FWI algorithm addresses computational challenges through a two-stage approach:

### Stage 1: Low-Frequency Full-Model Inversion
- Establishes a baseline model representing long-to-medium wavelength features
- Uses conventional full-model elastic waveform inversion
- Provides the foundation for subsequent localized processing

### Stage 2: High-Frequency Localized Inversion
- Sources and receivers are extrapolated to regions near the target area
- Enables local forward modeling and inversion
- Achieves high-frequency estimation with reduced computational cost

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/5.jpg" title="Schematic illustration of localized inversion" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="Processing sequences" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    **Figure 2 & 3.** Left: Schematic illustration of the proposed localized inversion in a layered model. Right: Processing sequences for high-frequency localized waveform inversion.
</div>

## Key Innovations

1. **Wavefield Injection**: Physical sources inject wavefields into localized regions of interest
2. **Wavefield Extrapolation**: Efficient extrapolation to both physical and virtual receivers
3. **Localized Processing**: Focused inversion on target areas reduces computational overhead
4. **Time-Lapse Optimization**: Particularly effective for monitoring subsurface changes

## Applications

- **Oil & Gas Reservoir Monitoring**: Track fluid movement and production changes
- **Geothermal Systems**: Monitor heat extraction and injection effects
- **Carbon Capture & Storage**: Verify CO₂ sequestration integrity
- **Mining Operations**: Assess structural stability and resource extraction

## Technical Implementation

The algorithm leverages:
- **Conjugate gradient optimization** for efficient convergence
- **Step-length calculation** for stable model updates
- **Green's function precomputation** for wavefield operations
- **Model interpolation** for seamless integration between scales

## Results & Validation

Numerical tests demonstrate that inverting low-frequency data for the overburden is sufficient to achieve an accurate high-frequency estimation of elastic parameters for the target region. This approach significantly reduces computational requirements while maintaining inversion quality.

## Related Publications

- **Yuan, S., Fuji, N., Singh, S., & Borisov, D. (2017).** Localized time-lapse elastic waveform inversion using wavefield injection and extrapolation: 2-D parametric studies. *Geophysical Journal International*, *209*(3), 1699-1717.

- **Yuan, S., Fuji, N., & Singh, S. C. (2021).** High-frequency localized elastic full-waveform inversion for time-lapse seismic surveys. *Geophysics*, *86*(3), R277-R292.

## Future Work

- Extension to 3D elastic media
- Integration with machine learning techniques
- Real-time processing capabilities
- Application to other geophysical inverse problems

---

*This project represents a significant advancement in computational geophysics, enabling high-resolution seismic imaging at reduced computational cost.*
