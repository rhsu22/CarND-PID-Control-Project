#Discussion on hyperparameters

I tuned `kp`, `ki`, and `kd` hyperparamters by hand, following observations of effects of each
on the steering behavior.

`Kp` controls how quickly steering can change at any given instant given it is only dependent on
the instantaneous error.  If the value is too low, then steering doesn't change fast enough for
turns.  On the other hand, when it's too high, the vehicle exhibits rapid, repeated overcorrection
after making turns.

`Ki` helps reduce effects of any built-in bias.  In the test case, it'd appear that the integrated
error adds up rather quickly, leading to large magnitudes.  Thus, the value had to be kept fairly
low.

`Kd` acts as a kind of stabilizing, damping factor to prevent rapid steering changes that
`Ki` and proportional error correction may introduce.  If the value is too low, then it doesn't
counter the high `Ki` overcorrection well enough.  However, if it's too high, the car has trouble
making sharp turns.
