# MLOPsLC - MLOPs Limited Commercial (Indie) Extensions for Houdini
 Experimental nodes for MLOPs in Houdini under a Limited Commercial (Indie) license
### Disclaimer: This repository is a user initiative and is not directly related to the [MLOPs repository](https://github.com/Bismuth-Consultancy-BV/MLOPs) or its authors.
 
 ## How to install:
 To install the node extension for the first time, follow these steps:
1. Clone this repository and make note of the directory you have cloned it to.
2. Copy the `MLOPsLC.json` and `MLOPs_rembg.json` files found in the repository root, and paste them in the $HOUDINI_USER_PREF_DIR/packages/ folder.
3. Edit the `MLOPs.json` file you just pasted, and modify the `$MLOPSLC` path found inside. Set the path to where you cloned the repository to in step one.
4. Launch Houdini and open the tab menu. Type Install to find all nodes with (Install) postfix. Click on each of those nodes to install dependencies. 
5. Restart Houdini once complete.
 
 ## Nodes list:
- [BLIP image captioning](#blip-image-captioning)
- [CLIPseg Image Mask](#clipseg-image-mask)
- [CLIPseg Prompt Mask](#clipseg-prompt-mask)
- [RemBG](#rembg)
- [Semantic Similarity](#semantic-similarity)
- [SD Image Roll](#sd-image-roll)
- [SD Shapes to Points](#sd-shapes-to-points)
- [SD COP2 Processor](#sd-cop2=processor)

 
 ## Nodes description:
 ### BLIP image captioning
This experimental node converts an image represented as colored points into a textual description of its content. The description is stored as a point attribute called 'prompt' and is based on a machine learning model trained on image-caption pairs.

- Based on: [Salesforce/blip-image-captioning-base](https://huggingface.co/Salesforce/blip-image-captioning-base)
- More models: [BLIP](https://huggingface.co/models?other=blip)
- Model documentation: [BLIP](https://huggingface.co/docs/transformers/model_doc/blip)
- Interactive page: [Salesforce/BLIP](https://huggingface.co/spaces/Salesforce/BLIP)

![Blip Image Captioning](/help/images/screenshot_BLIP_image_captioning.png)

### CLIPseg Image Mask
This node extracts low resolution mask from an input image based on another image when it is difficult to describe in text what exactly needs to be identified in the image. The mask can be used to isolate specific areas of interest for further processing downstream. 

- Based on: [https://huggingface.co/blog/clipseg-zero-shot)
- Model documentation: [CLIPSeg](https://huggingface.co/docs/transformers/main/en/model_doc/clipseg)

![CLIPseg Image Mask](/help/images/screenshot_CLIPSeg_image_mask.png)

### CLIPseg Prompt Mask
This node extracts low resolution mask from an input image based on text prompt. The mask can be used to isolate specific areas of interest for further processing downstream. 

- Based on: [https://huggingface.co/blog/clipseg-zero-shot)
- Model documentation: [CLIPSeg](https://huggingface.co/docs/transformers/main/en/model_doc/clipseg)
- Interactive page: [nielsr/CLIPSeg](https://huggingface.co/spaces/nielsr/CLIPSeg)

![CLIPseg Prompt Mask](/help/images/screenshot_CLIPSeg_prompt_mask.png)

### RemBG
This node extracts and replaces background of image with solid color. 

- Based on: [KenjieDec/RemBG](https://huggingface.co/spaces/nielsr/CLIPSeg/tree/main)
- Model documentation: [danielgatis/rembg](https://github.com/danielgatis/rembg)
- Interactive page: [KenjieDec/RemBG](https://huggingface.co/spaces/KenjieDec/RemBG)

- !!! Copy MLOPs_rembg.json to Packages folder in Houdini's preferences directory
- !!! You have to install dependecies: Tab - MLOPs - RemBG - MLOPS RemBG Solver (Install)

![RemBG Install](/help/images/screenshot_RemBG_install.png)
![RemBG](/help/images/screenshot_RemBG.png)

### Semantic Similarity
This node takes two textual prompts as input and returns a Similarity attribute between 0 and 1 indicating how closely related the prompts are in meaning. The score is based on a natural language processing model that compares the semantic content of the two prompts. 

- Based on: [tasks/sentence-similarity](https://huggingface.co/tasks/sentence-similarity)
- Model documentation: [SentenceTransformers ](https://www.sbert.net/)
- More models: [sentence-transformers](https://huggingface.co/models?library=sentence-transformers&pipeline_tag=sentence-similarity&sort=downloads)

- !!! You have to install dependecies: Tab - MLOPs - SentenceTransformers  - MLOPS Semantic Similarity (Install)

![Semantic Similarity Install](/help/images/screenshot_ST_semantic_similarity_install.png)
![Semantic Similarity](/help/images/screenshot_ST_semantic_similarity.png)

### SD Image Roll
This node shifts or offsets an input pixels along a specified axis.

- Based on: [Seamless Texture Inpainting](https://colab.research.google.com/drive/14gt9Z1wqQRS8jVfzJA1K9_PAYlXUAFrR?usp=sharing#scrollTo=WU3fAHi8DIhg)
- Method used: [Numpy Roll](https://numpy.org/doc/stable/reference/generated/numpy.roll.html)

![Semantic Similarity](/help/images/screenshot_SD_image_roll.png)

### SD Shapes to Points
This node generates black and white mask from different kinds of shapes with ability to blur edges.

- Based on: SD Image to Points

![Semantic Similarity](/help/images/screenshot_SD_shapes_to_points.png)

### SD COP2 Processor
This node contains COP2 subnetwork for image manipulations and outputs colored points.

- Based on: SD Image to Points

![Semantic Similarity](/help/images/screenshot_SD_cop2_processor.png)
