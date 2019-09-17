# Marvin

### marvin-en 20190817

1000 epochs, sensitivity 0.1, batch_size 100

[Google Speech Commands Dataset ](https://ai.googleblog.com/2017/08/launching-speech-commands-dataset.html) "marvin" for ww samples

[Public Domain Sounds Backup](http://pdsounds.tuxfamily.org/) + the other [Google Speech Commands Dataset ](https://ai.googleblog.com/2017/08/launching-speech-commands-dataset.html) + private dataset for nww.

precise 0.3.0

wake_words=1680 not_wake_words=102444 test_wake_words=420 test_not_wake_words=25619

{
    "tested_on": "test_set",
    "tp": 362,
    "tn": 25592,
    "acc": 99.72,
    "fn": 58,
    "fp": 14
}

{
    "tested_on": "train_set",
    "tp": 1512,
    "tn": 102383,
    "acc": 99.84,
    "fn": 168,
    "fp": 0
}