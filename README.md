# Neural Network Hessian Papers
> The Hessian matrix of neural networks or, more specifically, of the loss with 
> respect to model parameters is a central object of study in deep learning for 
> both optimisation and generalisation. During my PhD, I happened to read a lot 
> about the Hessian so here's my literature review.


[Eigenvalues of the Hessian in Deep Learning: Singularity and Beyond
](https://arxiv.org/abs/1611.07476): 
One of the first empirical studies of the Hessian observing its now 
well-recognised singularity, with a spectrum centered around zero and a few 
outliers depending on the data.

[Identifying and attacking the saddle point problem in high-dimensional non-convex optimization
](https://proceedings.neurips.cc/paper/2014/hash/17e23e50bedc63b4095e3d8204ce063b-Abstract.html):
An influential paper highlighting the prevalence of saddle points, compared to 
local minima, in the high-dimensional non-convex loss landscape of neural nets.

[PyHessian: Neural Networks Through the Lens of the Hessian
](https://ieeexplore.ieee.org/abstract/document/9378171?casa_token=yc32YU5jxsAAAAAA:v8JayGnZugoYAz1oRlQxQZlEq1pJgVnc_RhLeP32WGPaC9IeNDFfskQ-x06QYClBzHjw3Bb7):
Introduces a fantastic open-source library for efficient computation of a 
number of Hessian metrics (top eigenvalues, trace and eigendensity) for deep 
neural networks.

[Analytic Insights into Structure and Rank of Neural Network Hessian Maps
](https://proceedings.neurips.cc/paper/2021/hash/c900ced7451da79502d29aa37ebb7b60-Abstract.html):
An insightful paper deriving a tight upper bound on the Hessian rank for deep
linear networks depending on the *sum* of hidden layer widths. This is in 
contrast to the total number of parameters, which is proportional to the
*squared* sum of widths.

[Vanishing Curvature and the Power of Adaptive Methods in Randomly Initialized Deep Networks
](https://arxiv.org/abs/2106.03763): Another insightful paper taking a fresh
perspective on the phenomenon of vanishing gradients, showing that deep 
networks with standard initialisations also suffer from vanishing curvature.

[Visualizing high-dimensional loss landscapes with Hessian directions
](https://iopscience.iop.org/article/10.1088/1742-5468/ad13fc/meta): Neat paper
showing that the popular method of visualising the loss landscape on 2D random
projections can misidentify saddle points, proposing instead to slice it onto
the minimum and maximum Hessian eigenvectors.

[What Does It Mean to Be a Transformer? Insights from a Theoretical Hessian Analysis
](https://arxiv.org/abs/2410.10986):

[The asymptotic spectrum of the Hessian of DNN throughout training
](https://arxiv.org/abs/1910.02875):

[Empirical Analysis of the Hessian of Over-Parametrized Neural Networks
](https://arxiv.org/abs/1706.04454)

[The Full Spectrum of Deepnet Hessians at Scale: Dynamics with SGD Training and Sample Size
](https://arxiv.org/abs/1811.07062)

[Negative eigenvalues of the Hessian in deep neural networks
](https://arxiv.org/abs/1902.02366)

[Gradient Descent Happens in a Tiny Subspace
](https://arxiv.org/abs/1812.04754)

[Does SGD really happen in tiny subspaces?
](https://arxiv.org/abs/2405.16002)

[An Investigation into Neural Net Optimization via Hessian Eigenvalue Density
](https://proceedings.mlr.press/v97/ghorbani19b)

[How noise affects the Hessian spectrum in overparameterized neural networks
](https://arxiv.org/abs/1910.00195)

