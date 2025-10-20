## Understanding what GRPO is doing
<img width="921" height="410" alt="Image" src="https://github.com/user-attachments/assets/e8bf15c5-013a-45b9-bef6-f2cd1b1bb15f" />

Given the GRPO algorithm, we can see it involves three nested loops: the fine-tune iterations $$I$$, the sample batches $$M$$, and the GRPO iterations $$\mu$$.

In one iteration of sampled dataset, the process flow works like this: For each one in the sampled batch of prompts, we generate responses using policy model $$\pi_{\theta}$$, which is our fine-tuned LLM. This step stands for row 7. 

Then we define our reward functions and apply them to the responses and calculate the group relative advantages. This stands for row 8 and 9.

Finally, we update the $$\pi_{\theta}$$ by maximizing the GRPO objective $$\mu$$ times.
