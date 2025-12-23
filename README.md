<h1 align="center"> Agent-R1: Training Powerful LLM Agents with End-to-End Reinforcement Learning </h1>

<p align="center">
  <a href="https://arxiv.org/abs/2511.14460">
  <img src="https://img.shields.io/badge/Paper-Arxiv-b31b1b?logo=arxiv&logoColor=white" alt="Paper Arxiv">
</a>
  <a href="https://deepwiki.com/0russwest0/Agent-R1"><img src="https://devin.ai/assets/deepwiki-badge.png" alt="Ask DeepWiki.com" height="20"/></a>
  <a href="https://github.com/0russwest0/Agent-R1/stargazers"><img src="https://img.shields.io/github/stars/0russwest0/Agent-R1" alt="GitHub Repo stars"></a>
  <a href="https://github.com/0russwest0/Agent-R1/network/members"><img src="https://img.shields.io/github/forks/0russwest0/Agent-R1" alt="GitHub forks"></a>
  <a href="https://raw.githubusercontent.com/0russwest0/Agent-R1-Community/refs/heads/main/Wechat.jpg"><img src="https://img.shields.io/badge/微信-green?logo=wechat&amp"></a>
  <a href="https://discord.gg/kW3UZU2e"><img src="https://img.shields.io/badge/Discord-blue?logo=discord&amp"></a>
</p>

<p align="center"><img src="./image/agent.png" width="800px" alt="Agent vs Workflow" /></p>

## News

<details open>
<summary><b>Recent Updates</b></summary>

- [2025.11.18] **Technical Report**: We have released the technical report on arXiv.
  
- [2025.05.06] **Tool Environment Redesign**: Completely redesigned and abstracted tool environments to support more flexible and diverse agent-tool interactions patterns.

- [2025.05.06] **Critical Bug Fixes**: Fixed GRPO and Reinforce++ training crash issues that were causing NaN values during training.

- [2025.05.06] **New Tutorials**: Added comprehensive tutorials for creating custom tools and tool environments, including the first open-source runnable implementation of ReTool.

</details>

<details>
<summary><b>Earlier Updates</b></summary>

- [2025.04.01] Added basic **inference scripts** and a simple interactive chat interface. You can now easily deploy and interact with your trained models.

- [2025.03.18] Added comprehensive **multi-modal support**! Agent-R1 now seamlessly integrates with vision-language models (VLMs), enabling agents to process and reason with both text and visual inputs in rich multi-modal environments.

- [2025.03.18] Refactored our codebase to improve maintainability! We've converted verl from a static folder to a **git submodule** and separated our custom code extensions. This makes it easier to update `verl` and understand the project structure.
  > **Important:** After pulling this update, you'll need to reinitialize your environment. Run `git submodule update --init --recursive` and reinstall verl locally from this directory.

- [2025.03.16] Added support for **process rewards**! You can now assign rewards for each tool call based on its effectiveness. To balance process rewards with outcome rewards, we implemented reward normalization inspired by 
## Overview

**Agent-R1** is an open-source framework designed to accelerate research and development at the critical intersection of **RL** and **Agent**. Our framework employs **End-to-End** reinforcement learning to train agents in specific environments. Developers need only define domain-specific tools and reward functions to extend Agent-R1 to their unique use cases, eliminating the need for complex workflow engineering. We hope our modest contribution can benefit the open-source community, making it easier for researchers and developers to create and explore agents in their own domains, collectively advancing the development of autonomous agents. For more details on the algorithm

>
<p align="center"><img src="./image/framework.png" width="800px" alt="RICO Framework" /></p>

## Key Features

- **Multi-turn Tool Calling**: End-to-end reinforcement learning on complete interaction trajectories, allowing agents to learn from sequences of actions
- **Multi-tool Coordination**: Train agents to effectively coordinate and use multiple tools together to solve complex tasks
- **Process Rewards**: Assign rewards for each tool call based on its effectiveness, balanced with outcome rewards through normalization
- **Custom Tools and Environments**: Compatible with mainstream LLM tool calling formats, making it easy to extend with your own tools and scenarios
- **Multiple RL Algorithms**: Supports diverse reinforcement learning approaches including `PPO`, `GRPO`, and `REINFORCE++`
- **Multi-modal Support**: Compatible with vision-language models (VLMs) and multi-modal reinforcement learning

## Upcoming Features

- **Expanded Model Support**: Integration with more foundation models beyond the currently supported Qwen
- **Additional Use Cases**: More example implementations across diverse scenarios and domains

## Extending Agent-R1 with Your Own Tools and Environments

Agent-R1 provides a flexible architecture for creating custom tools and tool environments to suit various agent applications. Our framework is built on two key abstractions:

1. **BaseTool**: Individual tools that agents can use to interact with external systems
2. **BaseToolEnv**: Tool environments that define the state transition function for agent-tool interactions

For detailed guidance on extending Agent-R1, refer to our tutorials:

- 
Additional resources are available in the codebase:
- Example tools: `agent_r1/tool/tools/`
- Example environments: `agent_r1/tool/envs/`
- Data preprocessing: `examples/data_preprocess/`
- Reward functions: `verl/utils/reward_score/`





## Citation
**Agent-R1**
```md
@misc{cheng2025agentr1trainingpowerfulllm,
      title={Agent-R1: Training Powerful LLM Agents with End-to-End Reinforcement Learning}, 
      author={Mingyue Cheng and Jie Ouyang and Shuo Yu and Ruiran Yan and Yucong Luo and Zirui Liu and Daoyu Wang and Qi Liu and Enhong Chen},
      year={2025},
      eprint={2511.14460},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2511.14460}, 
}
```
**TableMind**(WSDM 2026)

*TableMind is built upon the Agent-R1 framework, leveraging its end-to-end reinforcement learning pipeline to train a specialized tool-augmented agent for structured table reasoning.*
```md
@article{jiang2025tablemind,
  title={TableMind: An Autonomous Programmatic Agent for Tool-Augmented Table Reasoning},
  author={Jiang, Chuang and Cheng, Mingyue and Tao, Xiaoyu and Mao, Qingyang and Ouyang, Jie and Liu, Qi},
  journal={arXiv preprint arXiv:2509.06278},
  year={2025}
}
