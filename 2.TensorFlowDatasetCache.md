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

Another possible solution:
you can also try go over the dataset once; once it is saved somewhere, 
the repeat method will not create any error.


# Attention
If the cached file existed, the cache method will not update the cached data.
Instead, it will use it directly. So once the dataset is edited, remove the
old cache so the program can create a new one.
