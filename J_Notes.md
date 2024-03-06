1. Error when install requirements: 

'error: tensorflow 2.13.1 has requirement typing-extensions<4.6.0,>=3.6.6, but you'll have typing-extensions 4.9.0 which is incompatible.'


<!-- 'stable "$1" "$ALPHA" NN-REHU "$INNER_EPSILON" "$SMOOTH_V" "$REHU" &' -->
One train many cmd is:
train_pendulum_stable stable 2 0.001 NN-REHU 0.01 0 0.005 &

Passing to pendulum_error.py: 

<!-- MODEL := stabledynamics[latent_space_dim=4,a=0.001,projfn=NN-REHU,projfn_eps=0.01,smooth_v=0,hp=60,h=100,rehu=0.005]
 -->
pendulum_error.py             \
    pendulum[n=$N,test]                     \
    "$MODEL"                                \
    "$OUTDIR/checkpoint_*.pth"              \
    1000 | tee -a "$OUTDIR/eval.txt"