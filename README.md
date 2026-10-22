# mossimage-prompts
# MOSS-Image Prompt Collection

Tested and verified prompts for [MOSS-Image](https://arxiv.org/abs/2610.23374), the open-source 5B diffusion model. Every prompt in this repo has been run through MOSS-Image-SFT and confirmed to work.

👉 **[mossimage.run](https://mossimage.run)** — Try these prompts online, free, no setup.

---

## Text-to-Image

```
A serene mountain lake at sunrise, pine trees silhouetted against orange sky, photorealistic, 8K
```

```
Minimalist Japanese bedroom, tatami mats, sliding shoji doors, soft natural light, architectural photography
```

```
Close-up of a cat with heterochromia, one blue eye one green eye, soft fur texture, shallow depth of field, studio lighting
```

```
A steampunk airship floating above a Victorian city at dusk, warm copper tones, detailed illustration
```

---

## JSON Layout Control

MOSS-Image-SFT lets you control object placement with JSON instead of prompt engineering.

**Two objects:**

```json
{
  "canvas": {"width": 1024, "height": 1024},
  "objects": [
    {"label": "red ball", "position": [0.2, 0.5], "size": [0.3, 0.3]},
    {"label": "blue cube", "position": [0.8, 0.5], "size": [0.3, 0.3]}
  ],
  "style": "white background, studio lighting"
}
```

**Coffee and book:**

```json
{
  "canvas": {"width": 1024, "height": 1024},
  "objects": [
    {
      "label": "a cup of coffee on a wooden table",
      "position": [0.3, 0.5],
      "size": [0.4, 0.35],
      "detail": "ceramic white mug, steam rising, dark roast coffee"
    },
    {
      "label": "an open book next to the cup",
      "position": [0.55, 0.45],
      "size": [0.3, 0.35],
      "detail": "old leather-bound book, yellowed pages"
    }
  ],
  "style": "warm morning light, cozy cafe atmosphere, shallow depth of field"
}
```

**Three objects — tabletop still life:**

```json
{
  "canvas": {"width": 1024, "height": 1024},
  "objects": [
    {"label": "a glass vase with a single sunflower", "position": [0.25, 0.4], "size": [0.2, 0.45]},
    {"label": "a vintage brass pocket watch", "position": [0.55, 0.55], "size": [0.25, 0.25]},
    {"label": "a stack of three old hardcover books", "position": [0.8, 0.45], "size": [0.3, 0.35]}
  ],
  "style": "warm afternoon light from a window, dust particles in the air, painterly realism"
}
```

---

## Chinese Text Rendering

```
一张中文海报，标题"春日特卖"位于顶部，副标题"全场五折起"，背景是樱花盛开，清新风格
```

```
A poster with Chinese text "你好世界" in bold calligraphy at the center, ink wash painting style, white background
```

```
一家奶茶店的店面招牌，写着"珍珠奶茶"四个大字，霓虹灯风格，夜晚街景
```

---

## English Text Rendering

```
A neon sign that says "OPEN" in pink and blue glow, dark brick wall background, cyberpunk aesthetic, rainy street reflection
```

```
Product mockup of a white t-shirt with the text "LESS IS MORE" printed in Helvetica, front view, clean studio lighting
```

```
Chalkboard menu with "TODAY'S SPECIAL" written in elegant chalk lettering, rustic coffee shop background, warm tones
```

---

## Prompt Tips

- **Layout accuracy:** JSON layout is ~80% accurate on SFT. Natural language alone is ~40%. Use JSON when position matters.
- **Text rendering:** Tell the model what kind of text it is — "neon sign", "printed on paper", "chalkboard lettering". Context helps it render correctly.
- **Prompt length:** Shorter prompts often work better. The built-in enhancer fills in details. Start with 10–30 words.
- **Chinese + English mixed:** Quote the non-dominant language. The model handles mixed-language well.
- **Fixed seed:** For reproducible results, use a fixed seed and square aspect ratio. Change one variable at a time.
- **Model choice:** SFT for text rendering and layout. Base for general generation.

---

## Related

- [mossimage-workflow](https://github.com/YOUR_USERNAME/mossimage-workflow) — ComfyUI workflow JSON
- [mossimage.run/comfyui/](https://mossimage.run/comfyui/) — ComfyUI setup guide
- [MOSS-Image paper (arXiv)](https://arxiv.org/abs/2610.23374)
- [OpenMOSS on GitHub](https://github.com/OpenMOSS)

## Contribute

Submit a PR with your prompt. Include: category, model version (Base/SFT), a note on why it works, and an example image if possible.

## License

CC0 — public domain. Free to use, no attribution required.
