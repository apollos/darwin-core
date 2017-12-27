# We need monitor and predict the potential computation cost to understand the worst search period

To estimate computation costs, we identified the basic
TensorFlow (TF) operations used by our model training
and validation, like convolutions, generic matrix multiplications,
etc. For each of these TF operations, we estimated
the theoretical number of floating-point operations
(FLOPs) required. This resulted in a map from TF operation
to FLOPs, which is valid for all our experiments.
For each individual within an evolution experiment, we
compute the total FLOPs incurred by the TF operations in
its architecture over one batch of examples, both during its
training (Ft FLOPs) and during its validation (Fv FLOPs).
Then we assign to the individual the cost FtNt + FvNv,
where Nt and Nv are the number of training and validation
batches, respectively. The cost of the experiment is then
the sum of the costs of all its individuals.
We intend our FLOPs measurement as a coarse estimate
only. We do not take into account input/output, data preprocessing,
TF graph building or memory-copying operations.
Some of these unaccounted operations take place once per
training run or once per step and some have a component
that is constant in the model size (such as disk-access latency
or input data cropping). We therefore expect the estimate
to be more useful for large architectures (for example,
those with many convolutions).
