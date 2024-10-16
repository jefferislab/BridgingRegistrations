# MANC-JRCFIB2022M transform

This transform maps data between the male adult nerve cord (MANC) and male CNS (JRCFIB2022M) space.
It was generated by Sebastian Cachero using the synapse clouds of the respective datasets.

Importantly, the male CNS synapse cloud was subset to the ventral nerve cord and re-centered. This means, that in order
to transform data in forward direction (MANC -> JRCFIB2022M) we have to apply an additional affine transform:

```zsh
$ streamxform JRCFIB2022M_MANC.list JRCFIB2022M_MANC.list/post_registration
270 306 291
304.730071 488.372787 738.641985
```

Invert to transform from male CNS to MANC space:

```zsh
$ streamxform -- --inverse JRCFIB2022M_MANC.list/post_registration --inverse JRCFIB2022M_MANC.list
304.730071 488.372787 738.641985
270 306 291
```

