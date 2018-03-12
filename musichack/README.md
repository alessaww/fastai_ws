# musichack

After following fast.ai course, part 1, I was able to participate to my first real hackaton, a [music hackaton](https://music-hack.org/).

The fast.ai deep learning library, lessons, and tutorials [Practical Deep Learning for Coders](http://course.fast.ai)

To run the model from scrach use the jupyter notebook `musichack_model_train`.
To test the model run the jupyter notebook `musichack_model_test`

The data comes from the [IraKorshunova repository](https://github.com/IraKorshunova/folk-rnn/tree/master/data) who has cleaned, parsed and tokenised the [thesession.org dataset](https://github.com/adactio/TheSession-data). We have used the version 3 of this dataset, [allabcwrepeats_parsed_wot](allabcwrepeats_parsed_wot), which has more than 46,000 transcriptions.

We divided the data in 5% for validation and 95% for training.

Here are some results:
1. *test_trained_for_3m.mid* - this is a generated file after we trained the model for 1 epoch - `learner.fit(3e-3, 1, wds=1e-6)`
1. *test_trained_for_23m.mid* - this after another 7 epochs - `learner.fit(3e-3, 3, wds=1e-6, cycle_len=1, cycle_mult=2)`
1. *test_trained_for_3h.mid* - and this is after 50 epochs - `learner.fit(3e-3, 10, wds=1e-6, cycle_len=5, cycle_save_name='adam3_10')`
1. *test_trained_for_3h_Queen.mid* - this result is done with the full trained model, with input a sequence from A Kind Of Magic - Queen

You need to install the following packages
`sudo apt-get install abcmidi timidity timidity-interfaces-extra`

To convert from abc to mid
`abc2midi test.abc -o test.mid`

To listen to the mid file
`timidity test.mid`

Here are the weights, for different moments of training:
1. [1 epoch](https://drive.google.com/open?id=1_OouFmHzJX-GGhyZatQVwaZrnazym_cM)
1. [7 epoch](https://drive.google.com/open?id=1vukGIXbIsgoF0aUYLmljb5y398iVKkZa)
1. [50 epoch](https://drive.google.com/open?id=15YU5iKZWkwUNV5jKQpOPFKl-8_OM2s0k)
