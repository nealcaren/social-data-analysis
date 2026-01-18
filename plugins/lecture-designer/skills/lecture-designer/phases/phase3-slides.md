# Phase 3: Slide Development

You are executing Phase 3 of the lecture design process. Your goal is to create visually effective slides in Quarto reveal.js format that support the speaker rather than replace them.

## Why This Phase Matters

In a large lecture hall, the slides are the visual anchor. But slides are not the lecture—they're visual aids. The goal is to reduce extraneous cognitive load so students can focus on understanding, not decoding cluttered visuals.

**Key Insight**: Audiences cannot read and listen simultaneously. When you show text-heavy slides, they read instead of listening to you.

> "If a slide contains more than 75 words, it has become a document, not a presentation." — Nancy Duarte

> "No more than 6 words on a slide. EVER." — Seth Godin

## Inputs

Before starting, read:
1. All Phase 0-2 outputs
2. **`pedagogy/slide-design-guide.md`** - Comprehensive visual design principles
3. **`quarto/`** - Quarto reveal.js syntax reference

## Your Tasks

### 1. Apply Mayer's Multimedia Principles

For every slide, apply these evidence-based principles:

| Principle | What It Means | How to Apply |
|-----------|---------------|--------------|
| **Coherence** | Remove extraneous material | No decorative images, minimal text |
| **Signaling** | Highlight key information | Use arrows, bolding, color strategically |
| **Segmenting** | Break into digestible units | One concept per slide, progressive reveal |
| **Redundancy** | Don't duplicate channels | Don't read bullet points aloud |
| **Spatial Contiguity** | Keep related items close | Labels on diagrams, not in legend |
| **Temporal Contiguity** | Narrate with visuals | Speak as visuals appear |

### 2. Design for Accessibility

**Font Sizes (for large lecture halls):**
- Headings: 32pt minimum, prefer 44pt
- Body text: 24pt minimum
- Captions/labels: 20pt minimum

**Contrast:**
- High contrast ratios (dark on light OR light on dark)
- Avoid red/green combinations (colorblindness)
- Test: Can you read it from the back row?

**Visual Descriptions:**
- Describe all images verbally ("As you can see in this graph, the trend...")
- Don't say "As you can see here..." without describing what's there

### 3. Slide Types and Templates

**Title Slide**
```markdown
---
title: "Lecture Title"
subtitle: "Course Name"
author: "Instructor Name"
date: "Date"
format: revealjs
---
```

**Section Header**
```markdown
# Section Title {background-color="#2a4d6e"}
```

**Content Slide**
```markdown
## Slide Title

- Point one
- Point two
- Point three

::: {.notes}
Speaker notes go here with timing cues and delivery notes.
:::
```

**Two-Column Slide**
```markdown
## Comparison

:::: {.columns}
::: {.column width="50%"}
**Option A**

- Feature 1
- Feature 2
:::

::: {.column width="50%"}
**Option B**

- Feature 1
- Feature 2
:::
::::
```

**Incremental Reveal**
```markdown
## Key Points

::: {.incremental}
- First point (appears first)
- Second point (appears on click)
- Third point (appears on click)
:::
```

**Image Slide**
```markdown
## {background-image="path/to/image.jpg"}

::: {.notes}
Full-bleed image. Describe: "This image shows..."
:::
```

**Poll Slide**
```markdown
## Poll: [Question]

What do you think explains [phenomenon]?

A) Option A
B) Option B
C) Option C
D) Option D

::: {.notes}
**Protocol:**
1. Display question (1 min)
2. Individual silent vote (1 min)
3. Check distribution
4. Peer discussion if 30-70% correct (3 min)
5. Re-vote (1 min)
6. Explain answer (2 min)
:::
```

### 4. Write Speaker Notes

Every slide should have speaker notes including:

**Content:**
- What to SAY (not what's on the slide)
- Key points to emphasize
- Examples or stories to tell
- Transitions to next slide

**Logistics:**
- Timing (e.g., "2 minutes on this slide")
- Activity cues (e.g., "Launch poll now")
- Movement cues (e.g., "Move to center stage")

**Example:**
```markdown
::: {.notes}
**Time:** 2 minutes

**Key point:** Emphasize that this mechanism explains the paradox from the hook.

**Say:** "Remember our opening puzzle about X? This is the answer. The reason Y happens is because..."

**Transition:** After explaining, launch Poll 2.
:::
```

### 5. Create the Slide Deck Structure

For a 75-minute lecture, approximately 30-40 slides:

```
slides.qmd
├── Title slide
├── Hook/Opening
│   ├── Mystery/problem statement
│   └── Baseline poll
├── Chunk 1 (5-7 slides)
│   ├── Key concept slides
│   └── ConcepTest poll
├── Chunk 2 (5-7 slides)
│   ├── Key concept slides (hardest material)
│   └── State change activity
├── Chunk 3 (4-6 slides)
│   ├── Application slides
│   └── Synthesis activity
├── Summary
│   ├── Return to hook
│   └── Key takeaways
└── Closing
    ├── Muddiest point
    └── Next steps
```

### 6. Visual Design Principles

See **`pedagogy/slide-design-guide.md`** for comprehensive guidance. Key principles:

**The Numbers That Matter:**
- **75-word limit**: More than 75 words = it's a document
- **6-word rule**: Aim for 6 words or fewer per slide (Godin/Reynolds)
- **3-second test**: Audiences must grasp content within 3 seconds
- **28pt minimum font**: Never smaller for keynotes

**CRAP Framework (Reynolds):**
- **Contrast**: Make different things VERY different
- **Repetition**: Consistent style throughout
- **Alignment**: Use invisible grid lines
- **Proximity**: Group related items; separate unrelated

**Simplicity:**
- One idea per slide
- Maximum 6 words per slide (aspiration), 6 lines absolute max
- Use full-bleed images when possible
- Empty space is a design element, not wasted space
- Remove logos from all but first/last slides

**The Picture Superiority Effect:**
- Hear information → remember 10% after 3 days
- Add a picture → remember 65% after 3 days
- **Images = 6x more memorable than words alone**

**Signal-to-Noise Ratio:**
Remove these distractions:
- Decorative backgrounds
- 3D effects on charts
- Unnecessary gridlines
- Clip art (always)
- Gradient fills and drop shadows

**Visual Hierarchy:**
- Largest = most important
- Color draws attention
- Position matters (top-left is read first)

## Output Files to Create

1. **slides.qmd** - The complete Quarto reveal.js slide deck with:
   - All slides with proper formatting
   - Speaker notes for every slide
   - Timing cues
   - Activity markers

2. **slide-inventory.md** - List of all slides with:
   - Slide number and title
   - Approximate time
   - Purpose (content, poll, transition, etc.)
   - Learning outcome alignment

3. **visual-assets.md** - List of needed visuals:
   - Images to source or create
   - Diagrams to build
   - Charts to generate

4. **phase3-report.md** - Executive summary including:
   - Total slide count
   - Time per section
   - Any slides that need instructor review
   - Visual assets needed

## Quarto reveal.js Quick Reference

**YAML Header:**
```yaml
---
title: "Lecture Title"
format:
  revealjs:
    theme: default
    slide-number: true
    transition: slide
---
```

**Speaker Notes:**
```markdown
::: {.notes}
Notes here
:::
```

**Incremental Lists:**
```markdown
::: {.incremental}
- Item 1
- Item 2
:::
```

**Fragments (appear on click):**
```markdown
::: {.fragment}
This appears on click
:::
```

**Columns:**
```markdown
:::: {.columns}
::: {.column width="50%"}
Left content
:::
::: {.column width="50%"}
Right content
:::
::::
```

## Guiding Principles

1. **Slides support, not replace**: The speaker is the presentation; slides are visual aids.

2. **One idea per slide**: If you need more, make more slides.

3. **No full sentences**: Bullet points are cues, not scripts.

4. **Big enough for the back row**: If in doubt, make it bigger.

5. **Speaker notes are essential**: They make the deck usable by anyone.

6. **Progressive reveal**: Don't dump everything at once.

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that slides.qmd was created
2. Total slide count and estimated timing
3. List of visual assets needed
4. Any slides that need special attention
5. Questions for the instructor about visual preferences
