# Stubble Vector Field

Little animated figures whose stubble is a live vector field. Each hair is a damped cantilever anchored to deforming skin, so jaw muscles (chewing, talking, chattering, clenching, yawning) and wind (with turbulence and travelling gusts) both show up as hair motion.

Open `index.html` in any browser. There is nothing to install or build.

## Controls

The page has two views.

- **Forecast** (front page): the three heads, a live readout of wind, gusts, jaw activity and peak bend, 12 condition presets, a box to describe your own condition, and two stubble sliders (length and beard area). With an Anthropic API key, `claude-haiku-4-5` turns the description into strict-JSON force parameters. The key stays in your browser and is sent only to api.anthropic.com. Without a key, a local keyword guesser fills in the same parameters.
- **The Details**: every force parameter as an editable field, the finer stubble settings (regions, softness as effective keratin modulus, density in hairs/cm²), display options (bending and skin magnification, hair glyph length, colour mode), live physics numbers for any one figure, the language model settings, and the full write-up of how the forces are computed.

## Honest scale

Short stubble barely bends in wind (about 0.1° at 10 m/s for 3 mm hair), so air bending is drawn magnified and the factor is always on screen. Skin motion is drawn at true scale. *True scale* shows the raw field.

## Physics

- **Hair:** rigid rod on a rotational spring (κ = 3EI/L, I = πD⁴/64, J = mL²/3), integrated exactly as a damped oscillator.
- **Skin:** mandible rotation about the TMJ with condylar glide, lateral shift, masseter bulge, lip spread and pucker.
- **Air:** potential flow over head and neck, separation and wake buffeting, boundary-layer and canopy attenuation, cylinder drag Cd = 1 + 10·Re^(-2/3), frozen Kolmogorov turbulence, and Poisson gusts.

Every equation and constant, with estimates flagged, is in the page's *How the forces are computed* panel and at the top of the source.

## License

MIT
