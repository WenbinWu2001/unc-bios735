# BIOS735 HW4

Wenbin Wu

## Question 1

> Summarize the computational method proposed in the paper, including its goal, key components, and how it differs from existing methods.

The paper proposes a computational method for statistical shape analysis that builds evolutionary skeletal representations (s-reps) of anatomical objects to achieve reliable geometric correspondence across a population. Each object is modeled as a diffeomorphic deformation of an ellipsoid, whose skeleton and spoke structure evolve stage-by-stage during the deformation. From this s-rep, the method constructs fitted local frames throughout the object interior (“onion-skin” layers) and derives alignment-independent geometric features, such as curvature and positional shifts. Unlike standard diffeomorphism-based representations, which encode deformation fields of boundaries, this approach explicitly models interior geometry and intrinsic coordinates, enabling more consistent correspondence and improved statistical comparison of shapes.

## Question 2

> What is one thing you found interesting or surprising about the method or results presented in the paper?

The idea of building skeleton and spokes is very interesting, as it sheds light on the iterative evolution process on how the shape could be developed from a backbone structure (ellipsoid with skeleton and spokes), like how  an epllisoid embryo develops to an infant.

## Question 3

> What is one thing in the paper you do not understand or would like to learn more about?

Diffeomorphism -- how to deform one shape to another shape and what are mathematical descriptions of this process.

## Question 4

> Identify one potential deficiency or limitation of the method.

The computational cost is a problem, as the evolution deformation is an iteractive process and requires repeated diffeomorphic registrations and skeleton refinements at multiple deformation stages. This may be severe for larger datasets or more complex object shapes.

## Question 5

> Describe how this approach might be applied to your dissertation or a project you are working on. Even if computer vision and geometric shape analysis is not your area of research, brainstorm ways this method could be adapted or extended to address a problem in your field.

I'm thinking of case-control contrastive learning. I could adapt this framework by using evolutionary s-rep coordinates to define pointwise correspondence and extract alignment-free interior features (frame curvatures, spoke lengths, local displacements) for each hippocampus. Then I’d train a contrastive model where positives are same-subject augmentations and negatives are cross-group pairs, encouraging embeddings that separate case vs control while remaining anatomically localized.