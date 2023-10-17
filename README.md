# Real World RL Deployment

The list focus on real-world deployment/product of RL. 
The list does not include RL application to games and robotics, which are two main applications.
All the information are publicly available. 

The list aggregates information from 
- [DeepRLInTheWorld](https://github.com/montrealrobotics/DeepRLInTheWorld)
- [RL for real-world problems](https://mighty-melody-f4b.notion.site/RL-for-real-world-problems-0114c270e5d94894b3c4f227e24401db)

We have several categories based on deployment status:
- Currently deployed  
- Deployed at least once/for some time  
- Planned to be deployed  
- Unknown  
- RL library  

learning setting:
- Online 
- Offline 
- Build a simulator then planning
- Build a simulator then search
- Offline data with partial simulator  

difficulty:
- High dimensional actions
- Reward is expensive 

### Industrial Control/Energy Optimization:

AMII applies RL for water treatment plant  
[Blog Post](https://www.amii.ca/latest-from-amii/isl-adapt-uses-ml-make-water-treatment-cleaner-greener/)  
Deployment status: unknown  
Approach: Build a simulator

Google Deepmind uses RL for date center cooling  
[Luo2022](https://arxiv.org/abs/2211.07357), [Lazic2018](https://proceedings.neurips.cc/paper_files/paper/2018/file/059fdcd96baeb75112f09fa1dcc740cc-Paper.pdf)   
Deployment status: Deployed at least once/for some time   
Approach: ?  
Difficulty: ?

Telus uses model-based RL to reducing energy consumption in data centers  
[Presentation](https://www.caiac.ca/sites/default/files/shared/canai-2021-presentations/slides-138.pdf), [Announcement](https://www.telus.com/en/about/news-and-events/media-releases/using-ai-for-good-telus-and-vector-institute-partner-to-reduce-climate-impacts-from-data-centres)  
Deployment status: Unknown   
Approach: Build a simulator then planning

Foobot uses deep RL for heating, ventilation and air conditioning (HVAC) optimization   
[Blog](https://techblog.foobot.io/)  
Deployment status: Deployed at least once/for some time (based on the information [here](https://github.com/montrealrobotics/DeepRLInTheWorld))  
Approach: Build a simulator then planning  
Difficulty: High dimensional action spaces  
Algorithm: PPO with autoregressive policies

NVIDIA uses RL for datacenter congestion control.   
[Paper](https://arxiv.org/pdf/2207.02295.pdf)  
Deployment status: Deployed at least once/for some time  
Difficulty: Constraints on low memory and low inference time
Approach: ?  
Problem Formulation: Multi-agent POMDP  
Algorithm: Policy gradient with LSTM -> Distill to lightweight decision trees

Siemens Technology has been working on industrial applications of reinforcement learning. 
[Videos](https://www.anyscale.com/events/2022/03/29/reinforcement-learning-in-the-physical-world)

Phaidra uses deep reinforcement learning to improve plant stability and energy efficiency.  
[Website](https://www.phaidra.ai/)  
Deployment status: unknown  

StackEase applies deep RL algorithms to optimize Battery Energy Storage Systems (BESS).  
[Website](https://eolrobotics.fr/)  
Deployment status: unknown  

### Finance 

RL library: https://github.com/AI4Finance-Foundation/FinRL

### Recommendation
Yahoo (online bandits)

### Control (besides robotics)
Nuclear fusion control: google deepmind (Unknown deployment status)

Thermal Power Generating
https://arxiv.org/abs/2102.11492

Wave Energy Converters

Balloons 


### Autonomous vehicle
Nuro? 

### LLM
[ChatGPT](https://openai.com/blog/chatgpt) uses Reinforcement Learning from Human Feedback.   
Deployment status: Currently deployed   
Approach: Online   
Algorithm: PPO
Difficulty: Learning a reward model   

### Education 

### Healthcare
Machine Learning for Mechanical Ventilation Control
https://arxiv.org/pdf/2111.10434.pdf

### Operation Research

### Chip Design

### Compiler Optimization

### Drug Discovery
Matrix multiplication

### Algorithm 

## Academic venues
MLJ Special Issue on Reinforcement Learning for Real Life

## Other resources 