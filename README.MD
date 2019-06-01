Forked from (https://github.com/ideo/LaughDetection), see readme there for details. I suggest getting it up and running before returning. I am unsatisfied by its custom training instructions however.

I wanted real time feedback. In my use case, detecting female voices. 

# Custom Classes

I added `Notebooks/AudiosetProcessingGeneral` which enables you to specify the label you want, as the main repo hard coded the word 'laughing' everywhere. You should only have to modify the variables at the top of the file.

The ontology [here](https://research.google.com/audioset/ontology/index.html) will give you the label data below. If you want all the labels in one file instead of organized hierarchically, [this](https://github.com/IBM/audioset-classification/blob/master/audioset_classify/metadata/class_labels_indices.csv) will give you everything you need to simply get going. 

For my use case, I made the following files:

`Data/female_labels.csv `
```
2,/m/02zsn,"Female speech, woman speaking"
33,/t/dd00004,"Female singing"
```

`Data/not_female_labels.csv `
```
1,/m/05zppz,"Male speech, man speaking"
32,/t/dd00003,"Male singing"
```
The "not_" prefix is to stay in keeping with the original repo's naming convention. Since its use case was laughter vs speech it made more sense. 

# testing
I found pavucontrol's [monitors](https://unix.stackexchange.com/questions/82259/how-to-pipe-audio-output-to-mic-input/82297) the most reliably way to test the setup. I could simply direct a youtube video at it and see consistent results before using my microphone. 


The pre-trained models and re-balanced subset data are all licensed under a [Creative Commons Attribution 4.0 International License.](https://creativecommons.org/licenses/by/4.0/)

If you want to create your own processed subset of the AudioSet data on a different collection of labels, you can follow the code in `Notebooks/AudiosetProcessing.ipynb`. You can create your own subsets of the Audioset data by creating a list of labels to use for the positive and negative cases.




