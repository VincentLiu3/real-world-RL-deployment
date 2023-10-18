# Real World RL in Deployment

The repository compiles real-world applications of reinforcement learning.
- Only include methods that was deployed, is currently deployed, or will be deployed in the future. 
- Exclude RL applications to games and robotics. 
- Only include publicly available information. 

The repository aggregates information from several sources, including
- [DeepRLInTheWorld](https://github.com/montrealrobotics/DeepRLInTheWorld)
- [RL for real-world problems](https://mighty-melody-f4b.notion.site/RL-for-real-world-problems-0114c270e5d94894b3c4f227e24401db)
- [Application of RL 2023](https://docs.google.com/presentation/d/1bJssDePYLuVHSHoBAPYaiIjXcLFB0hOsuR1-PXtEb-o/edit#slide=id.g1d05b5b4042_462_15)

We categorize RL production based on the deployment status (e.g., currently deployed, deployed at least once/for some time, planned to be deployed, or unknown)
and the approaches to solve the problems (e.g., online, offline, build a simulator then planning, build a simulator then search, offline data with partial simulator).

### Industrial Control

**AMII** applies RL for water treatment plant.  
Link: [Blog Post](https://www.amii.ca/latest-from-amii/isl-adapt-uses-ml-make-water-treatment-cleaner-greener/)  
Deployment status: Planned to be deployed   
Approach: Build a simulator 

**Google Deepmind** uses RL to improve the energy efficiency of heating, ventilation and air conditioning (HVAC) control.  
Link: [Luo2022](https://arxiv.org/abs/2211.07357), [Lazic2018](https://proceedings.neurips.cc/paper_files/paper/2018/file/059fdcd96baeb75112f09fa1dcc740cc-Paper.pdf)   
Deployment status: Deployed at least once/for some time. Experiments were done in real world facilities.    
Approach: Online  
Algorithm: Policy iteration, with value function estimated from offline data

**Telus** uses RL to reduce energy consumption for data centers.   
Link: [Presentation](https://www.caiac.ca/sites/default/files/shared/canai-2021-presentations/slides-138.pdf), [Announcement](https://www.telus.com/en/about/news-and-events/media-releases/using-ai-for-good-telus-and-vector-institute-partner-to-reduce-climate-impacts-from-data-centres)  
Deployment status: Unknown   
Approach: Build a simulator then planning

**Foobot** uses deep RL for HVAC optimization.   
Link: [Blog](https://techblog.foobot.io/)  
Deployment status: currently deployed (based on the information [here](https://github.com/montrealrobotics/DeepRLInTheWorld))  
Approach: Build a simulator then planning  
Difficulty: High dimensional action spaces  
Algorithm: PPO with autoregressive policies

**NVIDIA** uses RL for data center congestion control.   
Link: [Paper](https://arxiv.org/pdf/2207.02295.pdf)  
Deployment status: Experiments were done in real world system.   
Approach: Build a simulator then planning   
Difficulty: Constraints on low memory and low inference time, multi-agent POMDP  
Algorithm: Policy gradient with LSTM layers -> distill to lightweight decision trees

**Siemens Technology** has been working on industrial applications of RL.   
Link: [Video](https://www.anyscale.com/events/2022/03/29/reinforcement-learning-in-the-physical-world)  
Deployment status: ?  

**Phaidra** uses deep RL to improve plant stability and energy efficiency.  
Link: [Website](https://www.phaidra.ai/), [Technical Report](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42542.pdf)   
Deployment status: unknown  

**Microsoft Project Bonsai** uses RL for industrial control systems  
Link: [Website](https://www.microsoft.com/en-us/ai/autonomous-systems-project-bonsai?activetab=pivot:primaryr7), [Report](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4Gk6P)  
Deployment status: unknown  
Approach: Build a simulator then planning   

### Energy Control
**Deepmind** successfully controlling the nuclear fusion plasma in a tokamak with deep reinforcement learning.  
Link: [Paper](https://www.nature.com/articles/s41586-021-04301-9), [Post](https://www.deepmind.com/blog/accelerating-fusion-science-through-learned-plasma-control)  
Deployment status: Real-world experiments on TCV (an experimental tokamak)  
Approach: Build a simulator then planning   
Algorithm: MPO (four-layer neural network for the actor, larger RNNs for the critic)

**DeepThermal** uses model-based offline RL to optimize the combustion efficiency of a thermal power generating unit.  
Link: [Paper](https://arxiv.org/pdf/2102.11492.pdf)  
Deployment status: currently deployed (deployed in four large coal-fired thermal power plants in China)  
Approach: Offline  
Algorithm: offline model learning using LSTM + offline actor-critic with reward penalty

[comment]: <> (Wave Energy Converters)

[comment]: <> (**StackEase** applies deep RL algorithms to optimize Battery Energy Storage Systems &#40;BESS&#41;.  )

[comment]: <> (Link: [Website]&#40;https://eolrobotics.fr/&#41;  )

[comment]: <> (Deployment status: unknown  )

### Other Control Applications
Stratospheric balloons  
Link: [Paper](https://www.nature.com/articles/s41586-020-2939-8)

Drone  
Link: [Paper](https://www.nature.com/articles/s41586-023-06419-4)


### Autonomous vehicle
Nuro? 

### LLM
**OpenAI** uses Reinforcement Learning from Human Feedback (RLHF).   
Link: [Introducing ChatGPT](https://openai.com/blog/chatgpt)   
Deployment status: Currently deployed   
Approach: Online   
Difficulty: Learning a reward model  
Algorithm: PPO with learned reward model 

### Recommendation
Yahoo (online bandits)

Azure AI Personalizer

### Operation Research
Amazon inventory control  
Google Maps 

### Finance/Accounting
IRS uses bandits for audit selection  
Link: [Paper](https://realworldml.github.io/files/cr/paper68.pdf) 

### Chip Design

### Compiler Optimization
Compiler Optimization  
Memory mapping  

### Drug Discovery

[comment]: <> (Difficulty: Reward is expensive )

### Education 

### Healthcare
Machine Learning for Mechanical Ventilation Control
https://arxiv.org/pdf/2111.10434.pdf

### Algorithm 
Matrix multiplication

Video compression

### Open Source Software
[ReAgent: Applied Reinforcement Learning @ Facebook](https://github.com/facebookresearch/ReAgent)  
[FinRL: Financial Reinforcement Learning](https://github.com/AI4Finance-Foundation/FinRL)

### Other Resources  
[Towards Deployable RL - What’s Broken with RL Research and a Potential Fix](https://avivtamar.substack.com/p/deployablerl)  
[CMU Real World RL course by Emma Brunskill](https://www.cs.cmu.edu/~ebrun/15889e/index.html)  
MLJ Special Issue on Reinforcement Learning for Real Life   
Reinforcement Learning for Real Life Workshop @ NeurIPS and ICML
