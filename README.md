# Study for AAAI-2023 paper: "Understanding CNN Hidden Neuron Activations using Structured Background Knowledge and Deductive Reasoning."
This directory contains the codes, reproducible scripts, and experimental data.
1) **Code folder contains the script for** -
   - training and testing a Resnet50V2 model with ADE20K Dataset,
   - loading the model,
   - getting activations from the dense layer for ADE20K Dataset,
   - getting activations from the dense layer for Google Images,
   - script for downloading Google Images in batches.

2) **ecii_pre-requisite_files contains** -
   - .xlsx file, which has positive sets and negative sets for each neuron (Derived from the activations from the dense layer for the ADE20K dataset),
   -  knowledge base wiki data which is mapped with ADE20K Dataset - [Wikidata mapped with ADE20K](https://doi.org/10.17605/OSF.IO/N76B2).
   -  example of a configuration file that is needed to run ECII; the following fields are user-defined parameters and need to be changed:-
```
      // knowledge source definition/owl_file_name
        ks.fileName : string, required
     // positive examples
        lp.positiveExamples : array, required
     // negative examples
        lp.negativeExamples : array, required
```
3) **setting up ECII** -
   - steps on how to setup and run ECII can be found at - [ECII](https://github.com/md-k-sarker/ecii).
     
4) **ecii_results_for_each_neuron contains** -
   - .txt file returned by ECII for each neuron in correspondence to the positive set of Images and negative set of Images for each neuron; .txt file contains the concepts that best describe the positive set of Images for each neuron.

5) **analyzing_dense_layer_activations_googleImages contains** -
   - evaluation - activations for Google Images for each neuron,
   - verification - activations for new set of Google Images for the confirmed neurons,
   - top20vsbelow20_top1_ecii_eval.xlsx file contains the summary for all the neurons and their activations from dense layer for Google Images,
   - top20vsbelow20_top1_ecii_verification.xlsx contains the summary for the confirmed neurons and their activations from dense layer for new set of Google Images.
  
## Steps to reproduce the results
1) Train Resnet50V2 model with ADE20K Dataset
2) Test the model with ADE20K Dataset and get activations from the Dense Layer.
3) For each neuron, classify images into positive and negative sets based on threshold values.
4) Set up ECII and change the user parameters in the config file.
5) Run ECII for each neuron with positive, negative set and knowledge base.
6) ECII returns a hypothesis concept associated with each neuron.
7) Collect the Google Image dataset for hypothesis concept by running the third-party app [Imageye](https://chrome.google.com/webstore/detail/image-downloader-imageye/agionbommeaifngbhincahgmoflcikhm).
   - Add the Google Chrome extention from this link [Imageye](https://chrome.google.com/webstore/detail/image-downloader-imageye/agionbommeaifngbhincahgmoflcikhm).
   - Search for the keywords in Google Chrome and go to images. Go to Imageye from extentions and set the size to medium and type to .jpg to download the google images.
9) Retrieve activations from the Dense Layer for the Google Image dataset to confirm the hypothesis.
10) Collect a new set for Google Image dataset; to validate the above step.
