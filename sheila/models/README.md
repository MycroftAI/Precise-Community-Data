# Sheila

### sheila-en 20190817

1000 epochs, sensitivity 0.1, batch_size 3000

[Google Speech Commands Dataset ](https://ai.googleblog.com/2017/08/launching-speech-commands-dataset.html) "sheila" for ww samples

[Public Domain Sounds Backup](http://pdsounds.tuxfamily.org/) + the other [Google Speech Commands Dataset ](https://ai.googleblog.com/2017/08/launching-speech-commands-dataset.html) + private dataset for nww.

precise 0.3.0

wake_words=1618 not_wake_words=102506 test_wake_words=404 test_not_wake_words=25635

{
    "tested_on": "test_set",
    "tp": 356,
    "tn": 25618,
    "acc": 99.8,
    "fn": 48,
    "fp": 4
}

Tested on data used for training

{
    "tested_on": "train_set",
    "tp": 1529,
    "tn": 102444,
    "acc": 99.91,
    "fn": 89,
    "fp": 1
}