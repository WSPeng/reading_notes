# MASTERING ATARI WITH DISCRETE WORLD MODELS

### intro

compact (and discrete) latent space. and is trained separately from the policy.

balancing term with KL loss

### dreamerv2

replace gaussian latents with categorical variables.

**experience dataset**:  the discount factor is set to 0 at terminate time step? <!--what is the meaning of it?--> batch 50 and length 50, and sampled randomly form replay buffer. "make the enough episode ends observed."

**Model components**: a image encoder, a recurrent state space model RSSM, a predictor

