# Real World RL in Deployment

The repository compiles a list of real-world applications of reinforcement learning.
- Only include methods that was deployed, is currently deployed, or will be deployed in the future. 
- Exclude RL applications to games and robotics where experiments were only done in simulation. 
- Only include publicly available information. 

The repository aggregates information from several sources, including
- [Deep RL In The World](https://github.com/montrealrobotics/DeepRLInTheWorld)
- [RL for real-world problems](https://mighty-melody-f4b.notion.site/RL-for-real-world-problems-0114c270e5d94894b3c4f227e24401db)
- [Application of RL 2023](https://docs.google.com/presentation/d/1bJssDePYLuVHSHoBAPYaiIjXcLFB0hOsuR1-PXtEb-o/edit#slide=id.g1d05b5b4042_462_15)
- [Awesome Real World RL](https://github.com/ugurkanates/awesome-real-world-rl#papers)

We categorize RL applications based on the deployment status (e.g., currently deployed, deployed at least once/for some time, planned to be deployed, or unknown), and the approaches to solve the problems (e.g., online, offline, train with simulators, search with simulators, using offline data to build partial simulators).

## Contents

- [Industrial Control](#industrial-control)
- [Energy Control](#energy-control)
- [Control of Physical Systems](#control-of-physical-systems)
- [LLM](#llm)
- [Other Applications without Deployment](#other-applications-without-deployment)
- [Open Source Software](#open-source-software)
- [Other Resources](#other-resources)

## Industrial Control

**AMII** has been applying RL for water treatment plant.  
Link: [Blog Post](https://www.amii.ca/latest-from-amii/isl-adapt-uses-ml-make-water-treatment-cleaner-greener/)  
Deployment status: Planned to be deployed

**Google Deepmind** used RL to improve the energy efficiency of heating, ventilation and air conditioning (HVAC) control.  
Link: [Paper2022](https://arxiv.org/abs/2211.07357), [NeurIPS2018](https://proceedings.neurips.cc/paper_files/paper/2018/file/059fdcd96baeb75112f09fa1dcc740cc-Paper.pdf)   
Deployment status: Deployed at least once/for some time. Experiments were done in real world facilities.    
Approach: Online  
Algorithm: Policy iteration, with value function estimated from offline data

**Telus** used RL to reduce energy consumption for data centers.   
Link: [Presentation](https://www.caiac.ca/sites/default/files/shared/canai-2021-presentations/slides-138.pdf), [Announcement](https://www.telus.com/en/about/news-and-events/media-releases/using-ai-for-good-telus-and-vector-institute-partner-to-reduce-climate-impacts-from-data-centres)  
Deployment status: Unknown   
Approach: Train with simulators

**Foobot** used deep RL for HVAC optimization.   
Link: [Blog](https://techblog.foobot.io/)  
Deployment status: Currently deployed (based on the information [here](https://github.com/montrealrobotics/DeepRLInTheWorld))  
Approach: Train with simulators   
Difficulty: High dimensional action spaces  
Algorithm: PPO with autoregressive policies

**NVIDIA** used RL for data center congestion control.   
Link: [Paper2023](https://arxiv.org/pdf/2207.02295.pdf)  
Deployment status: Experiments were done in real world system.   
Approach: Train with simulators  
Difficulty: Constraints on low memory and low inference time, multi-agent POMDP  
Algorithm: Policy gradient with LSTM layers -> distill to lightweight decision trees

**Siemens Technology** has been working on industrial applications of RL.   
Link: [Video](https://www.anyscale.com/events/2022/03/29/reinforcement-learning-in-the-physical-world)  
Deployment status: unknown

**Phaidra** has been working on using deep RL to improve plant stability and energy efficiency.  
Link: [Website](https://www.phaidra.ai/), [Technical Report](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42542.pdf)   
Deployment status: unknown  

**Microsoft Project Bonsai** used RL for industrial control systems  
Link: [Website](https://www.microsoft.com/en-us/ai/autonomous-systems-project-bonsai?activetab=pivot:primaryr7), [Report](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4Gk6P)  
Deployment status: unknown  
Approach: Train with simulators

## Energy Control
**Deepmind** successfully controlling the nuclear fusion plasma in a tokamak with deep reinforcement learning.  
Link: [Nature2022](https://www.nature.com/articles/s41586-021-04301-9), [Post](https://www.deepmind.com/blog/accelerating-fusion-science-through-learned-plasma-control)  
Deployment status: Real-world experiments on TCV (an experimental tokamak)  
Approach: Train with simulators  
Algorithm: MPO (four-layer neural network for the actor, larger RNNs for the critic)

**DeepThermal** uses model-based offline RL to optimize the combustion efficiency of a thermal power generating unit.  
Link: [AAAI2022](https://arxiv.org/pdf/2102.11492.pdf)  
Deployment status: Currently deployed (deployed in four large coal-fired thermal power plants in China)  
Approach: Offline  
Algorithm: offline model learning using LSTM + offline actor-critic with reward penalty

[comment]: <> (**StackEase** applies deep RL algorithms to optimize Battery Energy Storage Systems &#40;BESS&#41;.  )
[comment]: <> (Link: [Website]&#40;https://eolrobotics.fr/&#41;  )
[comment]: <> (Deployment status: unknown  )

## Control of Physical Systems
**Google** and **Loon** used RL to control a superpressure balloon in the stratosphere.  
Link: [Nature2020](https://www.nature.com/articles/s41586-020-2939-8)  
Deployment status: Currently deployed  
Approach: Using offline data to build partial simulators (wind simulation based on historical data)  
Difficulty: Partial observability  
Algorithm: Incorporate uncertainty estimates as additional inputs, QR-DQN with a seven-layers Relu network + parallel simulation

**Swift** achieved champion-level performance in drone racing.  
Link: [Nature2023](https://www.nature.com/articles/s41586-023-06419-4)  
Deployment status: Deployed at least once/for some time (won several races against human champions)  
Approach: Train with simulators + fine-tune by collecting more real-world data  
Difficulty: Optimizing a policy purely in simulation yields poor performance on physical hardware  
Algorithm: PPO + parallel simulation

[comment]: <> (Nuro)

## Large Language Models/Conversational Systems
**OpenAI** used Reinforcement Learning from Human Feedback (RLHF) for ChatGPT.   
Link: [Introducing ChatGPT](https://openai.com/blog/chatgpt), [NeurIPS 2020](https://arxiv.org/pdf/2009.01325.pdf)  
Deployment status: Currently deployed  
Algorithm: PPO with learned reward models, penalizes the KL divergence between the RL policy and the original supervised model

**Deepmind** used RLHF for Sparrow.  
Link: [Sparrow](https://arxiv.org/abs/2209.14375), [Blog](https://www.deepmind.com/blog/building-safer-dialogue-agents)   
Deployment status: Unknown (the model was not released publicly)  
Algorithm: A2C with learned reward models, penalizes the KL divergence between the fine-tuned policy and the initial teacher language model

**Anthropic** used Reinforcement Learning from AI Feedback for Claude.   
Link: [Constitutional AI](https://arxiv.org/abs/2212.08073), [Iterated Online RLHF](https://arxiv.org/abs/2204.05862)  
Deployment status: Currently deployed  
Algorithm: Preference labelling are done by an independent model (feedback model), instead of human. The remainder of the training pipeline is exactly the same as RLHF with PPO.

**Meta** used RLHF for Llama 2.   
Link: [Llama 2](https://arxiv.org/abs/2307.09288)  
Deployment status: Currently deployed  
Algorithm: PPO with rejection sampling fine-tuning

**Google** developed a real-time and open-ended dialogue system using RL.  
Link: [Paper](https://arxiv.org/abs/2208.02294)  
Deployment status: Currently deployed in Google Assistant  
Approach: Offline
Algorithm: Stochastic Action Q-learning & Continuous Action Q-learning & Conservative Q-learning

## Recommendation
Yahoo (online bandits)

Azure AI Personalizer

## Operation Research
Amazon inventory control  
Link: [Paper](https://arxiv.org/abs/2210.03137)

Google Maps 

Ridesharing 

## Finance/Accounting
IRS uses bandits for audit selection  
Link: [Paper](https://realworldml.github.io/files/cr/paper68.pdf) 

## Chip Design

## Compiler Optimization
Compiler Optimization  
Memory mapping  

## Drug Discovery

[comment]: <> (Difficulty: Reward is expensive )

## Education 

## Healthcare
Machine Learning for Mechanical Ventilation Control
https://arxiv.org/pdf/2111.10434.pdf

## Sport 
The Emirates Team New Zealand won the America’s Cup with the help of an RL agent.  
Link: [Presentation](https://www.anyscale.com/blog/sailing-to-victory-with-reinforcement-learning)

## Algorithm 
Matrix multiplication

Video compression

## Other Applications without Deployment
Apple used RL to learn a network defense policy  
Link: [Paper](https://drive.google.com/file/d/1frDQBb3dlc12BbCzJRJ_H6swVdhAjWGT/view)

Hewlett Packard Enterprise used RL to control Wave Energy Converters

Boeing used RL to optimize the obstacle avoidance policy.  
Link: [Paper](https://drive.google.com/file/d/1IBGLKZW7AZHC1k6Q2NLlQvEezdLIcQKm/view)

## Open Source Software
[ReAgent: Applied Reinforcement Learning](https://github.com/facebookresearch/ReAgent) from Facebook  
[RLlib: Industry-Grade Reinforcement Learning](https://docs.ray.io/en/master/rllib/index.html)  
[FinRL: Financial Reinforcement Learning](https://github.com/AI4Finance-Foundation/FinRL)  
[TRL: Transformer Reinforcement Learning](https://github.com/huggingface/trl) from Hugging Face  
[RL4LMs: A modular RL library to fine-tune language models to human preferences](https://github.com/allenai/RL4LMs) from AI2

## Other Resources 
#### Blog Posts
[Towards Deployable RL - What’s Broken with RL Research and a Potential Fix](https://avivtamar.substack.com/p/deployablerl)  by Shie Mannor and Aviv Tamar  
[Don’t Panic! Reinforcement learning is full of magical things patiently waiting for our wits to grow sharper](https://medium.com/@marlos.cholodovskis/dont-panic-b4e96aee1364) by Marlos C. Machado  

#### Lectures
[CMU Real World RL course](https://www.cs.cmu.edu/~ebrun/15889e/index.html)  by Emma Brunskill  

#### Journal & Workshop
MLJ Special Issue on Reinforcement Learning for Real Life   
Reinforcement Learning for Real Life Workshop @ NeurIPS and ICML
