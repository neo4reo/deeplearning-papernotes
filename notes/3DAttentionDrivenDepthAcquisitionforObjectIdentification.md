This is a massive collaboration paper, and results in a massive result. So first at the high level. We are in an environment where a robot wants to reconstruct a scene from a set of previously known objects. The robot views the world through a moving depth sensor that the robot and swivel to view the scene from any angle. This paper tries to aggregate all the view data into a single reconstruction while determining the next best view to gather more information about the scene. Now that you know that, let’s dig in.

The core model consists of a multi view CNN (another paper) extracting high level features from each view and then max pooling over the features. Those features are then used to (1) classify and (2) update the state of a view RNN. The classifier is a hierarchical classifier with a TON of tweaks. The view RNN is trained using a signal of something similar to REINFORCE.

Okay, this seems reasonable if not somewhat complex, but the heavy hitting stuff comes next, the tweaks. They use unsupervised hierarchy discovery in order to order the classes, reasonable. But then they add focus driven occlusion tolerance features (a mouthful). They cluster convolutional filters and keep the filters at the cluster centers as their focus filters. They can then slide these over the image and add attention to areas of high activation, but they go further.  They then train a classifier for each filter and use that classifier at each sliding window to classify the image (combining them in some way that is most likely not important). This seems ridiculously complex, almost deserving its own paper if the results are good, but no, this is a tweak. Sigh. 

Well this is about all I have to say on this one. I look forward to reading the multi view CNN paper