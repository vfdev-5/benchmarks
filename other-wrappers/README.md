
## Benchmark CNN with other TF wrappers

Each subdirectory contains a group of test scripts.

Environment: TF1.3.0, Single Tesla M40, cudnn6.0. Tested on 09/26/2017.

Speed is measured by images per second.

| Task											  | tensorpack	 | Keras	  | tflearn  |
| --------------------------- | ------------ | ------   | -------  |
| Small CNN on Cifar10 			  |		__5364__   | 3571     | 3571     |
| VGG on fake ImageNet			  |		__74__		 | 49				| 49       |
| AlexNet on fake ImageNet	  |		__1207__	 | 711			| didn't test|

Note:

1. The first-epoch is warmup and is not considered in timing.
2. tensorpack uses NCHW format as suggested by TensorFlow, while the Keras experiements are in 'channels_last' format.
	 I tried 'channels_first' in VGG but only got worse performance for unknown reason.

I would hope to benchmark on real ImageNet, but sadly I couldn't find any
working training code on ImageNet with Keras/tflearn.
