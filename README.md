# Markov chain Monte Carlo Gibbs Sampling of Projective Fields
This code is from an assignment for a computational neuroscience course at the University of Rochester.   


The assignment is to model V1 neurons under the assumption that they perform inference in a linear Gaussian model with binary latents by neuron sampling:  

<img width="378" height="54" alt="sampling_equation" src="https://github.com/user-attachments/assets/33399b0d-4437-481e-83e0-8b34cf694335" />

CI is a diagonal matrix with diagonal elements being 0.1 (the variance of the independent pixel noise).  
The Bernoulli prior over the latents (the prior probability of any one latent being 1): p(ri = 1) = 0.04  
Τhe 64 projective fields used were provided beforehand, but more could be generated using a 2D Gabor function.


pfs.npy:
<img width="1368" height="852" alt="ProjectiveFields" src="https://github.com/user-attachments/assets/0e2a0604-ecc0-4026-87f2-e6f483eaf022" />

#
The projective field of neuron #10 plotted alongside the spike numbers and marginal posterior probabilities of the neuronal population. When the Gibbs conditional probability is computed and Gibbs sampling is run, neuron #10 is the only one with significant spiking activity and consequently, has a significantly large marginal posterior probability, indicating that it gives the most information about the projective field shape. 
<img width="1370" height="854" alt="PF10" src="https://github.com/user-attachments/assets/cf016dd3-cf8f-44ec-bdf8-349d9a58f0da" />


#
The averaged projective field of neurons #13 and #29 plotted alongside the spike numbers, and marginal posterior probabilities of the neuronal population. When the Gibbs conditional probability is computed and Gibbs sampling is run, neurons #13 and #29 have significant spiking activity and large marginal posterior probabilities, indicating that they give them ost information about the projective field shape.
<img width="1370" height="854" alt="PF13PF29" src="https://github.com/user-attachments/assets/cdfe127a-f921-4b8c-9b99-f662147b9420" />

When reconstruction is done with the information gained from Gibbs sampling, the averaged projective field of neurons #13 and #29 can be reconstructed with high accuracy. 
<img width="1368" height="875" alt="ReconstructedPF13PF29" src="https://github.com/user-attachments/assets/c88ca76a-b2ca-4b53-8586-e777f8e5290a" />
#
Neurophysiology Experiment

A 2D Gabor function was used to generate 8 pixel by 8 pixel sin-wave gratings of 50 different orientations from -π to π radians, and three spatial frequencies k = [1,2,4]. I(x,y,θ) = c*sin(k(x*cos(θ) - y*sin(θ))), where c = 0.2 and is the contrast of the grating.

<img width="1370" height="854" alt="K1SpatialGratings" src="https://github.com/user-attachments/assets/92a9bebd-23a2-433e-95cb-f75e23ceec6e" />
<img width="1370" height="854" alt="K2SpatialGratings" src="https://github.com/user-attachments/assets/57986f7b-0316-4167-b076-60e908c9bc63" />
<img width="1370" height="854" alt="k4SpatialGratings" src="https://github.com/user-attachments/assets/38159eee-861d-4cc9-b479-0f4cfef02a7b" />

The gratings were then shown 50 times for 500ms each, and the average firing rate across the 50 trials were computed for each stimulus. This was used to create an orientation tuning curve for each neuron.
<img width="1370" height="853" alt="OrientationTuningCurves" src="https://github.com/user-attachments/assets/e1d3b4a2-0f68-45d9-9948-880fa760d864" />

