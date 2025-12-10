# Midjourney Prompt Framework

## A structured approach to consistent, high-quality generation

---

## Core Prompt Architecture

```
[SUBJECT] + [STYLE/MEDIUM] + [MOOD/ATMOSPHERE] + [TECHNICAL PARAMETERS]
```

### Example:
```
Portrait of a woman in her 30s, editorial fashion photography, 
natural light, confident expression, minimalist composition, 
shallow depth of field --ar 2:3 --v 6.1 --style raw
```

---

## Component Breakdown

### 1. SUBJECT (What to Generate)

**Be specific but not prescriptive:**
- ✅ "Woman in her 30s wearing a white blazer"
- ❌ "Woman with exactly 3 buttons on blazer, hair 14 inches long"

**Composition guidance:**
- "Close-up portrait"
- "Full body shot"
- "Environmental portrait with context"
- "Product-focused composition"

**Action/pose (if relevant):**
- "Laughing naturally"
- "Professional pose, hands clasped"
- "Mid-stride, dynamic movement"

---

### 2. STYLE/MEDIUM

**Photography styles:**
- "Editorial fashion photography"
- "Documentary street photography"
- "Studio product photography"
- "Cinematic film still"
- "Architectural photography"

**Illustration styles:**
- "Flat vector illustration"
- "Hand-drawn pencil sketch"
- "Watercolor painting"
- "3D rendered illustration"
- "Isometric technical drawing"

**Art movements:**
- "Art nouveau poster design"
- "Bauhaus geometric composition"
- "Impressionist painting style"
- "Cyberpunk aesthetic"

**Specific artists (use thoughtfully):**
- "In the style of [Artist Name]"
- *Note: Consider copyright/ethics implications*

---

### 3. MOOD/ATMOSPHERE

**Lighting:**
- "Golden hour natural light"
- "Dramatic chiaroscuro lighting"
- "Soft diffused studio lighting"
- "Neon-lit urban environment"
- "Overcast grey light"

**Color palette:**
- "Muted earth tones"
- "Vibrant saturated colors"
- "Monochromatic blue palette"
- "Warm amber and ochre tones"
- "High contrast black and white"

**Emotional tone:**
- "Optimistic and energetic"
- "Contemplative and serene"
- "Mysterious and moody"
- "Playful and whimsical"

---

### 4. TECHNICAL PARAMETERS

#### Essential Parameters:

**--ar [ratio]** (Aspect Ratio)
- `--ar 16:9` → Landscape (presentations, web banners)
- `--ar 1:1` → Square (Instagram feed, profile images)
- `--ar 2:3` or `--ar 4:5` → Portrait (Instagram story, print ads)
- `--ar 21:9` → Ultra-wide (cinematic, hero images)

**--v [version]** (Model Version)
- `--v 6.1` → Latest model (recommended default)
- `--v 6` → Previous stable version
- `--v 5.2` → If you need v5 aesthetic

**--style [raw/default]**
- `--style raw` → Less "Midjourney aesthetic", more realistic
- Default → More opinionated, artistic interpretation

#### Advanced Parameters:

**--chaos [0-100]** (Variation degree)
- `--chaos 0` → Very consistent results
- `--chaos 25` → Moderate variation (good for exploration)
- `--chaos 50-100` → High variation (brainstorming phase)

**--stylize [0-1000]** (Artistic interpretation)
- `--stylize 0` → Very literal prompt interpretation
- `--stylize 100` → Default, balanced
- `--stylize 500-1000` → Strong artistic interpretation
- *Lower values for brand-specific work*

**--quality [.25, .5, 1, 2]** (Render quality)
- `--q .25` → Fast drafts
- `--q 1` → Default (recommended)
- `--q 2` → Highest quality (2x cost, diminishing returns)

**--seed [number]** (Reproducibility)
- Use same seed for consistent base compositions
- Example: `--seed 12345`
- *Critical for iterating on approved directions*

**--no [element]** (Negative prompting)
- `--no people` → Exclude people from scene
- `--no text` → Avoid text in image
- `--no watermark` → Reduce "signature" elements

#### Weights and Multi-prompts:

```
Element one::2 element two::1
```
- Higher numbers = stronger influence
- Useful for balancing competing concepts

---

## Iterative Refinement Strategy

### Phase 1: Broad Exploration (Chaos 25-50)
```
/imagine sustainable fashion campaign, modern minimalist aesthetic, 
natural materials, earth tones --ar 16:9 --chaos 35 --v 6.1
```

Generate 4 options, identify strongest direction.

### Phase 2: Direction Locking (Capture seed)
```
/imagine [refined prompt based on Phase 1] --seed [number from best result]
```

Generate variations with locked seed, test small prompt adjustments.

### Phase 3: Production Consistency (Chaos 0-10)
```
/imagine [locked prompt] --seed [number] --chaos 0
```

Generate finals with maximum consistency.

---

## Use Case Examples

### Use Case: Brand Campaign Hero Image

**Brief:** Sustainable tech startup, needs hero image for homepage. Clean, modern, approachable.

**Iteration 1 (Exploration):**
```
Modern office space with natural light, sustainable design elements,
plants integrated with technology, soft color palette, editorial 
photography style --ar 16:9 --v 6.1 --chaos 30
```

**Iteration 2 (Refined):**
```
Bright open-plan office with floor-to-ceiling windows, young professionals
collaborating at wooden desk, abundant potted plants, laptop screens
showing data visualizations, natural morning light, architectural
photography, clean composition --ar 16:9 --v 6.1 --style raw --chaos 15
```

**Iteration 3 (Production):**
```
[Same as Iteration 2] --seed 45782 --chaos 5 --q 1
```

### Use Case: Social Media Asset Series

**Brief:** 6 Instagram carousel slides about product features, consistent style.

**Master Prompt Template:**
```
[FEATURE DESCRIPTION], flat lay product photography, minimalist 
white background, soft shadows, studio lighting, clean commercial 
aesthetic --ar 1:1 --v 6.1 --style raw --seed 88234 --chaos 0
```

**Applied:**
- Slide 1: `Smartphone with glowing screen, [rest of template]`
- Slide 2: `Smartphone with earbuds beside it, [rest of template]`
- Slide 3: `Smartphone charging on wireless pad, [rest of template]`

*Locked seed ensures visual consistency across series*

### Use Case: Concept Pitch Illustrations

**Brief:** 3 futuristic concept illustrations for investor deck.

**Exploration Prompt (high chaos for bold ideas):**
```
Futuristic city with organic architecture, biomimetic design, 
sustainable technology integrated with nature, concept art style, 
cinematic lighting, sense of wonder --ar 16:9 --v 6.1 --chaos 60 --stylize 400
```

*Use high chaos to generate diverse concepts, then refine the most exciting direction*

---

## Common Pitfalls & Solutions

### Pitfall 1: Generic "AI Look"
❌ Problem: Overly polished, uncanny valley aesthetic  
✅ Solution: Use `--style raw`, lower `--stylize` value, add specific photographic references

### Pitfall 2: Inconsistent Series
❌ Problem: Assets look unrelated despite similar prompts  
✅ Solution: Lock `--seed` value, reduce `--chaos`, use precise repeated language

### Pitfall 3: Overcomplicating Prompts
❌ Problem: 200-word prompts that confuse the model  
✅ Solution: Keep prompts focused, 20-50 words, test incremental additions

### Pitfall 4: Ignoring Aspect Ratio Until Later
❌ Problem: Perfect image, wrong format for use case  
✅ Solution: Always specify `--ar` from first generation

### Pitfall 5: Not Documenting Winning Prompts
❌ Problem: Can't recreate successful results  
✅ Solution: Copy/paste every successful prompt into project notes

---

## Agency Production Tips

### Tip 1: Create Prompt Libraries
Build a spreadsheet of tested prompts organized by:
- Client/industry
- Visual style
- Use case (hero image, social, print)
- Parameters that worked

### Tip 2: Seed Management
When a client approves a direction:
1. Note the seed value
2. Test 5-10 generations with that seed
3. Confirm consistency before scaling up
4. Document in project files

### Tip 3: Batch Similar Assets
If generating 10 product shots:
- Create a prompt template with [PRODUCT] variable
- Generate all in same session
- Use seed + low chaos for consistency

### Tip 4: Client Collaboration
Share Midjourney links with clients:
- They can see generation history
- Transparency builds trust
- Easy to reference specific options

### Tip 5: Upscaling Strategy
For print/high-res needs:
1. Generate at largest native resolution
2. Use Midjourney's upscale features
3. Consider external upscalers (Topaz Gigapixel)
4. Always test print output at actual size

---

## Prompt Recipes for Common Needs

### Professional Portrait
```
Professional headshot of [description], neutral grey background,
even studio lighting, shallow depth of field, direct eye contact,
confident expression --ar 2:3 --v 6.1 --style raw
```

### Lifestyle Product Photo
```
[Product] in [lifestyle context], natural window light, modern 
interior styling, depth of field, editorial photography, warm 
color grading --ar 4:5 --v 6.1 --style raw
```

### Abstract Concept Visualization
```
Abstract representation of [concept], [color palette], geometric 
forms, [artistic movement], clean composition, conceptual 
illustration --ar 16:9 --v 6.1 --stylize 200
```

### Brand Pattern/Texture
```
Seamless repeating pattern, [theme/motif], [color scheme], 
[style reference], tileable design, clean vector aesthetic 
--ar 1:1 --v 6.1 --tile
```

### Social Media Story Template
```
[Content description], mobile-first vertical composition, bold 
typography placement area, [brand colors], modern graphic design,
Instagram story aesthetic --ar 9:16 --v 6.1
```

---

## Advanced: Multi-Prompt Weighting

For complex compositions, use weights to balance elements:

```
sustainable architecture::2 lush vegetation::1.5 modern interiors::1
```

This tells Midjourney:
- Prioritize architectural elements (weight 2)
- Strong vegetation presence (weight 1.5)
- Interior details as supporting context (weight 1)

Useful when one element keeps dominating inappropriately.

---

## When to Move to ComfyUI

Midjourney is excellent for exploration, but migrate to ComfyUI when you need:
- Exact control over specific elements
- Batch generation with precise consistency
- Integration with other technical workflows
- Custom model training/fine-tuning

See `/workflows/comfyui/` for production workflow guidance.

---

## Resources & Community

- **Official Docs:** https://docs.midjourney.com
- **Prompt Craft:** Community prompt sharing
- **Version Testing:** Always test new versions before production use
- **Parameter Experimentation:** Budget time for testing, it pays off

---

**Remember:** Prompting is both art and science. Document what works, iterate systematically, and build your prompt library over time.
