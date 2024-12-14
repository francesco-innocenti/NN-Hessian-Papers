# 📑 Neural Network Hessian Papers
> The Hessian matrix of neural networks or, more specifically, of the loss with 
> respect to model parameters is a central object of study in deep learning for 
> understanding overparameterisation, optimisation and generalisation.


## Empirical studies
[Identifying and attacking the saddle point problem in high-dimensional non-convex optimization
](https://proceedings.neurips.cc/paper/2014/hash/17e23e50bedc63b4095e3d8204ce063b-Abstract.html):
An influential paper highlighting the prevalence of saddle points, compared to 
local minima, in the high-dimensional non-convex loss landscape of neural nets.

[Eigenvalues of the Hessian in Deep Learning: Singularity and Beyond
](https://arxiv.org/abs/1611.07476): 
One of the first (if not the first) empirical studies of the Hessian observing
its now well-recognised singularity, with a spectrum centered around zero and 
a few outliers depending on the data.

[Empirical Analysis of the Hessian of Over-Parametrized Neural Networks
](https://arxiv.org/abs/1706.04454): Follow-up of the above paper performing
a more comprehensive analysis.

[Gradient Descent Happens in a Tiny Subspace
](https://arxiv.org/abs/1812.04754): Inspired the above set of papers, finds 
that the gradient tends to move in a low-rank subspace of the Hessian spanned 
by the dominant eigenvectors equal to the data classes.

[Does SGD really happen in tiny subspaces?
](https://arxiv.org/abs/2405.16002): A recent revision of the above paper, 
revealing that training SGD on the dominant subspace does not work (the loss 
plateaus), while projecting it on the bulk subspace does. The author then 
clearly show that this spurious alignment is due to the stochastic noise of SGD.

[The Full Spectrum of Deepnet Hessians at Scale: Dynamics with SGD Training and Sample Size
](https://arxiv.org/abs/1811.07062): Confirms the findings of earlier empirical
studies on the spiked spectrum of the Hessian for larger networks. Together with
the paper below, it also introduces a Stochastic Lanczos algorithm for fast and 
scalable approximation of the Hessian eigendensity.

[An Investigation into Neural Net Optimization via Hessian Eigenvalue Density
](https://proceedings.mlr.press/v97/ghorbani19b): Similar to the above paper, 
finds that, in contrast to previous findings on small networks, the Hessian has 
still some significant eigendensity at the end of training for ResNets trained 
on ImageNet.

[Gradient Descent on Neural Networks Typically Occurs at the Edge of Stability
](https://arxiv.org/abs/2103.00065): For full-batch GD, this influential paper 
demonstrates across a variety of tasks, architectures and hyperparameters that 
the maximum eigenvalue of the Hessian (aka sharpness) rapidly increases at the
start of training (progressive sharpening) and eventually hovers just above the 
2/n threshold for GD convergence (edge of stability).

[A Loss Curvature Perspective on Training Instability in Deep Learning
](https://arxiv.org/abs/2110.04369): Investigates the impact of various
hyperparameters including initialisation, normalisations and learning rate 
warm-up on the sharpness during training, finding that all successful models 
help to avoid or navigate out of high-curvature regions in favour of flatter
ones where larger steps can be taken.

[On the Maximum Hessian Eigenvalue and Generalization
](https://proceedings.mlr.press/v187/kaur23a): A more modern and comprehensive 
empirical investigation of the flatness hypothesis (flatter minima or small
sharpness lead to better generalisation).

[PyHessian: Neural Networks Through the Lens of the Hessian
](https://ieeexplore.ieee.org/abstract/document/9378171?casa_token=yc32YU5jxsAAAAAA:v8JayGnZugoYAz1oRlQxQZlEq1pJgVnc_RhLeP32WGPaC9IeNDFfskQ-x06QYClBzHjw3Bb7):
Introduces a fantastic open-source library for efficient computation of a 
number of Hessian metrics (top eigenvalues, trace and eigendensity) for deep 
neural networks.

[Why Transformers Need Adam: A Hessian Perspective
](https://arxiv.org/abs/2402.16788): Supporting the theoretical analysis of 
[Ormaniec et al. (2024)](https://arxiv.org/abs/2410.10986), shows that training 
transformers with SGD is much worse than Adam because of the block 
heterogeneity of the Hessian.

## Random matrix theory approaches

[The Loss Surfaces of Multilayer Networks
](https://proceedings.mlr.press/v38/choromanska15.html): Shows that, under 
some simplifying assumptions, the loss landscape of feedforward networks is
equivalent to that of a spin-glass model, which for deep models effectively 
means that all the local minima are close to the global minimum.

[Geometry of Neural Network Loss Surfaces via Random Matrix Theory
](https://proceedings.mlr.press/v70/pennington17a.html): Derives an 
approximation of the Hessian eigendensity under simplifying assumptions, 
showing that below a certain critical energy value all critical points are 
minima.

[Beyond Random Matrix Theory for Deep Networks
](https://arxiv.org/abs/2006.07721): Shows that random matrix theoretical 
distributions (including the Wigner semi-circle and Marcenko-Pastur) used to 
model the Hessian spectrum do not match well empirical data at the end of 
training.

[Hessian Eigenspectra of More Realistic Nonlinear Models
](https://proceedings.neurips.cc/paper/2021/hash/a7d8ae4569120b5bec12e7b6e9648b86-Abstract.html):
Derives the eigenspectrum of the Hessian for "generalised generalised linear 
models" (G-GLMs), showing similarly to the above paper that the spectrum can 
depart significantly from theoretical random matrix ensembles depending on the 
data, model and loss.

## Other theoretical works

[Towards Understanding Generalization of Deep
Learning: Perspective of Loss Landscapes](https://arxiv.org/abs/1706.10239):
For one-hidden-layer networks, this shows that low-complexity solutions defined
by small change in the variance of the network map across inputs have a small 
Hessian norm.

[The asymptotic spectrum of the Hessian of DNN throughout training
](https://arxiv.org/abs/1910.02875): Characterises the Hessian spectrum at
initialisation and during training in the NTK limit, and its first two 
moments in the mean-field regime.

[Sharp Minima Can Generalize For Deep Nets
](https://proceedings.mlr.press/v70/dinh17b): A popular paper showing that 
using the flatness or sharpness of minima as a measure of generalisation is 
problematic, since one can easily obtain models of equal generalisation but 
arbitrarily different curvature due to inherent network symmetries.

[Vanishing Curvature and the Power of Adaptive Methods in Randomly Initialized Deep Networks
](https://arxiv.org/abs/2106.03763): Another insightful paper taking a fresh
perspective on the phenomenon of vanishing gradients, showing that deep 
networks with standard initialisations also suffer from vanishing curvature.

[Analytic Insights into Structure and Rank of Neural Network Hessian Maps
](https://proceedings.neurips.cc/paper/2021/hash/c900ced7451da79502d29aa37ebb7b60-Abstract.html):
An insightful paper deriving a tight upper bound on the Hessian rank for deep
linear networks depending on the *sum* of hidden layer widths. This is in 
contrast to the total number of parameters, which is proportional to the
*squared* sum of widths. See [The Hessian perspective into the Nature of 
Convolutional Neural Networks](https://arxiv.org/abs/2305.09088) for an
extension of these results to convolutional nets.

[Analytic Characterization of the Hessian in Shallow ReLU Models: A Tale of Symmetry
](https://proceedings.neurips.cc/paper/2020/hash/3a61ed715ee66c48bacf237fa7bb5289-Abstract.html) & 
[Analytic Study of Families of Spurious Minima in Two-Layer ReLU Neural Networks: A Tale of Symmetry II
](https://proceedings.neurips.cc/paper_files/paper/2021/hash/806d926414ce19d907700e23177ab4ff-Abstract.html)

[Visualizing high-dimensional loss landscapes with Hessian directions
](https://iopscience.iop.org/article/10.1088/1742-5468/ad13fc/meta): Neat paper
showing that the popular method of visualising the loss landscape on 2D random
projections can misidentify saddle points, proposing instead to slice it onto
the minimum and maximum Hessian eigenvectors.

[What Does It Mean to Be a Transformer? Insights from a Theoretical Hessian Analysis
](https://arxiv.org/abs/2410.10986): Following the approach of [Singh et al. (2021)
](https://proceedings.neurips.cc/paper/2021/hash/c900ced7451da79502d29aa37ebb7b60-Abstract.html),
this paper expresses the Hessian of a single self-attention layer, highlighting 
its highly heterogeneous structure compared to standard feedforward and 
convolutional architectures.

[Theoretical characterisation of the Gauss-Newton conditioning in Neural Networks
](https://arxiv.org/abs/2411.02139): Derives tight bounds on the condition 
number of the Gauss-Newton matrix of arbitrary deep linear networks, showing
that many popular techniques to aid optimisation such as skip connections and
batch normalisation improve landscape conditioning.

[Neglected Hessian component explains mysteries in Sharpness regularization
](https://arxiv.org/abs/2401.10809) 
