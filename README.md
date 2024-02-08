# steinbock

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

![image](https://github.com/Elena983/steinbock/assets/68946912/d795bad5-e043-4ed6-956b-3503c833c097)


The pseudobulk-expression profile of B cells seems markedly distinct from the other cell types, while comparable cell types such as the T cell subtypes (Treg, Tcyt, Thelp) group together.

![image](https://github.com/Elena983/steinbock/assets/68946912/9bb04f9a-d403-40df-8a14-7ddb1d747a9d)

Segmentation mask visualizing

![image](https://github.com/Elena983/steinbock/assets/68946912/7ef4bafb-a0ce-40a1-86c7-3f8deba536b2)

![image](https://github.com/Elena983/steinbock/assets/68946912/269967bf-ded2-41a4-8427-9ba2649ce8d3)

![image](https://github.com/Elena983/steinbock/assets/68946912/7fcaacf9-3260-4b65-bf99-b5c3d3b88d2f)

Selective visualization of cell outlines on composite images

![image](https://github.com/Elena983/steinbock/assets/68946912/ce2b059d-12c6-49de-8363-bdf8008c82da)

Outlining cells on images

![image](https://github.com/Elena983/steinbock/assets/68946912/5c443f6d-7b3a-4afd-b0be-7e146e03088f)






