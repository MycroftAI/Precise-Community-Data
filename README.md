# Precise-Community-Data
Pre-trained Precise models and training data provided by the Mycroft Community

## Pre-trained Models
Models are housed in two branches:
- Master - for completed models available for download and use
- Models-dev - for models in development, available for testing

Models should be packaged in a gzip tar.  Each archive should contain the model files (wakeword.pb, wakeword.pb.params, wakeword.pb.txt).  A SHA256 hash of the archive should be uploaded as part of the of the README.md in the models/ directory.

## Files
### Directory Structure
```
│   README.md
│   
└───licenses/ # contains license templates and the licenses of submitted files.
│   │   license-template.txt
│   │   license-YYYYMMDD-githubusername.txt
│   │   license-YYYYMMDD-githubusername.txt
│   │   ...
│   
└───not-wake-words/ # samples that are clearly not wake words
│   │
│   └───lang-short/ # the two-character ISO 639-1 language code eg de, en, es, pt, etc.
│   │   │   metadata.csv # a transcript for the not-wake-word files
│   │   │   notwakeword-lang-uuid.wav
│   │   │   notwakeword-lang-uuid.wav
│   │   │   ...
│   │
│   └───noises/ # samples that are not audible words
│       │   noise-uuid.wav
│       │   noise-uuid.wav
│       │   ...
│
└───wake-word/ # the wakeword name eg hey-mycroft, computer etc
    │
    └───models/ # Precise models for this wake-word
    │   README.md
    │   wakeword-lang-preciseversion-YYYYMMDD-githubusername.tar.gz
    │   ...
    │
    └───lang-short/ # the two-character ISO 639-1 language code eg de, en, es, pt, etc.
        │   README.md
        │   wakeword-lang-uuid.wav
        │   wakeword-lang-uuid.wav
        │   ...

```

### File Naming Conventions
Wake word clips should be named using the format of “wakeword-lang-uuid.wav”.  UUID’s can be generated using command line tools on unix systems.  Not wake word clips should be named as “notwakeword-lang-uuid.wav”.  Noise clips would use “noise-uuid.wav”.  The name of the model archive should be in the format of “wakeword-lang-preciseversion-YYYYMMDD-githubusername.tar.gz”.  Licenses should use names like “license-YYYYMMDD-githubusername.txt”

### Audio Clip Conventions
Audio files should be WAV files in little-endian, 16 bit, mono, 16000hz PCM format.  FFMpeg calls this “pcm_s16le”.  Clips for wake words should contain only the wake word and silence of no more than one second before and after.  All clips should be less than or equal to three seconds total length.  

## Contributions
### Pull Request Template
New pull requests containing raw audio data will need to be submitted with a license file. A PR for a wakeword should be submitted to the branch for that wakeword.  If a branch does not exist, create one, as well as a README.md for the word.  The license file will need to include the names of all files submitted as part of the PR, as well as the github user’s name.  Each PR should have its clips and files sorted using the previously described directory structure.  It is preferred that a PR be one set of words or model, ie, a single wake word, or only not wake words.  A compressed/zip file of just the clips can be submitted as part of the PR; please ensure the file is placed in the relevant directory.  Clips meant for not-wake-word should also have an updated metadata.csv file, using a format of “filename,transcript”.  For models, add an entry to the relevant Readme.md file about the model. This should indicate at a minimum the model name, license, and SHA256 sum. Additional information like the datasets used, a link to further info, and precise parameters used in training to create the model are also helpful.  

### PR Review Process
1. Verify formatting of files is correct
2. Review the license file for correct contents.  
3. Check that included clips are named correctly, formatted correctly (ie, file $clip), and less than three seconds duration (ie, exiftool -Duration \*.wav | some grep and things)
4. Spot check clips to ensure they are the correct wake word, or that noise, or not wake word speech is contained as appropriate.
5. For submitted models, if you speak the submitted language, test the model. (other stuff about testing model here)
6. If PR looks correct and sounds right, then approve and merge. If not, post a comment indicating what needs to be updated.
7. Any PR open longer than 30 days with an un-replied to comment will be closed.  

## Licensing
We prefer audio clips to be submitted under public domain license.  Other acceptable audio licenses include the Creative Commons BY, BY-SA, BY-NC, BY-NC-SA licenses.  A license template for public domain usage is provided in the Licensing directory.  For pre-trained models, we can accept any of the main seven CC licenses including BY-ND and BY-ND-NC. Submissions using other licenses will need to be reviewed more thoroughly before acceptance.  

All audio should be sourced by the submitter. No copyright material will be accepted. No material from unknown provenance will be accepted.

Contributors to the repo must include a license during submission. They are not required to sign the Mycroft Contributor License Agreement.
