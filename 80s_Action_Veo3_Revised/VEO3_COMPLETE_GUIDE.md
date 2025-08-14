# VEO3 PROMPT ENGINEERING - COMPREHENSIVE GUIDE
*Updated with official Google documentation*

## CONFIRMED DISCOVERIES (Our findings validated by Google)
- 8-second maximum duration per clip
- Single scene focus (don't chain A then B then C)
- Clear, specific language required
- Image-to-video: prompt for MOTION ONLY, not description

## NEW CRITICAL INFORMATION FROM GOOGLE

### 1. NINE CORE PROMPT ELEMENTS
```
1. Subject (people, animals, objects)
2. Action (movements, interactions, emotions)
3. Scene/Context (location, time, weather)
4. Camera Angles (eye-level, low-angle, close-up, etc.)
5. Camera Movements (pan, tilt, dolly, zoom, etc.)
6. Lens & Optical Effects (wide-angle, telephoto, bokeh)
7. Visual Style (lighting, mood, artistic style, ambiance)
8. Temporal Elements (pacing, slow-motion, time-lapse)
9. Audio (sound effects, ambient noise, dialogue)
```

### 2. DIALOGUE FORMATTING (CRITICAL!)
**CORRECT FORMAT FOR SPOKEN DIALOGUE:**
```
A guy says: My name is Ben
```
**WRONG (creates subtitles):**
```
A guy says: "My name is Ben"
```
- Use colon (:) only
- NO quotation marks
- This explains our dialogue issues!

### 3. CAMERA SHOT TERMINOLOGY THAT WORKS
**Angles:**
- Eye-level shot
- Low-angle shot (power)
- High-angle shot (vulnerability)
- Bird's-eye view
- Close-up / Extreme close-up
- Medium shot
- Wide shot / Establishing shot

**Movements:**
- Static shot
- Pan left/right
- Tilt up/down
- Dolly in/out
- Zoom in/out
- Aerial drone shot
- Arc shot

### 4. OUR CHARACTER BLOCK DISCOVERY STILL CRUCIAL
Not mentioned in Google guide but proven effective:
```json
"CHARACTER_A BLOCK:",
"All Character A actions",
"CHARACTER_B BLOCK:",
"All Character B actions"
```

### 5. COMBINING OUR DISCOVERIES WITH GOOGLE'S

**OPTIMAL PROMPT STRUCTURE:**
```json
{
  "scene": "Location - Time",
  
  "1_subject": "Clear character descriptions",
  
  "2_action_sequence": [
    "CHARACTER_A BLOCK:",
    "Sequential actions with subject-object clarity",
    "CHARACTER_B BLOCK:",
    "Sequential actions"
  ],
  
  "3_scene_context": "Setting details",
  
  "4_camera_angles": "Use Google's terminology",
  
  "5_camera_movements": "Explicit movements",
  
  "7_visual_style": {
    "lighting": "",
    "mood": "",
    "artistic_style": ""
  },
  
  "9_audio": {
    "dialogue": "Character says: Text here",
    "sound_effects": "",
    "ambient": ""
  }
}
```

### 6. IMAGE-TO-VIDEO BEST PRACTICES
- Source image provides subject/scene/style
- Text prompt ONLY describes motion
- Three types of animation:
  1. Camera Motion (most reliable)
  2. Subject Animation
  3. Environmental Animation

### 7. WHAT TO AVOID
- Multiple distinct events in one prompt
- Quotation marks in dialogue
- Re-describing what's in source image
- Ambiguous language

## REVISED SUCCESS FORMULA

### For Text-to-Video:
1. Use CHARACTER BLOCKS (our discovery)
2. Format dialogue with colon only (Google's rule)
3. Include all 9 elements when relevant
4. Single scene focus
5. 8-second clips

### For Image-to-Video:
1. High-quality source image
2. Prompt for MOTION ONLY
3. Refer to "the subject" not specifics

## KEY INSIGHT COMBINATION
Google's guide + Our discoveries = Complete solution
- Google provides the framework
- Our CHARACTER BLOCKS solve multi-character scenes
- Subject-object explicitness prevents confusion
- Dialogue formatting explains our attribution issues

## FILES TO REFERENCE
- WORKING TEMPLATE: `scene_01D_WORKING_TEMPLATE.json`
- Adapt to include Google's 9 elements
- Keep CHARACTER BLOCK structure
- Fix dialogue formatting (remove quotes)