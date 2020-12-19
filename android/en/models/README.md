# Android models


### EN
#### android-en-0.3-20201215-jarbas.tar.gz
Trained using a personal dataset, for not wake-word the google-commands 
dataset, false_activations-20201215.tar.gz, bg_noise-20201215.tar.gz and 
noises-20190814-elt.tar.gz were used

Training data contained several speakers from various countries and genders,
with about 3 samples per speaker, microphone quality and pronounciation varied 
a lot per speaker

Added to this 64 samples of my own voice collected with mycroft-core during 
testing of the initial model available at android-20201215-jarbas.tar.gz


=== TrainData ===
- wake_words=114 
- not_wake_words=14444 
- test_wake_words=38 
- test_not_wake_words=14496


=== Test set results ===
- 14513 out of 14533
- 99.86%
- 0.07% false positives
- 26.32% false negatives
  

- False Positives: 10
- True Negatives: 14485
- False Negatives: 10
- True Positives: 28
