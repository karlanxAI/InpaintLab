# InpaintLab

**InpaintLab** is a standalone AI inpainting workflow studio for Stable Diffusion users who want a faster, more visual way to edit images with multiple masks, prompts, candidates, and cleanup tools.

It is designed to work alongside **Forge**, **Forge Neo**, and **Stable Diffusion WebUI / Automatic1111-compatible backends**.

InpaintLab does not replace your Stable Diffusion backend. Instead, it connects to your running WebUI through the API and gives you a dedicated workspace for multi-mask inpainting, candidate selection, autotagging, AI object removal, and final image merging.

---

## What InpaintLab Does

InpaintLab is built for workflows where one image needs multiple targeted edits.

Instead of repeatedly jumping back and forth between masks, prompts, folders, and previews, InpaintLab lets you:

* Load one base image
* Draw multiple coloured masks
* Give each mask its own prompt and settings
* Generate candidates for each masked area
* Compare the results visually
* Pick the best candidate for each mask
* Merge everything into one final image
* Use autotagging and AI removal tools to speed up the process

It is especially useful for detailed inpainting workflows where different parts of an image need different prompts or different generation settings.

---

## Built for Perfectionist Workflows

InpaintLab is made for users who like to fine-tune an image until the result feels right.

Instead of generating a batch of variations, opening them all in browser tabs, comparing them one by one, losing track of the good ones, and slowly becoming a tiny exhausted PNG detective, InpaintLab keeps the comparison process inside one workspace.

You can generate up to 8 candidates at once, scroll through them easily, preview the masked area more closely, delete unwanted results, and keep only the variations worth comparing.

For smaller or harder-to-see edits, the **Crop Preview** button lets you zoom in on the masked subject so you can judge the actual inpainted area instead of squinting at the full image.

This makes InpaintLab especially useful for picky or detail-focused workflows where the first result is rarely the final result.

---

## Requirements

Before launching InpaintLab, you need one of these running in the background:

* Forge
* Forge Neo
* Stable Diffusion WebUI / Automatic1111-compatible WebUI

Your backend must be running with API access enabled.

For Forge / Stable Diffusion WebUI, this usually means launching with:

```bash
--api
```

InpaintLab connects to your running backend locally and sends generation requests through it.

Common local backend URLs include:

```text
http://127.0.0.1:7860
http://127.0.0.1:7861
http://127.0.0.1:7862
```

---

## Main Features

### Multi-Mask Inpainting

Create and manage multiple masks on one image.

* Up to 4 coloured masks
* Separate controls for each mask
* Enable or disable masks individually
* Generate one mask at a time
* Generate all selected masks in sequence
* Clear, edit, or replace masks as needed

Each mask can have its own workflow instead of forcing the whole image through one prompt.

---

### Per-Mask Prompts and Settings

Each mask can use its own settings, including:

* Prompt
* Negative prompt
* Denoise strength
* Resize / scale value
* Padding
* Batch size
* Crop/detail settings
* Candidate count / generation workflow

This allows one mask to be subtle and another to be much stronger without constantly changing your global Stable Diffusion settings.

---

### Candidate Generation

InpaintLab is built around candidate-based editing.

For each mask, you can generate multiple options, then choose the one that looks best.

* Generate multiple candidates per mask
* Preview candidates inside the app
* Compare results quickly
* Delete bad candidates
* Keep the best ones
* Select a final candidate for each mask
* Merge selected candidates into one finished image

This makes inpainting feel more like picking the best result from a controlled mini-gallery instead of digging through folders like a tired little file goblin.

---

### Candidate Merging

After choosing your favourite candidate for each mask, InpaintLab can merge them back into a final image.

This lets you build up a complete edit piece by piece:

1. Generate candidates for mask 1
2. Pick the best result
3. Generate candidates for mask 2
4. Pick the best result
5. Continue through your enabled masks
6. Merge everything into one final image

---

### AI Object Removal

InpaintLab includes an AI-powered removal / cleanup workflow for removing unwanted objects from an image.

Useful for:

* Removing small unwanted objects
* Cleaning up visual mistakes
* Filling in areas without writing a full prompt
* Quick background or object cleanup

The removal tool is designed as a fast alternative when you just want something gone without building a full inpainting prompt.

---

### Autotagging

InpaintLab includes integrated autotagging to help create prompts from selected image regions.

There are two autotagging options:

1. **Default autotagger**
2. **WD14 autotagger**

The default autotagger is the main option, while WD14 is available as an additional/secondary tagging option.

Autotagging features include:

* Tagging selected mask regions
* Confidence threshold controls
* Banned tag filtering
* Custom banned tag lists
* Substring-based banned tags
* Fast prompt insertion
* Tag cleanup for unwanted terms

This is useful when you want the tool to describe part of the image, then reuse or refine those tags for inpainting.

---

### Banned Tag Filtering

InpaintLab includes banned tag controls for cleaning up autotagging results.

This can help remove tags you do not want in your prompts, such as:

```text
1girl
1boy
white background
simple background
text
watermark
```

Substring filtering is also supported, so banning a word like:

```text
background
```

can also filter tags such as:

```text
simple background
white background
gradient background
```

---

### Stable Diffusion Backend Integration

InpaintLab connects to your running Stable Diffusion backend and can use its available resources.

Depending on your setup, InpaintLab can access:

* Checkpoints
* VAEs
* LoRAs
* Backend generation settings
* Inpainting API features

This makes it easier to work from one dedicated inpainting interface while still using your existing Forge, Forge Neo, or Stable Diffusion installation.

---

### Fullscreen Canvas Editing

InpaintLab includes a fullscreen editing workflow for easier mask drawing and image inspection.

Features include:

* Fullscreen canvas mode
* Zoom controls
* Brush tool
* Eraser tool
* Adjustable brush size
* Mask editing
* Mask colour visibility
* Better workspace for detailed selections

Useful shortcuts may include:

* Fullscreen toggle
* Brush size adjustment
* Eraser mode
* Delete / clear mask actions

---

### Crop Preview and Detail Workflow

InpaintLab is designed for “only masked” style workflows where the selected region can be cropped, padded, resized, and generated with better control.

This helps improve detail while keeping the edit focused on the selected area.

Useful for:

* Faces
* Hands
* Feet
* Clothing details
* Body details
* Small objects
* Local corrections
* Any area where full-image inpainting would be too broad or slow

---

### Tutorial Mode

InpaintLab includes a built-in tutorial mode to help new users learn the workflow.

Tutorial mode is designed to explain the app step by step, including:

* Loading an image
* Drawing masks
* Using mask controls
* Generating candidates
* Selecting results
* Merging candidates
* Using autotagging
* Using removal tools

This makes the tool easier to understand even for users who are new to multi-mask inpainting.

---

## Basic Workflow

1. Start Forge, Forge Neo, or Stable Diffusion WebUI with API enabled.
2. Launch InpaintLab.
3. Connect to your local backend.
4. Load your base image.
5. Draw one or more masks.
6. Add prompts and settings for each mask.
7. Generate candidates.
8. Choose the best candidate for each mask.
9. Merge your selected candidates.
10. Save the final image.

---

## Installation

1. Go to the **Releases** page.
2. Download the latest InpaintLab ZIP file.
3. Extract the ZIP somewhere safe.
4. Start Forge, Forge Neo, or Stable Diffusion WebUI with API enabled.
5. Launch InpaintLab using the included launcher.
6. Follow the setup instructions.

Do not run InpaintLab directly from inside the ZIP file. Extract it first.

---

## Important Notes

* InpaintLab requires a running Stable Diffusion backend.
* InpaintLab does not generate images by itself without Forge, Forge Neo, or Stable Diffusion WebUI running.
* Your backend must have API access enabled.
* Generation speed depends on your Stable Diffusion setup, model, resolution, GPU, and chosen settings.
* Larger crops, higher resolutions, and bigger batches may take longer.

---

## Official Downloads

Only download official InpaintLab releases from this repository:

```text
https://github.com/karlanxAI/inpaintlab
```

Unofficial forks or reuploads may not match the official version.

---

## Support and Feedback

Bug reports, feature requests, and suggestions can be submitted through the GitHub Issues page.

When reporting an issue, please include:

* Your InpaintLab version
* Which backend you are using: Forge, Forge Neo, or Stable Diffusion WebUI
* Your backend URL / port if relevant
* What you were trying to do
* What went wrong
* Any console errors if available

---

## Roadmap

Planned or possible future improvements include:

* Automatic update support
* Improved setup flow
* More backend compatibility improvements
* Expanded tutorial mode
* More inpainting workflow tools
* Quality-of-life improvements for candidate management
* More advanced mask controls

---

## License

All rights reserved unless otherwise stated.

---

## Credits

InpaintLab is built to work with Stable Diffusion WebUI-compatible backends such as Forge, Forge Neo, and Automatic1111-style APIs.

Additional tools, models, or libraries used by InpaintLab should be credited here as the project develops.
