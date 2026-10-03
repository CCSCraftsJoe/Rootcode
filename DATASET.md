# Rootcode Dataset Convention

Recommended labels for every Rootcode machine-vision image:

- `rootcode_version` — e.g. `1.0.0`
- `plaintext` — uppercase A–Z ground truth
- `source` — e.g. `synthetic`, `print`, `vinyl`, `sculpture`, `screen`
- `split` — `train`, `validation`, or `test`

Optional metadata may include rotation, perspective, illumination, background, occlusion, capture device, and physical medium.

```json
{
  "file": "images/000001.png",
  "rootcode_version": "1.0.0",
  "plaintext": "KAIROSOMA",
  "source": "synthetic",
  "split": "train"
}
```

## Benchmark integrity

Keep benchmark/test images out of training splits. For zero-knowledge model tests, retain a private set of previously unpublished physical captures and disclose them only after evaluation.

## Variation guidance

Useful variation includes uniform scale, camera rotation, perspective distortion, uneven illumination, blur, print/vinyl artifacts, textured backgrounds, occlusion, glare, and crop error. Synthetic images should supplement, not replace, real physical captures.

Project-produced datasets are CC BY 4.0 unless otherwise noted. Third-party material must carry compatible rights and provenance.
