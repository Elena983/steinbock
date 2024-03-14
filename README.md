# steinbock

Image of the colorectal cancer core from TMA [from](https://lunaphore.com/40-plex-tma-minerva-story/#s=0#w=0#g=0#m=-1#a=-100_-100#v=0.7676_0.499_0.5#o=-100_-100_1_1#p=Q)

All images are from different patients.
As input, we need only the image and panel.csv file.

Patient 2's image seems to have insufficient segmentation as this sample is a metastatic signet-ring cell carcinoma (SRCC) appendix and may be processed incorrectly. 

![iScreen Shoter - Google Chrome - 240207131626](https://github.com/Elena983/steinbock/assets/68946912/66f55b23-f3e8-4d8b-91c7-bcc684f4eae1)

The distribution of expression counts across cells is often skewed towards the right side, meaning many cells display low counts, and few cells have high counts. The expression counts are commonly transformed or clipped to avoid analysis biases from these high-expressing cells.

Nuclei are centered within the segmentation masks and all cell types are correctly segmented
The segmentation approach here segments cells across different sizes correctly. 

patient2 image displays less dense tissue structure
but overall,  it is intact and appears to be segmented correctly

![image](https://github.com/Elena983/steinbock/assets/68946912/236fa420-d0ef-4143-8805-45cd1179c209)
Differences in cell size distributions can indicate segmentation biases due to differences in cell density or can indicate biological differences due to cell type compositions (tumor cells tend to be larger than immune cells).

the absolute measure of cell density often reported in cells/mm2 

![image](https://github.com/Elena983/steinbock/assets/68946912/72c1ae24-69ae-44b7-8b39-0e36740fc2d7)

![image](https://github.com/Elena983/steinbock/assets/68946912/e495b953-72ae-4ad1-80ab-038f89133bd0)

![image](https://github.com/Elena983/steinbock/assets/68946912/d02efeb5-2fc6-4a1a-bddf-fcb25ea7805d)
Visualization of the mean marker expression per image to identify images with outlying marker expression. 
This check does not indicate image quality per se but can highlight biological differences.

![image](https://github.com/Elena983/steinbock/assets/68946912/39c8bd2f-68fd-4203-bec0-bc326c5618e7)
We observed a more aggressive merging of cells from different patients than the results after fast correction, so we chose the harmony algorithm. 
Notably, immune cell and epithelial markers are expressed in distinct regions of the UMAP.

![image](https://github.com/Elena983/steinbock/assets/68946912/8f4b8e63-0515-48a2-9f6f-fa35129bef7b)
Phenograph looks like a better clustering approach than SNN and FlowSom.

![image](https://github.com/Elena983/steinbock/assets/68946912/b859cc74-c934-47cd-8f48-ac3fc6e1bef0)

Publication-ready ComplexHeatmap. 

Summarizing all above
Tumor cells have the largest mean cell area, many neighbors, and elevated Ki67 expression.
MPs and DCs have the highest number of neighbors on average, 
which is biological sound given their predominant location in highly immune infiltrated regions near tumors.

Color Set 1

![image](https://github.com/Elena983/steinbock/assets/68946912/fa00867a-fb67-4512-88af-151bb8342566)

Color Set 2

![image](https://github.com/Elena983/steinbock/assets/68946912/0c975ce5-b405-4584-9a1d-72b58a2e829f)


The pseudobulk-expression profile of B cells seems markedly distinct from the other cell types, while comparable cell types such as the T cell subtypes (Treg, Tcyt, Thelp) group together.

![image](https://github.com/Elena983/steinbock/assets/68946912/9bb04f9a-d403-40df-8a14-7ddb1d747a9d)

Segmentation mask visualizing

![image](https://github.com/Elena983/steinbock/assets/68946912/7ef4bafb-a0ce-40a1-86c7-3f8deba536b2)

![image](https://github.com/Elena983/steinbock/assets/68946912/269967bf-ded2-41a4-8427-9ba2649ce8d3)

![image](https://github.com/Elena983/steinbock/assets/68946912/7fcaacf9-3260-4b65-bf99-b5c3d3b88d2f)

Selective visualization of cell outlines on composite images.

![image](https://github.com/Elena983/steinbock/assets/68946912/ce2b059d-12c6-49de-8363-bdf8008c82da)

Outlining cells on images

![image](https://github.com/Elena983/steinbock/assets/68946912/5c443f6d-7b3a-4afd-b0be-7e146e03088f)

##Spatial analysis

![image](https://github.com/Elena983/steinbock/assets/68946912/d713b413-e484-4618-971d-7653d8345af7)

Highlighting all spatial clusters and only the tumor communities

![image](https://github.com/Elena983/steinbock/assets/68946912/48267def-070e-49ce-97b2-4e5234b29e04)

Non-tumor communities and enrichment analysis between all spatial clusters

![image](https://github.com/Elena983/steinbock/assets/68946912/377ea589-4670-451b-a133-4550ee517ca5)

##Cell-cell interactions analysis

In Patient 1's sample, the cellular composition consists primarily of immune cells, encompassing most of the detected cellular neighborhoods (CN). Conversely, in Patient 3's sample, the cellular makeup predominantly comprises tumor cells, with immune cells occupying a minority proportion of the detected CN.

The results are very similar to the [(Cyto-Community analysis)](https://github.com/Elena983/CytoCommunity). 

We clearly see the same formation of tertiary lymphoid structures (B cells and T cells) and the interplay between stroma and endothelial cells.

![image](https://github.com/Elena983/steinbock/assets/68946912/9eada5e0-a60a-4f26-a03e-e48be5e19caf)

##Tissue regions

As expected, we can observe that interfaces between different CNs make up distinct SCs.

Filter the SCs based on user-defined thresholds for the number of group entries (here at least 2 patients) and/or total number of cells (here a minimum of 100 cells) per SC
 
For example, we can observe that SC 6 (B and T cells) has a degree (n = 2) and potentially more CN interactions with CN2 (directly to SC 1), * to 1 and 6

![image](https://github.com/Elena983/steinbock/assets/68946912/9796d469-4222-4868-b992-3edeeb90cbc0)

##Immune and stroma infiltration to tumor cluster

Cellular neighborhood analysis - Supervised

T cell (CD8+, CD4+) infiltration to tumor

Patient 3 exhibits a higher frequency of tumor patches compared to Patient 1. Additionally, both samples display T-cell infiltration into the tumor region; however, in Patient 3, the frequency of T-cells is twice as high.

![image](https://github.com/Elena983/steinbock/assets/68946912/b57f25ed-f9c5-47e2-9ea5-1fbaa7fe5f86)

The distribution between cell types 

![image](https://github.com/Elena983/steinbock/assets/68946912/6556a564-eb7b-4cc4-b1df-99e979c7db65)

see the [stemness score calculating for comet data](https://github.com/Elena983/stemness_omics) on the same data





