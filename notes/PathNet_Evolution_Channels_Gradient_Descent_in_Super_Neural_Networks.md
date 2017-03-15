An odd little deep mind paper combining evlolutionary algorithms with deep learning. The idea is quite simple. We have a NN with L layers and M modules (where each module is its own N). Multiple modules in each layer can be active (where each module is a different architecture… perhaps). Active modules are learned for an epoch. And determining which module is active is done by an evolutionary algorithm. In the end all parameters not in the optimal genetic pathway are reinitialized.

That is about it. One way to think about this is as an evolutionary dropout network. It performs well on toy examples.