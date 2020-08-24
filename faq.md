---
layout: page
title: FAQ
---


1.  When we compute the error (1) of a hold out set, which sigma shall
    we use: the same one as in the training set, or we compute a sigma
    value for each point in the test set and then average them?
    According with Girolami's book, there is a formula to estimate the
    uncertainty (variance) of a single test point once we obtained w\*,
    but I'm not sure if it's good to use it to compute the error in the
    hold out set.
    
    **You fit sigma on the training set**
2.  I've found that some authors consider the error function just as the
    sum of the differences between actual values and predicted values.
    They do not use the sigma term. Which formulation shall we use?
    
    **I mentioned this in class. The sigma term comes if you look at the
    error as the negative log likelihood (which is what we are doing).
    If you just view least squares as the approach it doesn't appear.**
3.  How many assignments and exams are there in the course?
    
    **Two assignments (one from Neil, one from Trevor), worth 40% (20%
    each), one exam, worth 60%.**
4.  When is the expected date for the final exam? I may go to my home
    country for holidays in December/January, so I just want to make
    sure to be back on time.
    
    **That isn't scheduled by us. We don't have any control over it. It
    is within the semester period, and you are expected to be in
    Sheffield across all semester periods. For more details see
    <http://www.sheffield.ac.uk/ssid/exams/timetables>.**
5.  The doubt is about the term $\mathbf{w}$ ; in the linear
    regression equation it makes perfect sense about $w_1$ being
    the slope and $w_0$ being the intercept on the y-axis but as we
    move to non-liner i.e quadratic or higher orders what would the
    vector elements in $\mathbf{w}$ stand for i.e. the coefficients
    in the equation $w_0 + w_1 x + w_2 x^2$ stand for ?
    
    I am sorry if this is a stupid question but i needed a little
    clarification. Linear combination does tell me the scalars \* the
    vectors but I am a little confused as to what the scalars stand for
    in higher order polynomials.
    
    **It's not a stupid question, because actually those parameters
    start to lose interpretation as the model becomes more complex.
    Sometimes they mean something (like in a quadratic,** $w_2$
    **would be the curvature) but in general they don't necessarily mean
    anything. It depends very much on the basis set we consider.**
6.  Just a simple question. For question 1 part a) of the first
    assignment, we need to compute the error of the fit. Shall we use
    the quadratic loss to compute it, or the equation where we need to
    fit the variance first?
    
    **You should use the error function as it was defined in the
    class.**
7.  Just a brief question: in part 3 (Bayesian analysis) of the
    assignment, how can I plot one standard deviation above and below my
    fit? I computed the covariance matrix $\mathbf{C}_w$, but from
    all the numbers, which ones are the ones I need to use for
    plotting?
    
    **As it explains in the lecture slides from the Gaussian process
    session (and I went through on the board, and is reviewed in some
    detail in the Week 5 lab sheet), the variance of the output can be
    derived as** $$\Phi \mathbf{C}_w \Phi ^\top$$ **But that
    gives the full covariance of the function. For the marginal standard
    deviations you first need the marginal variances, they can be
    extracted from the diagonal of the full covariance. Then you need to
    square root them to get the standard deviations. Error bars are
    generally shown at two standard deviations.**
    
8.  ) I'm having problems to pause a plot and wait until a key is
    pressed. I haven't found a proper command for this. So far, I've
    made a simulation where a fit is plotted as the number of basis
    increases. The title of the plot changes to show to the user the
    computed error respectively. Is it fine to leave it like this?
    
    **Don't worry too much about this and with ipython notebook there
    are other ways of doing the same thing (e.g. displaying several
    plots in line).**
9.  Once the assignment is finished, where can I upload it?
    
    **On [MOLE](http://vle.shef.ac.uk).**
10. For the Gaussian Process analysis, how can we compute the VC
    dimension?
    
    **That is not part of the syllabus, GP analysis is rarely justified
    via VC dimension, which was originally developed for classification.
    We haven't taught any statistical learning theory in the regression
    part of this course.**
11. For the $\sigma$ fit that we got using MLE, isn't it a biased
    estimate? Shouldn't we use an unbiased estimate?
    
    **I haven't covered the concept of biased estimates in this module
    and don't intend to (although I did talk about error due to bias and
    error due to variance in the lecture on generalization, but that's a
    different thing), so for this course you should *always* use the
    maximum likelihood estimate for $\sigma^2$ (which is, indeed,
    biased).**
12. Suppose we've a data set. We divide it into a training set and
    validation set. We train different models and select the most
    appropriate using the validation set. Once we've selected a model,
    which parameters should we use and report? The ones obtained from
    the training set? Or, using the selected model, we "train" again
    that particular model but this time with the whole data set?
    
    **Good question, it shows you're thinking. I would be happy with
    either, but I think the second is best. Although in practice you
    might do the first because of computational issues.**
13. For the Bayesian approach discussed in class, you mentioned that the
    variance of the output is obtained from
    $\boldsymbol{\Phi}\mathbf{C}_w\boldsymbol{\Phi}^\top$.
    Aren't we forgetting to add the noise term, $\sigma^2
    \mathbf{I}$.
    
    **Again, this shows you are thinking about it. The posterior
    (co)variance of $f(\mathbf{x})$ is given by
    $\boldsymbol{\Phi}\mathbf{C}_w\boldsymbol{\Phi}^\top$,
    but the posterior covariance of $y(\mathbf{x}) = f(\mathbf{x}) +
    \epsilon$ where $\epsilon \sim \mathcal{N}(0, \sigma^2)$
    is indeed given by
    $\boldsymbol{\Phi}\mathbf{C}_w\boldsymbol{\Phi}^\top +
    \sigma^2\mathbf{I}$. I did cover this in class, but may have
    been too quick.**
	
14. During last lab session, why even though we add the variance term to
    the GP, the output looks noiseless compared with the Bayesian
    output?
    
    **If I understand your question correctly, that's because there is a
    lot of noise in the uncertainty about $f$ so adding the noise
    only makes a small difference.**
	
15. Also, on the last lab session, as the GP output moves away from the
    data, the response tends to our prior belief with mean zero and
    standard deviation L. Is it accurate this observation?
    
    **Yes, that's true, and in this case it shows that the prior wasn't
    very sensible, we should have had a prior that doesn't return to
    mean zero. As an independent exercise think about a few different
    ways of doing this.**
    
16. How can we select a good prior distribution to improve the learning
    process?
    
    **Ah! The question to end all questions! That is a very open
    question, and it is, indeed, what much of my research is about! It
    is either that or, given an appropriate prior and likelihood (which
    together I would call the model) how can I do the Bayesian inference
    to infer the posterior distributions and the model parameters.**

