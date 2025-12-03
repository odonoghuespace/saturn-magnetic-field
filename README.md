# Saturn Magnetic Field Viewer

An interactive 3D web visualization of Saturn's magnetic field, featuring real magnetic field line traces computed using the **Cassini 11** spherical harmonic model.

🔗 **[Live Demo](https://YOUR_USERNAME.github.io/saturn-magnetic-field/)** *(update with your URL)*

![Saturn Magnetic Field](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Saturn_from_Hubble.jpg/300px-Saturn_from_Hubble.jpg)

## Features

- **Real magnetic field model**: Field lines are traced using the Cassini 11 spherical harmonic model, not a simplified dipole approximation
- **Interactive controls**: Adjust L-shell (1.1–30), number of longitude lines, and line thickness
- **Accurate Saturn representation**: Oblate spheroid (flattening = 0.902) with characteristic banded coloring
- **Ring system**: Realistic D, C, B, A, and F rings with Cassini Division
- **Enceladus**: Moon shown at correct orbital distance (3.948 Rs) with accurate relative orbital motion
- **45° latitude circles**: Visual reference for auroral regions

## Magnetic Field Model

This visualization uses the **Cassini 11** internal field model for Saturn, which is based on magnetometer data from the Cassini spacecraft's Grand Finale orbits (2017). The model represents Saturn's magnetic field using spherical harmonic coefficients up to degree and order 11.

### Model Reference

The field model is accessed via the [**JupiterMag / planetary_magfield_simple**](https://github.com/rjwilson-LASP/JupiterMag) Python package, which provides convenient access to various planetary magnetic field models.

**Specific model used:** `cassini11`

```python
from planetary_magfield_simple import get_field
Bx, By, Bz = get_field('cassini11', x, y, z)  # Cartesian coordinates in Rs
```

### Key References

- **Dougherty, M. K., et al. (2018)**, "Saturn's magnetic field revealed by the Cassini Grand Finale", *Science*, 362(6410). [DOI: 10.1126/science.aat5434](https://doi.org/10.1126/science.aat5434)

## Technical Details

- **Field line tracing**: Bidirectional RK4-style integration from equatorial starting points until reaching Saturn's surface (r < 1 Rs)
- **L-shells**: 54 values from L=1.1 to L=30 (0.1 steps to L=3, 0.5 steps to L=10, 1.0 steps to L=30)
- **Longitudes**: 24 field lines per L-shell (15° spacing)
- **Coordinate system**: Saturn-centered, rotation axis = z-axis (converted to Three.js y-up convention)

## Saturn Parameters

| Parameter | Value |
|-----------|-------|
| Equatorial radius | 60,268 km |
| Polar flattening | 0.902 |
| Rotation period | 10.656 hours |
| Enceladus orbit | 3.948 Rs (237,948 km) |
| Enceladus orbital period | 32.885 hours |

## Built With

- [Three.js](https://threejs.org/) v0.160.0 - 3D graphics library
- [planetary_magfield_simple](https://github.com/rjwilson-LASP/JupiterMag) - Planetary magnetic field models

## Author

James O'Donoghue

## License

MIT License
