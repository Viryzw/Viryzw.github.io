### 2026_03_02 Report

> 西北工业大学软件学院 2023级 杨峥巍


#### 1. Previous Work

- leverage large-scale robot demonstrations：have limitations in generalization
- incorporating intermediate thinking processes（explicit CoT）：suffer from high inference latency due to  lengthy reasoning traces
- reasoning dropout：risks performance degradation due to critical information loss

![1](..\images\img-report2\1.png)

#### 2. Fast-ThinkAct

![2](..\images\img-report2\2.png)

##### 2.1. Verbalizable Latent CoT by Reward Preferences

$$
\mathcal{J}_{\mathrm{GRPO}}(\theta)=\mathbb{E}_{\tau\thicksim\mathcal{F}_\theta^T}\left[\min\left(r_\theta(\tau)A(\tau),\mathrm{clip}(r_\theta(\tau),1-\epsilon,1+\epsilon)A(\tau)\right)\right]
$$

where

- $$A(\tau)=\frac{R_\tau-\mathrm{mean}(\{R_i\}_{i\in G(\tau)})}{\mathrm{std}(\{R_i\}_{i\in G(\tau)})}$$：normalization in the group，relative quality

- $$r_{\theta}(\tau) = \frac{\mathcal{F}_{\theta}^{T}(\tau)}{\mathcal{F}_{old}^{T}(\tau)}$$：Represents the difference between the new distribution and the old distribution

- clip：avoid "one-hot" or overfitting.

$$
\mathcal{L}_{\mathrm{verb}}=-\mathbb{E}\left[\log\sigma\left(\beta\left(\log\frac{p_{\psi}(\tau^{+}|\mathbf{z})}{p_{\mathrm{ref}}(\tau^{+})}-\log\frac{p_{\psi}(\tau^{-}|\mathbf{z})}{p_{\mathrm{ref}}(\tau^{-})}\right)\right)\right]
$$

where

- $$\tau^+=\arg\max\limits_{\tau\in G}A(\tau)\mathrm{~and~}\tau^-=\arg\min\limits_{\tau\in G}A(\tau)$$

- $$\log\frac{p_{\psi}}{p_{ref}}$$：not a preference that arises inherently from $$\tau$$ itself.

##### 2.2. Action-Aligned Visual Plan Distillation

$$
\mathcal{L}_{\mathrm{distill}}=\|h_t^T-h_t\|_2^2
$$

where $$h_{t}^{T}$$ and $$h_{t}$$ are the hidden states from teacher (corresponding to $$\tau^{+}$$) and student, respectively.

hidden state alignment
$$
\mathcal{L}_{\mathrm{ans}}=\sum_{i=1}^K\|p_i-\hat{p}_i\|_2^2,\mathrm{~with~}p_i=\mathrm{MLP}(h^{\prime}(\mathbf{s}_i))
$$
output trajectory alignment

##### 2.3. Reasoning-Enhanced Policy Learning

$$
\mathcal{L}_{\mathrm{IL}}(\phi)=\ell\left(\pi_\phi(o_t,l,c_t),\hat{a}_t\right)
$$

where

- $$c_{t}$$：which is also $$\{\mathbf{s}_{i}\}$$, is in Spatial KV
- $$\hat{a}_{t}$$$：ground-truth actions

- $$\ell$$：diffusion policy

#### 3. Training Datasets and Evaluation Benchmarks

- datasets

  - reasoning VLM training
    - single-arm visual trajectories
    - dual-arm visual trajectories from the AIST dataset
    - QA tasks
  - reasoning-enhanced policy learning
    - OXE dataset
    - static Aloha dataset

- benchmarks

  - embodied reasoning

  | Benchmark      | Task                               | Metric            |
  | -------------- | ---------------------------------- | ----------------- |
  | EgoPlan-Bench2 | Multiple-choice question answering | accuracy          |
  | RoboVQA        | Video-based question answering     | BLEU score        |
  | OpenEQA        | Visual question answering          | LLM-based scoring |
  | RoboFAC        | Visual question answering          | LLM-based scoring |

  - robot manipulation

  | Benchmark   | Task                                                    | Key Features                                  |
  | ----------- | ------------------------------------------------------- | --------------------------------------------- |
  | SimplerEnv  | Simulated manipulation tasks                            | Highly correlated with real-world performance |
  | LIBERO      | Diverse manipulation tasks including long-horizon tasks | Tests long-horizon planning ability           |
  | RoboTwin2.0 | Complex bimanual manipulation                           | High-difficulty dual-arm tasks                |

#### 4. Results

![3](..\images\img-report2\3.png)

- enables long-horizon planning

![4](..\images\img-report2\4.png)

- enables failure recovery

![5](..\images\img-report2\5.png)

- enables few-shot adaptation

![6](..\images\img-report2\6.png)