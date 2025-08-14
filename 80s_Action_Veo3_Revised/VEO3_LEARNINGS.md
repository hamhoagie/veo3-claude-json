# VEO3 PROMPT ENGINEERING DISCOVERIES - EFFICIENT REFERENCE

## CORE BREAKTHROUGH: CHARACTER BLOCK STRUCTURE
```
SUCCESS RATE: 1/3 renders with correct character attribution and action
KEY: Never intercut between characters - use sequential CHARACTER BLOCKS
```

## CRITICAL RULES FOR VEO3 SUCCESS

### 1. CHARACTER BLOCKING (MOST IMPORTANT)
```json
"action_sequence": [
  "CHARACTER_A BLOCK:",
  "All Character A actions sequential",
  "Character A completes ALL actions",
  
  "CHARACTER_B BLOCK:",
  "All Character B actions sequential",
  "Character B completes ALL actions"
]
```
NEVER: "A does X, B does Y, A does Z"
ALWAYS: "A does X,Y,Z" then "B does A,B,C"

### 2. SUBJECT-OBJECT EXPLICITNESS
BAD: "swings chicken" / "walks forward" / "speaks angrily"
GOOD: "SOLLY swings chicken at REX" / "REX walks toward SOLLY" / "REX SPEAKS TO SOLLY"

### 3. DIALOGUE ATTRIBUTION
- Maximum 2 characters per scene
- Maximum 1 primary speaker per scene preferred
- Use: "[CHARACTER SPEAKING TO OTHER]: 'dialogue'"
- Include character names IN dialogue: "Rex Armstrong is retired"
- Physical actions during speech: "REX SPEAKS WHILE DOING PUSHUPS"

### 4. SCENE COMPLEXITY LIMITS
- 8-second maximum duration
- 2 characters maximum for dialogue scenes
- 1 primary speaker preferred
- 3-4 lines of dialogue maximum

### 5. CONTENT POLICY TRIGGERS TO AVOID
- "Vladimir" + "crime boss" = Putin detection
- Specific body parts in violence ("hits chest" -> "hits")
- Minor/child + any conflict
- "Aggressive" and similar violent descriptors
- Random enforcement - if flagged, wait and retry

### 6. WORKING JSON TEMPLATE STRUCTURE
```json
{
  "scene": "Location - Time",
  "camera_position": {
    "starts": "Shot description",
    "movement": "Camera action",
    "ends": "Final shot"
  },
  "environment": {
    "primary_location": "",
    "details": ["List of visual elements"]
  },
  "characters": {
    "CHARACTER_A": {
      "description": "",
      "physique": "",
      "wardrobe": "",
      "position": ""
    }
  },
  "action_sequence": [
    "ESTABLISHING:",
    "CHARACTER_A BLOCK:",
    "Sequential actions",
    "CHARACTER_B BLOCK:",
    "Sequential actions",
    "FINAL SHOT:"
  ],
  "sequence_blocks": {
    "block_1": "A does X to B",
    "block_2": "B does Y to A"
  }
}
```

### 7. SUCCESSFUL PROMPT CHARACTERISTICS
- Sequential not simultaneous actions
- Clear "ESTABLISHING" and "FINAL SHOT" markers
- Character names used frequently
- Explicit cause-effect relationships
- Numbered enemies/objects for tracking

### 8. CAMERA MOVEMENT (EXPERIMENTAL)
Current hypothesis: Integrate camera into action blocks
```json
"CAMERA BLOCK 1 - WIDE SHOT:",
"Camera action described",
"CHARACTER BLOCK:",
"Character actions in that shot"
```

### 9. NAMING CONVENTIONS THAT WORK
- "REX ARMSTRONG" - clear protagonist name
- "SOLLY" - avoid real person names (Vladimir->Putin trigger)
- Use character names repeatedly in action lines

### 10. PHYSICAL COMEDY SUCCESS
- "Chicken hits Rex" worked when:
  - Wind-up clearly described
  - Impact explicitly stated
  - Reaction separated into own block
  - Sound effects included ("SMACK")

## FILES TO REFERENCE
- WORKING TEMPLATE: `scene_01D_WORKING_TEMPLATE.json`
- Contains chicken hit scene that achieved 1/3 success rate

## KEY INSIGHT
VEO3 can handle complex scenes but needs:
1. Information in rigid sequential blocks
2. Explicit subject-object relationships everywhere
3. No ambiguity about who/what/when
4. Character actions never intercut

## RECONSTRUCTION INSTRUCTIONS
When starting new conversation:
1. Load this document
2. Reference `scene_01D_WORKING_TEMPLATE.json` as base
3. Apply CHARACTER BLOCK structure to all scenes
4. Maintain subject-object explicitness throughout
5. Expect 1/3 success rate as benchmark