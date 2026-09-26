# Hindi Prosodic Phrase Annotated Dataset for Children

This dataset contains prosodic boundary annotations for Hindi children's reading materials. The annotations are designed to identify locations where a prosodic boundary or pause may naturally occur during read-aloud speech.

## Dataset Overview

- **Language**: Hindi
- **Total Stories**: 54 stories
- **Grade Range**: Grade 3 to Grade 8
- **Stories per Grade**: 9 stories each (6 grades × 9 stories = 54 stories)
- **Batches**: 3 CSV files, each containing 18 stories
- **Annotators**: 6 annotators
- **Annotation Coverage**: All 6 annotators annotated all 54 stories
- **Annotation Threshold**: A token is considered to have a prosodic boundary when at least 4 out of 6 annotators marked a boundary
- **Target Use**: Prosodic boundary prediction for children's reading materials

## Data Source

The source of the Hindi reading materials will be documented in a future version of this repository.

## File Structure

The dataset is divided into three annotation batches:

- `annotations/Batch-1_combined.csv` — 18 stories
- `annotations/Batch-2_combined.csv` — 18 stories
- `annotations/Batch-3_combined.csv` — 18 stories

Together, the three files contain annotations for all 54 stories.

## Data Format

Each CSV file contains token-level annotations along with individual annotator markings and the resulting ground-truth labels.

| Column | Description |
|--------|-------------|
| `Mask` | Semantically masked word |
| `StoryID` | Unique identifier for the story |
| `TokenID` | Individual word/token in the story |
| `R1` through `R6` | Individual annotator markings |
| `GT` | Agreement score across annotators |
| `GT_isboundary` | Presence of a prosodic boundary (`GT >= 4`) |
| `GT_boundary_forbidden` | Presence of a forbidden pause (`GT = 0`) |

## Annotation Schema

Annotators marked whether a prosodic boundary should occur after a given token.

- **0**: No prosodic boundary
- **1**: Prosodic boundary

The final ground-truth boundary label was obtained using a threshold of **4 out of 6 annotators**:

- **GT ≥ 4** → Boundary
- **GT < 4** → No Boundary

## Annotation Guidelines

Annotators were instructed to identify locations where a prosodic boundary or pause would naturally occur when reading the children's text aloud.

The annotations are intended to capture prosodic phrasing relevant to natural and comprehensible read-aloud speech.

## Data Privacy and Masking

The released annotation files contain masked word representations rather than the original word forms.

The masking is intended to protect the original text while retaining the information required for the annotation and prosodic boundary prediction task.

As a result, features that depend directly on the original word form, such as exact word length or syllable count, may differ from those computed from the original unmasked text.

## Use Cases

This dataset can be used for research in:

- Hindi prosodic boundary prediction
- Prosodic phrase boundary detection
- Text-to-speech systems
- Child-oriented speech synthesis
- Read-aloud speech processing
- Educational speech technology
- Computational prosody

## Citation

Citation information will be added once the associated research work is finalized.

## Contact

For questions about this dataset, please contact:

**Sakshi Jadhav**  
Email: sakshijadhav565@gmail.com

## Acknowledgments

We thank all annotators who contributed to the annotation of the Hindi children's reading materials.
