# Study for AAAI-2023 paper: "Understanding CNN Hidden Neuron Activations using Structured Background Knowledge and Deductive Reasoning."
This directory contains the codes, reproducible scripts, and experimental data.
1) Code folder contains the script for -
   - training and testing a Resnet50V2 model with ADE20K Dataset,
   - loading the model,
   - getting activations from the dense layer for ADE20K Dataset,
   - getting activations from the dense layer for Google Images.
   - script for downloading Google Images in batches.

2) ecii_pre-requisite_files contains -
   - .xlsx file, which has positive sets and negative sets for each neuron (Derived from the activations from the dense layer for the ADE20K dataset),
   -  knowledge base wiki data which is mapped with ADE20K Dataset
   -  example of a configuration file that is needed to run ECII; the following fields are user-defined parameters and need to be changed:-
     // knowledge source definition/owl_file_name
        ks.fileName : string, required
     // positive examples
        lp.positiveExamples : array, required
     // negative examples
        lp.negativeExamples : array, required

3) ecii_results_for_each_neuron contains -
   - .txt file returned by ECII for each neuron in correspondence to the positive set of Images and negative set of Images for each neuron; .txt file contains the concepts that best describe the positive set of Images for each neuron.

4) analyzing_dense_layer_activations_googleImages contains -
   - evaluation - activations for Google Images for each neuron
   - verification - activations for Google Images for the confirmed neurons
   - 
