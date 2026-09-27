# The Rookie — Character Encyclopedia

A character bible for *The Rookie*, built from a cleaned 320-character dataset. Instead of a flat spreadsheet, characters are written up as full bios in a standardized format and browsed through an interactive HTML file.

## Contents

| File | What it is |
|---|---|
| `The_Rookie_Character_Encyclopedia.html` | Interactive, searchable/filterable browser for every bio'd character. Open it in any browser — no server or build step needed. |
| `The_Rookie_Character_Dataset_CLEANED.csv` | The source-of-truth dataset (320 rows) after cleanup. |
| `The_Rookie_Bio_Bible_v1.md` | The same bios as the HTML file, in plain Markdown (source content for the HTML). |
| `The_Rookie_Character_Dataset_Expanded.csv` / `.xlsx` | Original uploaded dataset (321 rows, pre-cleanup). |

## Dataset cleanup

Starting from the original 321-row dataset:

- **Removed 1 duplicate**: `TR-046` and `TR-053` were both "Brendan Acres" (Kevin Zegers, FBI Special Agent, S5–S7) entered twice under slightly different name spellings. Merged into `TR-046`.
- **Flagged 3 non-character rows**: `TR-159` ("Doctor"), `TR-205` ("Nurse"), `TR-263` ("Paramedic") are unnamed functional roles, not distinct characters. Kept in the dataset with a `Review_Flag` note recommending they be folded into a generic "Medical/Support Staff" entry rather than given standalone bios.
- Net result: **320 characters**, no further duplicates found.

## Bio format

Every full bio follows the same 10-field structure, so details stay consistent across characters:

1. Appearance/Role
2. Personality
3. Background
4. Career
5. Relationships
6. Major Storylines
7. Skills
8. Important Events
9. Character Development
10. Current Status

Plus a header block: Actor, Seasons, Position, Category, Department/World.

The cleaned CSV is the source of truth — hard facts (names, seasons, relationships, roles) are pulled from it, and narrative texture is added from general show knowledge.

## Progress

Dataset is tiered by `Data Depth` / `Category`:

- ✅ **54 "Detailed bio-ready" characters** (Main cast: 14, Recurring + Crossover: 39/40 after dedup) — full bios written and loaded into the HTML browser.
- ⏳ **~120 "Roster-level" Recurring/Guest characters** (2+ appearances) — not yet written.
- ⏳ **~150 Minor Guest characters** (one-episode appearances) — planned as short, lightweight profiles rather than full bios.

### Known data-quality flags (carried into the bios, not hidden)
- **Sava Wu** (`TR-045`): source data is "Varies" across nearly every field — too thin to be a real bio as written. Needs targeted re-research.
- **Abigail** (`TR-040`): actor credit was uncertain in the source data ("Sarah Drew?").

## Using the HTML browser

Open `The_Rookie_Character_Encyclopedia.html` directly in a browser (double-click, or drag into a tab). Features:

- Search by name, actor, or role
- Filter by category: Main / Recurring / Crossover
- Click any roster entry to open their full file (bio fields, seasons, status)
- Status badges (Active / Deceased / Inactive File) are computed automatically from each character's "Current Status" text
- Fully self-contained — all data is embedded in the file, works offline, no dependencies

## Next steps

1. Write full bios for the ~120 Recurring/Guest characters (2+ appearances), same 10-field format.
2. Write lightweight one-line profiles for the ~150 Minor Guest (one-episode) characters.
3. Resolve the Sava Wu / Abigail data flags above.
