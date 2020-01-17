# Intro:

the usage of tf.Dataset.cache, and problems encountered when use it.


# Usage:

tf.Dataset.cache() is used to store processed data onto disk or memory
during the first epoch, thus increases the efficiency. Meanwhile, if 
data is cached onto disk, it can help with deal with really large dataset
that doesn't fit into meory.

# Issues 
Currenty dataset.cache may generate error when use dataset.take.repeat.
Currently, try avoid using the dataset in such a case.
