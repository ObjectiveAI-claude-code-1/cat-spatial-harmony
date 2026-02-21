# cat-spatial-harmony

A scalar function that evaluates the spatial harmony between a cat and its environment in a photograph. It answers the question: *does the space around this cat serve it well?*

## Overview

Every photograph of a cat captures a relationship — between the animal and the world around it. The wall behind it, the floor beneath it, the open air above it, the objects beside it — all of these either contribute to the cat's presence or detract from it. **cat-spatial-harmony** quantifies that relationship, returning a score from 0 to 1 that reflects whether the environment acts as a stage for the cat or works against it.

A score near **1.0** means the photograph achieves strong spatial harmony: negative space feels intentional, background elements collaborate with the subject, and the cat commands its frame as the undeniable protagonist. A score near **0.0** means the environment has failed the subject — through visual chaos, spatial neglect, or compositional imbalance.

## Input

The function accepts a single required field:

| Field | Type | Required | Description |
|---|---|---|---|
| `photograph` | `image` | Yes | A photograph containing a cat. Any breed, any environment — indoors or outdoors, sparse or rich, orderly or chaotic, natural or artificial. The cat may be centered or off to one side. |

The photograph is the totality of the evidence. There is no metadata about photographer intent, no captions, no second image for comparison. The function evaluates what is visible and nothing more — mirroring how a viewer actually encounters a photograph.

## Output

A scalar value between **0** and **1**, where:

- **0.0** — The environment entirely fails the cat. Space feels neglectful, the background competes with or overwhelms the subject, and the cat does not feel like the protagonist of its own photograph.
- **0.5** — The environment is adequate but unremarkable. The space around the cat is neither actively harmful nor particularly supportive.
- **1.0** — The environment perfectly serves the cat. Negative space cradles the subject, background elements tell a unified visual story, and the cat commands the frame with dignity and presence.

The final score is the mean of three sub-scores, one for each quality evaluated.

## What It Evaluates

The function examines three distinct but interrelated qualities of the photograph. Together, they form a complete picture of whether the environment is serving its subject.

### 1. Purposefulness of Negative Space

Negative space — the empty areas not occupied by the cat or prominent objects — is evaluated for intentionality. The function asks whether the empty space *frames* the cat or *abandons* it.

**High scores** indicate space that feels deliberate: the cat has room to breathe, the emptiness creates a sense of calm and staging, and the subject feels cradled by the composition. Think of it as the visual equivalent of silence in music — not the absence of sound, but a choice that gives the notes around it more meaning.

**Low scores** indicate space that feels accidental: the cat is either lost in a vast, meaningless void that makes it feel small and forgotten, or pressed against the edges of the frame with no breathing room, as though the photograph is closing in on it.

### 2. Coherence of Background Elements

The objects, textures, colors, and shapes behind and around the cat are evaluated for visual coherence. The function asks whether the background feels like it belongs to the *same visual story* as the cat.

**High scores** indicate a background that collaborates with the subject. The elements tell a unified story — whether simple or richly detailed — and collectively guide the viewer's eye back to the cat. A lush garden, a warm wooden desk with a glowing lamp, a clean windowsill — all can score highly if their elements feel like they live in the same world as the cat.

**Low scores** indicate a background that competes with the subject. Dominant shapes pull the eye away, colors clash with the cat's fur, aggressive textures flatten the subject into the scenery, and the photograph becomes more of a visual search puzzle than a portrait. The environment has forgotten whose portrait this is.

### 3. Proportional Presence of the Subject

The cat's stature within the frame is evaluated for appropriateness. The function asks whether the cat feels like the *protagonist* of its own photograph.

**High scores** indicate a cat that commands its space — anchored in the composition, grounded in its environment, and given exactly the right amount of room to exist with dignity. The environment, regardless of scale, defers to the cat.

**Low scores** indicate a cat that struggles for presence — either so small within the frame that it becomes a minor detail lost in its surroundings, or cropped so tightly that it feels constricted and claustrophobic. The environment has overtaken the portrait.

Note: this is not strictly about how large the cat appears. A small cat in a vast landscape can score highly if the composition grants it visual weight and centrality.

## Use Cases

- **Photography review**: Identify which shots from a session achieve the best spatial relationship between cat and environment, separating images where the cat commands its space from those where composition undermines it.
- **Content curation**: Surface cat photographs that feel visually satisfying for social media feeds or editorial collections, since well-staged subjects hold viewer attention longer.
- **Crop guidance**: Use the score diagnostically — if spatial harmony is low, the image may benefit from a crop that removes competing background elements or rebalances the cat's presence in the frame.
- **Image generation training**: Inform generative models about what makes a cat feel at home in its photographic environment, contributing to more natural and appealing synthetic images.
- **Quality filtering**: Automatically flag or deprioritize cat photographs where the environment overwhelms, crowds, or abandons the subject.

## Philosophy

The principle behind this function is simple: **the environment exists to serve the cat**. Every pixel that is not the cat is either helping the viewer see the cat more clearly, feel it more deeply, and appreciate it more fully — or it is failing in its only job. This function evaluates whether a photograph remembers what it is a photograph *of*.