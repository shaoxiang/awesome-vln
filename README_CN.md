[English](./README.md)

# Awesome Vision-Language Navigation (VLN) [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

一个精心整理的视觉语言导航（VLN）论文、数据集、仿真器与代码库列表。
涵盖三维环境下的指令跟随、连续导航、基于大语言/视觉模型的规划、世界模型以及场景图推理。

---

## 目录
- [综述与基准测试](#surveys--benchmarks)
- [仿真器与框架](#simulators--frameworks)
- [数据集](#datasets)
- [方法](#methods)
  - [基础模型与预训练](#foundational-models--pre-training)
  - [离散/基于图的VLN](#discrete--graph-based-vln)
  - [连续VLN (VLN-CE)](#continuous-vln-vln-ce)
  - [基于地图与规划](#map-based--planning)
  - [基于VLM/LLM的智能体](#vlm--llm-based-agents)
  - [世界模型与预测规划](#world-models--predictive-planning)
  - [语义导航与场景图](#semantic-navigation--scene-graphs)
- [工具与实用程序](#tools--utilities)
- [贡献](#contributing)
- [许可证](#license)

---

## 综述与基准测试
*综合性综述与基准分析。*
- **[标题]** (作者, 年份, 会议/期刊) – 一句话总结。 [Paper](链接)


- [**NavNuances：VLN细粒度评估框架**](https://github.com/zehao-wang/navnuances) - 该项目旨在对视觉语言导航（VLN）代理进行细粒度评估，提出了一个系统的评估框架以诊断模型在指令理解、路径追踪和物体定位等子任务上的表现。基于EMNLP 2024 Findings，它通过多种导航场景和错误类型分析揭示VLN模型的局限性，适用于从事VLN评估和模型改进的研究人员。
- [**Awesome-VLN：VLN论文资源精选列表**](https://github.com/KwanWaiPang/Awesome-VLN) - 该项目是专门针对视觉语言导航（VLN）领域的论文综述式 Awesome List，系统整理了 VLN 相关的经典与前沿论文、基准、数据集及开源工具，覆盖 R2R、RxR、REVERIE 等任务变体，以及连续 VLN、大模型代理、世界模型等 2024-2026 年突破方向。适用于研究 VLN 的学者和工程师快速获取文献索引与资源导航。
- [**VLN-MME：多模态大语言模型导航能力诊断基准**](https://github.com/billzhao1030/VLN-MME) - 该项目是ACL 2026论文VLN-MME的官方实现，旨在系统诊断多模态大语言模型（MLLMs）在语言引导视觉导航任务中的能力。通过构建专门评估基准与诊断框架，项目分析MLLMs在指令跟随、环境理解与路径规划中的缺陷，提供面向Vision-Language Navigation场景的评测工具。适用于研究MLLM在具身导航中推理与规划能力的研究人员。
- [**Awesome-Vision-Language-Navigation：VLN学术资源精选列表**](https://github.com/NIneeeeeem/Awesome-Vision-Language-Navigation) - 该项目是一个汇集Vision-Language Navigation (VLN)领域学术资源、论文、基准和工具的精选列表（Awesome List），专为VLN研究人员提供系统性综述。它涵盖R2R、RxR、REVERIE等经典任务、Habitat等模拟器以及BEVBert、NavGPT等前沿模型，是入门与深入VLN研究的综合参考。
- [**Awesome_Visual_Language_Navigation：VLN资源大全**](https://github.com/waynechu1021/Awesome_Visual_Language_Navigation) - 该项目是一个针对视觉语言导航（VLN）领域的Awesome List汇总仓库，系统性地整理了VLN相关的论文、开源代码、数据集及工具资源。覆盖了R2R、REVERIE、RxR等经典任务，以及VLN-CE、LLM/VLM导航等前沿方向。通过分类索引帮助研究人员快速定位核心文献与代码实现，适合VLN领域的研究者和工程师使用。
- [**LH-VLN_Challenge2025：长时域VLN挑战赛问题跟踪**](https://github.com/Liquid-star/LH-VLN_Challenge2025) - 该项目是MMSP 2025长时域视觉语言导航（Long-Horizon VLN）挑战赛的官方问题跟踪仓库，用于发布赛事信息、数据集更新以及参赛者支持。它直接面向VLN领域的长期跨房间指令跟随任务，参赛者可在此提交问题、获取官方公告。目标用户为VLN研究人员和挑战参赛者。
- [**Awesome-VLN-myself：VLN个人研究资源汇总**](https://github.com/binbin2002/Awesome-VLN-myself) - 该项目是一个专门针对 Vision-Language Navigation (VLN) 领域的调研资源汇总列表（Awesome List），收录了 VLN 相关的论文、数据集、模型和工具。作为 VLN 研究社区的直接索引，它聚焦于视觉-语言导航的核心主题，包括 R2R、VLN-CE、LLM/VLM 导航器等，为入门和进阶研究者提供了系统性的文献与代码资源导航。
- [**VLN_survey：VLN领域综述仓库**](https://github.com/CHANGJianshuo/VLN_survey) - 该项目是一个面向Vision Language Navigation (VLN)领域的综述仓库，旨在整理和汇总VLN相关论文、方法、数据集与基准。由于直接关注VLN研究进展，可作为入门或文献索引工具。目标用户为VLN方向的研究者和开发者。
- [**NaVILA-Bench-for5090：面向5090 GPU的NaVILA基准测试**](https://github.com/jouta15123/NaVILA-Bench-for5090) - NaVILA-Bench-for5090 是一个在 Isaac Lab 仿真平台上实现的视觉语言导航（VLN）基准测试项目。它提供了一套工具和评估流程，用于在 3D 环境中测试基于指令的导航算法，特别针对 NVIDIA 的 5090 GPU 进行了优化。该项目旨在帮助研究人员快速验证和比较 VLN 模型在仿真中的性能。面向 VLN 研究者、机器人导航开发者及 Isaac Lab 用户。
- [**HA-VLN：人类感知导航开放式基准与排行榜**](https://github.com/F1y1113/HA-VLN) - HA-VLN 2.0 是一个面向人类感知导航的开放基准与排行榜，专为视觉语言导航（VLN）任务扩展而设计，同时支持离散和连续环境中的动态多人交互。该框架提供标准化评估协议、仿真环境及基线模型，使研究者能够系统评估导航智能体在复杂人类动态下的表现。核心实现基于 C++，集成 Habitat 等仿真平台，并为 VLN-CE 等连续导航场景提供评测支持。适合从事 VLN、人机交互及具身导航的研究人员使用。
- [**NavSpace：空间智能指令导航基准**](https://github.com/TidalHarley/NavSpace) - NavSpace是ICRA 2026提出的空间智能指令导航基准，专为VLN-CE（连续视觉语言导航）任务设计。该项目提供了评估导航代理遵循空间关系指令（如相对位置、方向描述）的标准框架，涵盖Habitat等3D环境，集成3D语义地图与指令解析模块。面向VLN研究者，旨在推动空间推理与指令跟随的结合。
- [**roomtour3d-NaviLLM：几何感知具身导航数据生成与零样本导航**](https://github.com/roomtour3d/roomtour3d-NaviLLM) - RoomTour3D 是一个面向具身导航的几何感知数据生成工具，能够从网络视频自动构建3D场景与导航指令对，无需人工标注。其 NaviLLM 方法将多模态大语言模型引入连续视觉语言导航（VLN-CE），通过零样本方式实现自然语言指令跟随与路径规划。关键技术包括自动视频结构化、3D重建与 LLM 推理，适用于 VLN 研究者和需要低成本仿真数据的从业者。
- [**r2r_spl：R2R SPL指标计算工具**](https://github.com/ros-sports/r2r_spl) - r2r_spl 是一个用于计算 Room-to-Room (R2R) 任务中 Success weighted by Path Length (SPL) 指标的轻量级 Python 工具。它直接针对 Vision-Language Navigation (VLN) 评估需求，帮助研究者在离散环境（如 Matterport3D 仿真器）中快速量化导航模型的路径效率与任务成功率。该脚本无需额外依赖，适合 VLN 论文复现与指标对比。目标用户为需要标准化评估 VLN 模型的研究者。
- [**vln_platform：可插拔多模型VLN评估与数据生成框架**](https://github.com/Winsleo/vln_platform) - VLN Platform 是一个面向视觉语言导航（VLN）领域的可插拔多模型评估与数据生成框架。它支持集成多种VLN模型进行统一评估，并提供自动化数据生成工具，帮助研究者快速验证和比较导航算法。该框架基于Python实现，强调模块化与可扩展性，适用于VLN模型开发与实验场景。目标用户为VLN研究人员和工程师。
- [**Single-Drone-VLN-Paper-List：单无人机VLN论文列表**](https://github.com/Rock3Yu/Single-Drone-VLN-Paper-List) - 该项目是一个专门收录单无人机视觉语言导航（VLN）相关论文的列表，聚焦于将VLN技术应用于无人机导航场景。它整理了领域内的关键文献，为研究无人机指令跟随与环境理解的研究人员提供集中资源。虽然项目暂无详细描述，但主题明确面向VLN子领域，直接符合收录标准。
- [**Rule-VLN: 通过语义推理与几何校正弥合感知与遵从**](http://arxiv.org/abs/2604.16993v1) - 本文提出 Rule-VLN，首个面向规约遵循的城市级视觉语言导航基准，包含 29k 节点和 177 类法规约束的 8k 限制节点，迫使智能体从仅关注物理可达转向语义合规。同时设计语义导航纠正模块 SNRM，利用粗到细 VLM 感知框架与认知心理地图实现零样本动态绕路规划。实验表明 Rule-VLN 显著挑战现有模型，而 SNRM 可缓解性能下降，将碰撞违规率降低 19.26%，任务完成率提升 5.97%，为安全合规 VLN 研究提供新标准与通用工具。
- [**无人机视觉语言导航：进展、挑战与研究路线图**](http://arxiv.org/abs/2604.13654v1) - 该论文首次对面向无人机的视觉语言导航（UAV-VLN）进行全面综述，系统梳理了从早期模块化方法到基于VLM、VLA及世界模型的端到端智能体的技术谱系，并详细梳理了仿真器、数据集与评测指标。其核心贡献在于建立UAV-VLN的清晰方法论分类，揭示当前导航系统在室外动态环境感知、语言模糊性推理及模型轻量化部署等关键瓶颈，为后续基于大模型的VLN研究提供了明确路线图。
- [**VLN-NF: 具备假前提指令的可行性感知视觉语言导航**](http://arxiv.org/abs/2604.10533v2) - 该工作针对现有VLN任务中指令前提均成立、目标总是存在的假设，提出了VLN-NF基准，引入假前提指令（目标物体在指定房间中不存在），要求智能体探索房间后显式输出NOT-FOUND。作者利用LLM改写原有VLN指令、VLM验证目标缺失来构建大规模数据，并设计REV-SPL指标同时衡量房间到达、探索覆盖与决策正确性。在此基础上，提出两阶段混合方法ROAM，结合监督式房间导航与基于LLM/VLM、自由空间先验的室内探索，有效克服了假前提下基线方法探索不足、过早终止的问题，推动了更真实、鲁棒的视觉语言导航研究。
- [**面向空中机器人的视觉语言导航：迈向大语言模型时代**](http://arxiv.org/abs/2604.07705v1) - 该综述系统梳理了面向无人机的视觉-语言导航（Aerial VLN）领域，提出了单指令与对话两种交互范式，并将现有方法划分为五类架构进行解析，重点评述了LLM/VLM的集成方式。文章直接以VLN为核心任务，回顾了专用数据集、仿真平台及评测指标，并对比了离散与连续动作、端到端与分层设计等架构权衡，为地面VLN之外的新场景提供了方法论参考。
- [**超越策略的交互基准：可复现的协同实例目标导航**](http://arxiv.org/abs/2604.00265v1) - 该论文提出首个可复现的协同实例目标导航基准QAsk-Nav，将基于自然语言对话的交互式问答与视觉导航分离评估，并设计了轻量级统一模型Light-CoNav，在开集泛化上超越现有协同导航方法。研究属于视觉-语言导航（VLN）的交互式目标导航子领域，通过人类对话消解视觉实例歧义，为评估VLN中的协作推理能力提供了系统化基准，有助于推动LLM/VLM驱动的导航agent研究。
- [**视觉语言导航最新进展综合综述**](https://openalex.org/W7139990939) - 该论文对视觉语言导航（VLN）领域的最新进展进行了全面综述，将现有工作按框架、模型、辅助模块和任务四个抽象层进行分类，系统分析了各方法的优势与局限，并整理了仿真环境与数据集。该综述直接以 VLN 为核心主题，不仅梳理了从架构创新到训练策略的整体脉络，还指出了当前挑战与未来方向，为 VLN 研究提供了结构化的全局视图。
- [**HUGE-Bench: 高层无人机视觉语言行动任务基准**](http://arxiv.org/abs/2603.19822v1) - 论文提出 HUGE-Bench，一个面向高层 UAV 视觉语言行动任务的基准，使用真实数字孪生场景与 3DGS-Mesh 混合表示，实现可扩展的轨迹生成和碰撞感知评估。该基准明确定位于 UAV VLN 领域，通过过程导向与安全评估指标，测量从高层语言指令到多阶段安全飞行的执行能力，揭示了现有 VLA 模型在语义完成与安全执行上的显著不足，为高层视觉语言导航提供了诊断性测试平台。
- [**NavTrust: 具身导航可信性统一基准**](http://arxiv.org/abs/2603.19229v1) - NavTrust 首次构建了面向视觉语言导航（VLN）的统一可信基准，系统地在 RGB、深度和指令等输入模态中引入真实 corruptions，评估当前主流 VLN 模型（如 Uni-NaVid、ETPNav）的性能退化，并探索数据增强、多模态融合等缓解策略。该基准不仅量化了 VLN 智能体在现实干扰下的脆弱性，还在真实机器人上验证了鲁棒性提升方案，为研发安全、可信的 VLN 系统提供了重要测试平台。
- [**CoT-VLNBench: 视觉链式推理导航机器人基准**](https://openalex.org/W7139011883) - 该文提出首个面向四足机器人视觉语言导航的链式推理基准CoT-VLNBench，含17.5万帧、525万三维边界框与87.5万视觉问答对，细粒度标注推理轨迹。同时设计7B参数的CoT-VLN模型，整合视觉、语言与推理模块，实现可解释导航，显著优于非VLM基线。该资源为VLN的感知与逐步推理能力评估提供了关键支撑。
- [**CapNav: 基于能力条件的室内导航视觉语言模型基准**](http://arxiv.org/abs/2602.18424v1) - CapNav提出了一个能力条件导航基准，用于评估视觉语言模型（VLMs）在室内VLN任务中对智能体不同物理能力（如尺寸、移动性）的推理能力。基准包含45个真实场景、473个导航任务和2365个QA对，覆盖五种典型代理。评估13个现代VLM发现，导航性能随能力限制收紧急剧下降，且模型难以推理空间尺寸。该工作为能力感知的VLN研究提供了新的评测标准，并揭示了当前模型在具身空间推理中的不足。
- [**大规模模型增强的视觉语言导航：最新进展、实际应用与未来挑战**](https://openalex.org/W7128526819) - 本文系统综述了大型模型增强的视觉语言导航（VLN）最新进展，涵盖指令理解、环境感知、高层规划、低层控制等核心模块，并分析了边缘部署、Sim2Real迁移及任务演化，为LLM/VLM驱动的VLN提供结构化评估与未来方向。
- [**LangMap: 开放词汇目标导航分层基准与大规模数据集**](http://arxiv.org/abs/2602.02220v1) - 本文提出 HieraNav 多粒度开放词汇目标导航任务，并构建大规模基准 LangMap，为室内3D扫描提供场景、房间、区域、实例四层语义目标及18K+导航任务。LangMap 利用自然语言描述目标位置，实现可评价不同指令风格的导航，其标注质量在判别性准确性上超越 GOAT-Bench 23.8%。零样本与有监督模型实验表明，丰富上下文与记忆能提升成功率，但长尾、小体积、上下文依赖和远距离目标仍具挑战。该基准为语言驱动的具身导航提供了严格测试平台，直接扩展了 VLN 中 REVERIE 等目标指向任务，推动开放词汇指令遵循的研究。
- [**AirNav: 大规模真实世界无人机视觉语言导航数据集**](https://openalex.org/W7119557735) - 该论文提出AirNav，首个基于真实城市空中数据的大规模无人机视觉语言导航（VLN）数据集，摆脱对合成环境的依赖，提供自然多样的指令，弥补现有UAV VLN基准的不足。同时引入AirVLN-R1模型，结合监督微调与强化微调策略提升泛化能力，并通过初步真实世界飞行实验验证可行性。工作为无人机VLN研究提供了高保真基准和端到端学习方案，推进了语言引导的空中自主导航。
- [**VLN-MME：将MLLM诊断为语言引导视觉导航智能体**](http://arxiv.org/abs/2512.24851v2) - 该工作构建了统一、可扩展的评估框架 VLN-MME，将传统视觉语言导航（VLN）数据集（如 R2R、REVERIE 等）桥接到标准化的零样本代理测试中，系统诊断多模态大模型（MLLMs）在语言引导视觉导航任务上的能力。主要贡献在于发现链式思考与自反思策略反而导致性能下降，揭示了当前 MLLMs 在具身导航中 3D 空间推理与情境感知的显著缺陷。该基准为 VLN 领域的通用 MLLMs 代理评估提供了模块化设计，可直接用于对比不同模型架构、代理设计及导航任务，并为后续 MLLMs 后训练提供指导。
- [**VL-LN Bench: 面向长程目标导向导航的主动对话基准**](http://arxiv.org/abs/2512.22342v4) - 论文提出交互式实例目标导航任务（IIGN）与 Vision Language-Language Navigation (VL-LN) 基准，首次在视觉语言导航中引入主动对话，允许 agent 通过自然语言与 oracle 交互以消除指令歧义。该基准自动生成了超 4.1 万条长程对话增强轨迹，并提供可评估对话能力的自动化协议。实验表明，融合对话的导航模型在模糊指令下显著优于基线，推动了 VLN 从静态指令跟随向交互式视觉语言导航的演进，为真实场景中的人机协作导航提供了新数据与方法。

## 仿真器与框架
*用于训练和评估VLN智能体的环境。*
- **[仿真器名称]** – 简短描述。 [Website](链接) | [GitHub](链接)


- [**Habitat-Lab：模块化具身AI高阶库**](https://github.com/facebookresearch/habitat-lab) - Habitat-Lab 是一个模块化高阶库，用于训练具身 AI 代理，支持多种任务和环境。其核心平台 Habitat 模拟器直接集成视觉语言导航（VLN）任务（如 VLN-CE、R2R），提供 Matterport3D 等 3D 场景和强化学习训练框架。通过灵活的传感器接口和任务 API，研究者可快速部署并评估 VLN 模型。适合具身 AI 与 VLN 研究人员。
- [**LH-VLN：长程视觉语言导航平台与基准**](https://github.com/HCPLab-SYSU/LH-VLN) - 该项目提供了一个面向长程视觉语言导航（Long-Horizon VLN）的完整平台、基准数据集和基线方法，发表于CVPR 2025。它构建了包含复杂指令和多步骤导航任务的仿真环境，并提出了新的模型以解决长程规划与视觉-语言对齐问题。适用于研究持续导航、LLM/VLM规划器以及跨场景泛化的VLN研究者。
- [**Matterport3DSimulator：基于真实全景图像的强化学习研究平台**](https://github.com/peteanderson80/Matterport3DSimulator) - Matterport3DSimulator是一个基于真实全景图像的强化学习研究平台，专门为视觉-语言导航（VLN）任务设计。它集成Matterport3D数据集，支持在真实3D场景中执行指令跟随（如R2R、RxR等），提供导航图、多视角观察和交互式环境。该项目是VLN领域最基础的模拟器之一，广泛应用于训练和评估多种VLN代理，涵盖离散图导航和连续控制。目标用户为VLN、具身导航和跨模态强化学习研究者。
- [**Open-Nav：连续环境零样本VLN开源实现**](https://github.com/YanyuanQiao/Open-Nav) - Open-Nav 是用于连续环境中的零样本视觉语言导航（VLN）的开源实现，发表于 ICRA 2025。它利用开源大语言模型（LLMs）作为规划器，结合视觉语言模型进行场景理解和指令跟随，无需预训练或导航图。该框架适用于无边界 3D 环境下的指令导航任务，目标用户为 VLN 与具身智能研究者。
- [**OnFly：无人机零样本空中视觉语言导航框架**](https://github.com/Robotics-STAR-Lab/OnFly) - OnFly是一个面向无人机的零样本空中视觉语言导航（VLN）框架，旨在实现安全高效的基于自然语言指令的飞行控制。它利用预训练的视觉-语言模型实现跨模态理解与零样本泛化，无需针对特定环境训练即可在真实世界执行导航任务。项目包含完整的感知、规划与控制模块，为空中机器人VLN研究提供了可直接使用的开源实现。适用于从事无人机、零样本导航和视觉-语言接地的研究人员。
- [**Co-NavGPT2：基于视觉语言模型的协作语义导航框架**](https://github.com/ybgdgh/Co-NavGPT2) - Co-NavGPT2是一个基于视觉语言模型的协作语义视觉导航框架，通过多智能体交互和语义场景理解实现指令跟随与路径规划。它利用VLM进行环境语义解析和跨智能体通信，适用于复杂室内环境的协同导航任务。该项目面向多机器人协作和视觉-语言导航研究，展示了VLM在连续VLN中的潜力。
- [**genisom_vln：面向四足机器人的VLN框架**](https://github.com/zsibot/genisom_vln) - 该项目是一个面向四足机器人的Vision-Language Navigation (VLN) 框架，将MATRiX仿真环境与LLM/VLM驱动的导航能力相结合。它提供了零样本基线方法，并支持通过HuggingFace、Ollama及云端API调用大模型进行指令跟随与导航决策。适用于希望利用LLM/VLM实现四足机器人自主导航的研究者和工程师。
- [**CoMaR：协作地图与路线策略学习用于连续VLN**](https://github.com/VIPL-EPP/CoMaR) - CoMaR 提出协作地图与路线策略学习方法，用于连续视觉语言导航（VLN-CE）。通过联合利用环境地图和预设路线进行决策，提升指令跟随的鲁棒性和效率。基于 Python 实现，面向连续 VLN 研究的科研人员。
- [**OVN-Map.github.io：单目开放词汇3D语义建图用于VLN**](https://github.com/xpu206/OVN-Map.github.io) - OVN-Map 提出单目开放词汇 3D 语义建图方法，专门为视觉-语言导航（VLN）任务设计。它利用开放词汇语义分割与单目深度估计，实时构建包含物体语义信息的3D地图，使智能体能够根据自然语言指令进行零样本或适应性的导航。项目面向VLN和具身智能研究人员，提供了开源代码与网页演示。
- [**VLN-Framework：面向VLN的认知架构研究框架**](https://github.com/thumathlon/VLN-Framework) - VLN-Framework 是一个专为视觉语言导航（VLN）设计的认知架构研究框架，提供模块化的规划、感知与推理组件，支持集成大型语言模型（LLM）以增强指令理解与决策。该框架基于Python实现，便于研究者快速构建和对比不同导航策略，适用于VLN、持续VLN（VLN-CE）以及LLM驱动的导航智能体开发。目标用户为从事VLN及相关多模态导航研究的研究人员与开发者。
- [**vision-language-navigation：基于CLIP和ROS2的机器人导航**](https://github.com/rohitmekkoth/vision-language-navigation) - 该项目利用CLIP模型和ROS2框架，实现基于自然语言指令的机器人导航。通过融合视觉和语言信息，机器人能够理解指令并规划路径，直接服务于Vision Language Navigation任务。适合研究视觉语言导航与机器人集成的基础应用。
- [**MapReAct-VLN：基于动态语义地图的推理行动VLN框架**](https://github.com/luohongk/MapReAct-VLN) - MapReAct-VLN是一个基于动态语义地图的Map-Guided ReAct框架，专为视觉语言导航（VLN）设计。它将ReAct（推理+行动）循环与语义地图相结合，通过实时构建和理解环境语义信息，使智能体能够根据自然语言指令进行导航决策。该框架融合了语义建图、多模态推理和行动规划技术，适用于室内导航场景。目标用户为VLN、具身导航、语义地图和LLM/VLM驱动智能体的研究人员。
- [**NaVILA：腿足机器人视觉-语言-动作导航模型**](https://github.com/AnjieCheng/NaVILA) - NaVILA 是为腿足机器人设计的视觉-语言-动作导航模型（RSS'25），核心创新在于利用预训练的视觉-语言模型（VLM）作为规划器，将自然语言指令直接映射为连续控制动作，显著提升在复杂地形中的零样本导航能力。项目基于 Habitat 仿真平台实现，并适用于真实腿足机器人部署，适合从事 VLM-based 导航及连续 VLN 的研究者。
- [**habitat-gs：基于动态高斯泼溅的高保真导航模拟器**](https://github.com/zju3dv/habitat-gs) - Habitat-GS 是一个基于动态高斯泼溅（Dynamic Gaussian Splatting）的高保真导航模拟器，专为具身智能和视觉语言导航（VLN）任务设计。它扩展了 Habitat 平台，支持连续 VLN（VLN-CE）场景，通过实时渲染动态场景提供逼真的交互环境。项目采用 C++ 实现，集成高斯化身技术，适用于室内导航、机器人仿真和视觉-语言 grounding 研究。目标用户是 VLN、具身 AI 和机器人领域的研究者与开发者。
- [**vln_gazebo_simulator：基于Gazebo的VLN仿真器**](https://github.com/Tipriest/vln_gazebo_simulator) - 该项目是一个基于 Gazebo 的视觉语言导航（VLN）仿真器，提供类似 Turtlesim 的简易环境，支持键盘和摇杆控制。它专为 VLN 算法测试而设计，可直接用于指令跟随、连续导航等任务的原型验证，适合 VLN 研究人员和开发者快速迭代。
- [**AeroAct：空中无人机视觉语言导航统一框架**](https://github.com/return-sleep/AeroAct) - AeroAct 是一个面向空中无人机平台的视觉语言导航（VLN）统一框架，融合空间、时序与具身推理能力。项目采用深度学习模型，支持无人机在三维环境中根据自然语言指令执行导航任务，并提供了配套数据集与仿真接口。适合从事空基 VLN 研究的研究人员与开发者。
- [**AirVLN：视觉语言导航开源工具包**](https://github.com/AirVLN/AirVLN) - AirVLN 是一个专注于视觉语言导航（VLN）的开源项目，基于 Python 实现。它提供了 VLN 任务的模型训练、推理和评估工具，支持 R2R、RxR 等主流基准，并与 Matterport3D、Habitat 等仿真环境集成。适合研究人员和工程师用于 VLN 模型开发与复现。
- [**VLN-Reproduction：UniNavid复现与通用VLN硬件框架**](https://github.com/beijieyuyin/VLN-Reproduction) - 该项目是Uninavid的复现实现，提供了一个统一的通用VLN（视觉语言导航）硬件框架。它旨在集成多种导航模块，支持在真实或仿真环境中执行基于指令的导航任务。技术实现基于Python，适合研究VLN硬件加速和系统部署的开发者。
- [**OmniNav：统一视觉语言导航框架与前向探索**](https://github.com/amap-cvlab/OmniNav) - OmniNav 是一个统一的视觉语言导航（VLN）框架，集成了前瞻性探索机制，通过预测未来状态来指导智能体在未知环境中执行导航指令。该项目提供了 ICLR 2026 论文的官方实现，支持连续 VLN（VLN-CE）与零样本导航场景，基于 PyTorch 开发，适用于室内外导航任务。目标用户为 VLN 领域的研究者和开发者。
- [**Vision-and-Language-Navigation：生产就绪的VLN实现**](https://github.com/kryptologyst/Vision-and-Language-Navigation) - 该项目提供了一个生产就绪的Vision-and-Language Navigation（VLN）实现，结合先进的计算机视觉和自然语言处理技术。它与VLN任务直接相关，涵盖指令跟随、视觉语言接地等核心功能，适用于研究人员和开发者快速部署VLN系统。
- [**MAVLN：多无人机视觉语言导航框架**](https://github.com/reinshift/MAVLN) - MAVLN 是一个面向多无人机（UAV）的视觉语言导航（Vision Language Navigation）框架，将经典的单智能体 VLN 扩展为多智能体协同场景。该项目通过融合视觉输入与自然语言指令，实现无人机集群在未知环境中的联合路径规划与目标搜索，支持多智能体通信与分布式决策。基于 Python 实现，适合研究多机器人导航、空地协同与多智能体强化学习的学者。
- [**VLN-PRET：VLN预训练代码库**](https://github.com/iSEE-Laboratory/VLN-PRET) - 该项目名为VLN-PRET，推测是一个面向Vision-Language Navigation（VLN）的预训练代码库，可能包含模型实现或训练脚本。由于仓库无详细描述，无法确认具体技术细节。目标用户为VLN研究人员和开发者。
- [**重新思考视觉语言导航中的具身鸿沟：物理与视觉差异的整体研究**](http://arxiv.org/abs/2507.13019v2) - 该论文提出了物理现实VLN平台VLN-PE，首次在真实机器人（人形、四足、轮式）上系统评估了多种自我中心VLN方法，包括单步离散动作分类、扩散密集航点预测和基于地图的LLM规划。研究揭示了由于观测空间受限、光照变化及碰撞摔倒等物理因素导致的性能显著退化，并强调该方法可扩展至MP3D之外的场景。这为改善跨具身VLN模型的鲁棒性和适应性提供了新路径。
- [**InternNav-ros2：InternVLA-N1的ROS2部署方案**](https://github.com/yubincho3/InternNav-ros2) - 项目为 InternVLA-N1 的 DualVLN 视觉语言导航模型提供 ROS 2 部署方案，将 GPU 推理服务器与 Unitree Go2 机器人客户端分离，通过 zenoh 通信实现在真实四足机器人上的指令跟随导航。适用于需要在物理机器人上部署 VLN 模型的研究者。
- [**XR-VLN：利用扩展现实辅助收集VLN数据集**](https://github.com/FaAlvn/XR-VLN) - 该项目利用扩展现实（XR）技术辅助收集视觉语言导航（VLN）数据集，通过沉浸式交互环境高效采集导航指令与对应视觉轨迹，为VLN模型训练提供定制化数据支持。技术实现可能涉及VR/AR设备集成与数据标注流程，目标用户是需要自定义VLN数据集的研究者。

## 数据集
*标准数据集与任务定义（R2R、REVERIE、VLN-CE等）。*
- **[数据集名称]** – 描述。 [Paper](链接)

---


- [**ALFRED：日常任务指令跟随基准与仿真平台**](https://github.com/askforalfred/alfred) - ALFRED是面向日常任务的基准数据集和仿真平台，专注于视觉语言导航中的指令跟随与接地理解。它提供带有自然语言指令的3D房间场景，要求智能体根据指令执行一系列子任务（如清理、加热），强调视觉-语言-动作的联合推理。该项目基于AI2-THOR仿真环境，适用于训练和评估VLN及具身问答模型，是跨模态导航和持续导航研究的关键资源。目标用户为从事指令跟随、具身人工智能及视觉语言接地的研究人员。
- [**NaVILA-Bench：基于Isaac Lab的VLN基准测试平台**](https://github.com/yang-zj1026/NaVILA-Bench) - NaVILA-Bench 是一个基于 Isaac Lab 的视觉语言导航（VLN）基准测试平台。它提供了标准化的评估环境和指标，用于测试和比较 VLN 模型在仿真环境中的性能。项目集成了 Habitat 和 Isaac Sim 等模拟器，支持连续空间导航（VLN-CE）和离散图导航任务，目标用户为从事 VLN 研究开发和基准测试的研究人员与工程师。
- [**REVERIE：远程具身视觉指代表达经典数据集**](https://github.com/YuankaiQi/REVERIE) - REVERIE 是面向远程具身视觉指代表达的经典 VLN 任务与数据集，要求智能体在真实室内环境中根据自然语言指令导航至远程物体并完成指代。其基于 Matterport3D 场景构建，提供了大规模的物体级导航-指代配对样本，是 VLN 领域基础性 benchmark 之一。适用于研究跨模态指令跟随、物体定位与具身导航的科研人员。
- [**R2RIE-CE：指令错误检测与定位基准数据集**](https://github.com/intelligolabs/R2RIE-CE) - 该仓库为 VLN 提供了首个指令错误检测与定位基准数据集 R2R-IE-CE（基于 R2R-CE），并提出了 IEDL 方法。通过标注指令中的不一致、冗余、缺失等错误，结合多模态特征进行错误检测与定位，适用于提升导航系统的鲁棒性。目标用户为研究 VLN 错误分析与鲁棒性的科研人员。
- [**LAMBDA：语言指导长期导航基准**](https://github.com/h2r/LAMBDA) - LAMBDA是一个面向语言指导的长期导航（房间到房间、楼层到楼层）基准测试，提供模拟和真实环境中的专家演示数据集。它与VLN直接相关，专注于长时程指令跟随和多模态导航规划。项目包含多模态匹配和演示收集工具，适合研究长期导航、指令理解和模拟到现实迁移的研究人员。
- [**CorNav-Site：开放集零样本VLN多任务基准站点**](https://github.com/mligg23/CorNav-Site) - 该项目是论文“MO-VLN: A Multi-Task Benchmark for Open-set Zero-Shot Vision-and-Language Navigation”的官方站点，提供了一个面向开放集零样本视觉语言导航的多任务基准测试平台。它通过定义多个子任务和评估指标，支持在复杂环境中评估VLN代理的泛化能力。该站点为VLN研究者提供了基准数据、任务定义和结果参考，适合从事零样本、开放集VLN研究的科研人员使用。
- [**MDE-AgriVLN：农业场景视觉-语言导航数据集**](https://github.com/AlexTraveling/MDE-AgriVLN) - MDE-AgriVLN是一个面向农业场景的视觉-语言导航（VLN）项目，通过单目深度估计（MDE）增强智能体在复杂农田环境中的空间理解与路径规划能力。该项目在ICIC 2026上以Oral形式发表，主要将VLN任务拓展至农业领域，利用深度信息提升指令跟随与避障性能，适用于农业机器人及户外导航研究。
- [**OpenFly：空中视觉语言导航工具链与大规模基准**](https://github.com/Eziotic/OpenFly) - OpenFly 是一个面向空中视觉-语言导航（Aerial VLN）的多功能工具链和大规模基准平台。它提供无人机场景下的指令跟随与导航评估，集成微调大语言模型（LLM）和视觉-语言模型（VLM）能力，支持从数据集构建到模型训练的全流程。该项目扩展了传统室内VLN任务到三维空域环境，为研究跨场景、多模态空中导航提供了标准化测试平台。适合从事陆空机器人导航、VLM规划器的研究者和开发者。
- [**FloorPlan-VLN：楼层平面图引导的视觉语言导航新范式**](http://arxiv.org/abs/2603.17437v1) - 该工作提出FloorPlan-VLN新范式，利用结构化的语义楼层平面图作为全局空间先验，使智能体仅依据简洁指令即可导航。作者构建了包含1万余条轨迹、跨越72个场景的FloorPlan-VLN数据集，并设计了FP-Nav方法，通过双视图时空对齐视频序列和辅助推理任务，有效对齐观察、平面图与指令。该方法在导航成功率上相对基线提升超60%，并验证了对动作漂移与平面图失真的鲁棒性，为利用建筑平面图提升VLN的空间推理能力开辟了新方向。
- [**细粒度对齐监督在视觉语言导航中的重要性**](https://openalex.org/W7126038551) - 该论文聚焦视觉语言导航中的细粒度跨模态对齐问题，首次引入人工标注的细粒度数据集Landmark-RxR，为VLN提供精准的地标级别监督。通过重新设计数据增强、训练范式、奖励塑形和导航损失等核心组件，充分挖掘细粒度数据的潜力，并设计了全新的评估机制。实验表明，细粒度监督能有效提升智能体对指令与轨迹的精确对齐能力，显著改善VLN任务中的跨模态理解。
- [**视觉语言导航中的室内场景识别**](https://openalex.org/W4417470533) - 该工作针对视觉语言导航（VLN）中室内场景识别能力不足的问题，提出Room-to-Room场景识别数据集R2R-SR，含来自Matterport3D的7283张图像、10个房间类别，用以增强VLN代理的空间感知。为解决类别不平衡，提出基于Llava和Stable Diffusion的全景环境数据增强方法LSDA，使模型在室内识别Top-1准确率达75.9%，超越主流CNN与ViT方法。该数据集与方法可直接集成到VLN流水线中，提升指令跟随与跨房间泛化能力。
- [**VLN-ChEnv：可变化环境下的视觉语言导航**](https://openalex.org/W4415539951) - 该论文提出ImperfectVLN任务与数据集，针对真实环境下指令与场景不完全匹配的三种情形（可导航性变化、错误地标引用、错误方向描述）评估视觉语言导航智能体。作者分析现有SOTA模型在路径阻断或地标移除时的性能波动，并设计反思模块让智能体回顾历史以识别错误，在ImperfectVLN上带来4.4%的性能提升。这项工作为动态变化环境中的实用VLN提供了新基准与优化思路。
- [**ToolNavigator：建筑工地小工具处理与视觉语言导航仿真数据集**](https://openalex.org/W4414432070) - 论文提出 ToolNavigator，首个面向建筑工地场景的小工具处理与视觉语言导航（VLN）仿真数据集，融合 Blender 与 NVIDIA Isaac Sim 生成包含 543 种小工具、102 类设备和 22 类重型机械的多样化环境，并提供 2D/3D 边界框、深度图、语义掩码及场景图等丰富多模态标注。实验表明现有 VLN 模型（如 Maplm）在该数据集上导航成功率仅 48.9%-53.2%，凸显工地环境下 VLN 任务的挑战性，为 AI 驱动建筑自动化提供了重要基准。
- [**HAVEN：从人类指导到助手的演化网络视觉语言导航**](https://openalex.org/W7105668490) - 该论文提出了一种新场景 Human Assistant VLN (HA-VLN)，由原本的导航指导者变为人类助手，并基于 Room-to-Room (R2R) 重构了 Room to Room Assistant (R2RA) 数据集。为应对 HA-VLN 任务中指令处理的挑战，作者设计了结合大语言模型与记忆系统的 HAVEN 网络，实现了从主流 VLN 方法到 HA-VLN 的范式迁移，无需额外信息即可完成路径规划。实验表明 HAVEN 能提升成功率、缩短路径并降低导航错误，可作为端到端模块集成到任意 VLN 方法中，对复杂现实场景下的视觉语言导航具有重要应用价值。
- [**生成包含细粒度对齐标注的视觉语言导航指令**](http://arxiv.org/abs/2506.08566v1) - 本文提出FCA-NIG框架，自动生成带有子指令-子轨迹和实体-地标双重细粒度对齐的导航指令。基于该框架构建了FCA-R2R数据集，是首个大规模细粒度对齐增强数据集。实验表明，使用FCA-R2R训练能显著提升多个VLN智能体（如SF、EnvDrop、RecBERT、HAMT）的导航性能，尤其在状态感知和动作决策上。该工作为VLN指令生成和跨模态对齐提供了高质量数据支撑，强化了VLN模型的精细理解能力。
- [**利用GPS与NLP自动生成自动驾驶车辆VLN数据集指令-动作对**](http://arxiv.org/abs/2505.03174v1) - 论文提出一个自动化数据收集系统 ADVLAT-Engine，利用移动 GPS 应用的语音导航指令与同步视频，无需人工标注即可生成大规模视觉-语言-动作三元组，并将指令细分为八类。该方法专门面向自动驾驶中的视觉语言导航（VLN）任务，旨在为 VLN 模型快速扩充指令-动作训练对，显著降低数据构建成本，推动 VLN 数据集的规模化建设。
- [**利用GPS和NLP自动生成自动驾驶车辆VLN数据集**](https://openalex.org/W4415247599) - 本文提出利用GPS语音指令与NLP自动生成指令-动作对的方法，并构建了ADVLAT-Engine数据采集系统，可自动生成包含视觉、语言和动作三元组的VLN数据集。系统将GPS指令分为八类，结合行车视频形成完整数据，旨在降低VLN数据标注成本、加速高质量数据池构建。该方法直接服务于视觉语言导航任务，为训练自动驾驶车辆的VLN模型和人类交互式系统提供基石，对大规模VLN数据集生产具有实用价值。
- [**OpenFly：面向空中视觉语言导航的综合平台**](http://arxiv.org/abs/2502.18041v7) - 论文提出 OpenFly，一个面向空中视觉语言导航（VLN）的综合性平台。它集成 Unreal Engine、3D Gaussian Splatting 等渲染引擎与全自动数据采集工具链，构建了涵盖 18 个场景、10 万条轨迹的大规模空中 VLN 数据集，并设计了关键帧感知的导航模型 OpenFly-Agent。该工作填补了户外空中 VLN 缺乏基准的空白，通过在真实感仿真环境中复现并评估现有 VLN 方法，展示了平台的有效性，推动 VLN 从室内向大范围空中场景扩展。
- [**NavRAG：基于检索增强LLM生成用户需求导航指令**](http://arxiv.org/abs/2502.11142v3) - NavRAG 提出一种检索增强生成框架，通过 LLM 构建从全局到细节的分层场景描述树，模拟多种用户角色和需求，自动生成符合人类沟通风格的高层导航指令。该工作针对视觉语言导航（VLN）训练数据稀缺问题，在 861 个场景中生成超 200 万条指令，大幅降低人工标注成本，并提升导航模型对用户需求多样化表达的理解与执行能力。
- [**通用场景适应视觉语言导航**](http://arxiv.org/abs/2501.17403v1) - 该论文提出通用场景适应视觉语言导航（GSA-VLN）任务，要求代理在特定场景中执行导航指令并同时适应环境以提升性能。为此构建了 GSA-R2R 数据集，大幅扩展 R2R 的环境和指令的数量与多样性，并设计三阶段 LLM 编排流水线，通过 speaker 生成与角色扮演生成不同说话风格的指令，模拟真实用户的个性化表达。该工作将 VLN 从一次性零样本评估扩展到持久场景的持续适应，为室内 VLN 的实用化提供了新基准与数据支撑。
- [**通过数据合成增强连续环境下的视觉语言导航**](https://openalex.org/W4412446586) - 该论文针对连续环境下的视觉语言导航（VLN-CE）数据稀缺问题，提出了一种无需人工标注的多模态数据合成方法。通过计算最短路径、使用阈值筛选关键动作与关键帧，并借助大规模预训练模型 CLIP 预测新名词来替换指令模板中的实体，自动生成新的 VLN-CE 指令。实验表明，该方法生成的大规模合成数据能有效提升 VLN-CE 模型的导航性能，为 VLN-CE 的数据增强提供了新思路。
- [**DynamicVLN：将动态性引入视觉语言导航场景**](https://openalex.org/W4406235035) - 该文提出了 DynamicVLN 任务，将传统静态 VLN 拓展到包含车辆移动、行人动态和天气变化的动态驾驶场景，旨在提升 agent 的实时适应与推理能力。作者基于 CARLA 模拟器与 LLM 构建了含 11,261 个动态导航实例的数据集，并设计了一个融合感知与决策模块的基线模型，证明其在遵循语言指令的同时能灵活应对环境变化。该工作为 VLN 从静态室内走向动态室外提供了新基准与模型框架。
- [**视觉语言导航与具身问答的场景理解**](https://openalex.org/W7106233847) - 论文提出Room Tour3D，一个由网络室内漫游视频重建的大规模视频指令导航数据集，包含约10万条轨迹和20万条导航指令，覆盖1847个真实环境。该数据集将非结构化的在线视频转换为带房间类型、物体位置和空间几何等标注的结构化轨迹，为VLN提供了开放世界的人类行走路径与导航指令。实验显示，Room Tour3D在CVDN、SOON、R2R和REVERIE等多个主流VLN基准上均带来显著性能提升，有效缓解了现有VLN数据多样性与规模不足的问题，拓展了具身导航的训练与评估场景。
- [**NAVCON：认知启发与语言接地的视觉语言导航语料库**](http://arxiv.org/abs/2412.13026v2) - 论文提出NAVCON语料库，基于R2R和RxR两个VLN数据集构建，引入四个认知驱动的导航概念，设计了大规模银标注算法，自动标注大约30,000条导航指令中的语言实现，并同步配对导航执行视频与2.7百万张对齐图像。共生成236,316个概念标注，经人评价和概念检测模型训练双重验证，为视觉语言导航领域首个全面的导航概念资源，同时利用GPT-4o展示了良好的少样本概念识别性能。
- [**RoomTour3D：面向具身导航的几何感知视频指令调优数据集**](http://arxiv.org/abs/2412.08591v2) - 该论文提出RoomTour3D，一个从真实室内房间游览视频构建的几何感知视频-指令数据集，通过3D重建获取带房间类型、物体位置和3D形状的行走轨迹，并与开放世界导航指令对齐。数据集包含约10万条轨迹和20万条指令，覆盖CVDN、SOON、R2R和REVERIE等标准VLN任务，实验证明了其对多项任务的显著提升，并首次展示了利用该数据训练零样本VLN智能体的可能性，推动了向开放世界导航的迈进。
- [**AdaVLN：面向连续室内环境中移动人类的视觉语言导航**](http://arxiv.org/abs/2411.18539v3) - 本文提出自适应视觉语言导航（AdaVLN）任务，通过在连续室内环境中引入动态移动的人体障碍物，拓展传统 VLN 到更逼真的设定。核心贡献包括 AdaVLN 模拟器和从 R2R 衍生的 AdaR2R 数据集，支持在 Matterport3D 中直接加入全身动画角色，并设计“冻结时间”机制以保障跨硬件公平对比。实验评估了多个基线，展示了 AdaVLN 在缩小学术研究与应用现实差距方面的潜力。
- [**NavAgent：面向室外城市无人机的多尺度街景融合具身VLN**](http://arxiv.org/abs/2411.08579v1) - 论文提出NavAgent，首个面向室外城市无人机的具身视觉语言导航模型，利用大视觉语言模型融合拓扑地图、全景和细粒度地标等多尺度环境信息实现导航。作者构建了地标识别器GLIP和动态场景拓扑图，并开发了NavAgent-Landmark2K数据集用于训练地标识别。该方法将VLN从室内地面机器人拓展至室外无人机场景，解决了城市环境细粒度地标匹配与多模态信息编码难题。
- [**零样本物体中心指令跟随：融合基础模型与传统导航**](http://arxiv.org/abs/2411.07848v3) - 本文提出 LIFGIF，一种零样本物体中心指令跟随方法，利用因子图融合语言推断，在未知环境中无需预存地图即能跟随自然语言指令进行导航。同时构建了 Object-Centric VLN (OC-VLN) 数据集，专门评估物体中心的视觉语言导航性能，并将 LIFGIF 与现有的 VLN 和物体目标导航方法对比，取得全面提升。最后在 Boston Dynamics Spot 机器人上实现真实世界演示，验证了方法的实用性。
- [**VLA-3D：面向3D语义场景理解与导航的数据集**](http://arxiv.org/abs/2411.03540v1) - 该论文构建了 VLA-3D 数据集，面向室内视觉与语言引导的导航任务，包含 11.5K 个 3D 扫描房间、语义场景图和 970 万条关注空间关系的指称语句。它为 VLN 研究提供了三维点云、可导航空间标注和自然语言指令，旨在评测具身导航模型在开放世界中的鲁棒性。该数据集可直接用于语言指令驱动的物体目标导航（ObjectGoal Navigation），为多模态 VLN 智能体提供了新的实验平台。
- [**HM3D-OVON：开放词汇物体目标导航数据集与基准**](http://arxiv.org/abs/2409.14296v1) - 该论文提出了HM3D-OVON，一个大规模开放词汇物体目标导航基准，基于真实3D场景提供超过15k个标注实例和379个物体类别，支持以自由文本指定目标。该数据集和评估框架直接服务于语言引导的具身导航，可以看作对REVERIE等视觉-语言导航任务的扩展，推动智能体在开放语义下灵活搜索任意物体，为VLN中的物体目标导航分支提供了高质量训练与测试平台。

## 方法

### 基础模型与预训练
*面向VLN的视觉-语言编码器与通用表征。*
- **[论文]** (作者, 年份) – 核心贡献。 [Code](链接)

### 离散/基于图的VLN
*在预定义连接图上导航（经典R2R与RxR设置）。*
- **[论文]** (作者, 年份) – 值得关注的技术。 [Code](链接)

### 连续VLN (VLN-CE)
*在三维空间中自由移动，无图假设。*
- **[论文]** (作者, 年份) – 如何处理连续动作空间。 [Code](链接)

### 基于地图与规划
*用于长时域规划的显式或隐式地图。*
- **[论文]** (作者, 年份) – 建图方法。 [Code](链接)

### 基于VLM/LLM的智能体
*使用冻结或微调的大语言/视觉模型进行零样本或少样本导航。*
- **[论文]** (作者, 年份) – VLM/LLM的作用。 [Code](链接)

### 世界模型与预测规划
*学习预测未来观测或轨迹以指导决策。*
- **[论文]** (作者, 年份) – 预测模型架构。 [Code](链接)

### 语义导航与场景图
*三维场景图、物体关系与结构化知识，用于可迁移的导航。*
- **[论文]** (作者, 年份) – 语义结构的使用。 [Code](链接)

---


- [**AgentNav：零样本稀疏引导长距离城市视觉导航**](https://github.com/Utkarsh-Mishra444/Sparsely-Grounded-Long-Range-Navigation) - AgentNav 是一个面向真实城市环境的零样本稀疏引导长距离视觉导航框架，核心利用多模态大语言模型（MLLM）实现无需预定义路径的指令跟随与导航决策。该项目在 EACL 2026 以 Oral 论文形式发表，明确定位于 Vision-Language Navigation（VLN）任务，特别适合城市级无图导航场景。目标用户为从事零样本、稀疏引导及跨模态导航研究的 VLN 学者。
- [**JanusVLN：解耦语义与空间特征的双重隐式记忆VLN方法**](https://github.com/MIV-XJTU/JanusVLN) - JanusVLN 是 ICLR2026 官方实现，用于视觉-语言导航（VLN）中解耦语义与空间特征的双重隐式记忆方法。该框架利用 LLM/MLLM 增强导航指令理解与空间推理，在经典 R2R/RxR 等基准上实现 SOTA。适合研究 VLN 中语义-空间解耦、隐式记忆机制及多模态导航的学者。
- [**GPT4Scene与VLN-R1：从视频理解3D场景的视觉语言导航**](https://github.com/Qi-Zhangyang/GPT4Scene-and-VLN-R1) - 该项目提出GPT4Scene，利用视觉语言模型从视频中理解3D场景，并包含VLN-R1模型，专门面向视觉语言导航任务。通过将视频场景解析与语言指令结合，提升导航代理在复杂环境中的空间理解与指令跟随能力。核心技术包括视觉语言模型、3D场景图构建和跨模态对齐。适合VLN研究者及需要强场景理解能力的具身智能系统开发者。
- [**StreamVLN：慢-快上下文建模的流式视觉语言导航**](https://github.com/InternRobotics/StreamVLN) - StreamVLN是StreamVLN论文的官方实现（被ICRA 2026接收），提出基于慢-快上下文建模的流式视觉语言导航方法。项目使用PyTorch实现，支持在Matterport3D/Habitat等模拟器上训练和评估，专为连续VLN（VLN-CE）场景设计。关键技术包括双速率特征提取和跨模态融合，旨在提升长指令跟随的鲁棒性。面向VLN研究人员和机器人导航开发者。
- [**ETPNav：连续环境下的进化拓扑规划视觉语言导航**](https://github.com/MarSaKi/ETPNav) - ETPNav 提出一种进化拓扑规划方法，用于连续环境下的视觉语言导航（VLN-CE）。该方法通过动态构建和更新拓扑图来处理长距离指令，结合视觉语言预训练（VLN-BERT）实现高效导航决策。项目提供了完整的训练和评估代码，面向连续环境中进行指令跟随的机器人研究。
- [**PARTNR-Planner：基于大型规划模型的人机协作与导航框架**](https://github.com/facebookresearch/partnr-planner) - 该项目提供PARTNR基准测试框架，利用大型规划模型（LPMs）在Habitat仿真器中解决人机协作与机器人指令跟随任务。它直接面向VLN社区中的指令跟随场景，集成了Habitat模拟环境，支持基于语言指令的导航规划。目标用户为从事Vision-Language Navigation、具身智能和机器人规划的研究者。
- [**NavGPT-2：指令微调释放VLM在连续环境中的导航规划能力**](https://github.com/GengzeZhou/NavGPT-2) - NavGPT-2 是基于大型视觉语言模型（VLM）的导航推理框架，通过指令微调释放 VLM 在连续环境中的导航规划能力。该工作发表于 ECCV 2024，直接面向 Vision-Language Navigation (VLN) 任务，尤其适用于无预定义图的连续导航（VLN-CE），且可结合 LLM/VLM 作为智能体执行指令跟随。项目开源了完整代码和训练流程，适合研究 VLM 驱动导航的学者与工程师。
- [**ScaleVLN：视觉语言导航数据规模化生成**](https://github.com/wz0919/ScaleVLN) - ScaleVLN 是 ICCV 2023 Oral 论文的开源实现，专注于视觉-语言导航（VLN）中的数据规模化生成。它提出了一种自动化数据生成管线，利用大规模预训练模型合成指令-轨迹对，显著提升训练数据多样性，从而增强 VLN 模型在离散和连续环境中的泛化能力。项目基于 Matterport3D 和 Habitat 仿真器，并提供完整的代码和预训练模型，适合从事 VLN 数据增强与迁移学习的研究人员。
- [**VLN-VER：基于体积环境表征的视觉语言导航**](https://github.com/DefaultRui/VLN-VER) - VLN-VER 是 CVPR 2024 提出的体积环境表征方法，用于视觉语言导航（VLN）。通过将3D场景建模为连续体积表示而非离散图，提升智能体在未知环境中遵循自然语言指令导航的泛化能力。项目提供了基于Habitat的训练代码和预训练模型，面向VLN-CE和零样本导航研究。
- [**HNR-VLN：基于神经辐射表示的前瞻探索连续VLN**](https://github.com/MrZihan/HNR-VLN) - 该项目是 CVPR 2024 Highlight 论文的官方实现，专注于连续视觉语言导航（VLN-CE）。它提出了基于神经辐射表示（Neural Radiance Representation）的前瞻探索方法，使智能体能够在连续 3D 环境中未预定义导航图的情况下进行指令跟随。关键技术包括使用类似 NeRF 的隐式场景表示预测未来观察状态，并集成强化学习进行策略优化。适用于研究 VLN-CE、基于模型的导航和神经隐式表示的研究人员。
- [**NavMorph：连续VLN中的自我进化世界模型**](https://github.com/Feliciaxyao/NavMorph) - NavMorph 是一个用于连续环境中视觉-语言导航（VLN-CE）的自我进化世界模型，由 Feliciaxyao 等在 ICCV'25 提出。它通过预测未来状态和轨迹来辅助导航决策，特别针对无预定义图的3D环境。该实现开源在 Python 下，适合研究 LLM/VLM 结合世界模型的导航代理。
- [**GSA-VLN：通用场景自适应视觉语言导航框架**](https://github.com/honghd16/GSA-VLN) - GSA-VLN 提出了面向视觉语言导航的通用场景自适应框架（ICLR'2025），旨在解决 VLN 模型在未知环境中的泛化难题。通过场景层级对齐与在线适应策略，该方法在不依赖额外标注数据的情况下显著提升跨场景导航成功率。项目提供完整代码与预训练模型，适合从事跨场景 VLN 泛化研究的学者与工程师。
- [**FLAME：基于多模态大语言模型的城市视觉语言导航**](https://github.com/xyz9911/FLAME) - FLAME是一个基于多模态大语言模型的导航方法，专门用于城市环境中的视觉语言导航。它利用LLM的推理能力，结合街景图像和自然语言指令进行路径规划，在连续城市环境中实现指令跟随。其主要创新在于将多模态LLM作为核心决策模块，适配到VLN任务中，为户外VLN研究提供了新范式。
- [**3D-Gaussian-Map-VLN：基于3D高斯地图的开放集语义分组VLN**](https://github.com/Gaozzzz/3D-Gaussian-Map-VLN) - 该项目提出一种基于3D高斯地图的开放集语义分组方法，用于视觉语言导航（VLN）。通过构建3D高斯场景表示并实现开放集语义分组，Agent能够理解指令中未预定义的类别。技术实现基于3D高斯溅射（3D Gaussian Splatting）与视觉语言模型，旨在提升导航智能体对复杂自然语言指令的泛化能力。目标用户为VLN和具身导航研究者。
- [**VLN-CE：连续环境视觉语言导航官方实现**](https://github.com/jacobkrantz/VLN-CE) - VLN-CE 是 Vision-and-Language Navigation in Continuous Environments 的开源实现，基于 Habitat 模拟器，支持在连续3D环境中进行视觉-语言导航任务。项目提供了基准模型、训练代码和评估工具，专注于 VLN-CE 赛道。适用于研究和开发连续环境下指令跟随导航的学者与工程师。
- [**VLN-BEVBert：面向语言引导导航的多模态地图预训练模型**](https://github.com/MarSaKi/VLN-BEVBert) - BEVBert是面向语言引导导航（VLN）的多模态地图预训练模型，其官方实现仓库。该项目提出联合学习鸟瞰视角地图和视觉-语言特征的Transformer架构，在R2R、RxR等离散导航任务上取得领先性能。代码基于PyTorch，提供训练、评估和预训练权重。主要面向VLN、具身AI和视觉语言导航研究人员。
- [**NaviLLM：基于大语言模型的具身导航通用模型框架**](https://github.com/zd11024/NaviLLM) - NaviLLM 是一个基于大语言模型的具身导航通用模型框架（CVPR 2024），通过多任务学习统一处理视觉语言导航（VLN）、3D问答等任务。其核心创新在于将导航指令跟随、场景理解等能力整合到单一LLM中，支持零样本和少样本导航泛化。适用于需要高效多任务具身导航的研究者。
- [**MapGPT：地图引导提示与自适应路径规划的VLN方法**](https://github.com/chen-judge/MapGPT) - MapGPT 是面向视觉语言导航（VLN）的官方实现，核心创新在于利用地图引导的提示（Map-Guided Prompting）与自适应路径规划（Adaptive Path Planning）来增强智能体在复杂环境中的指令跟随能力。该项目提供了完整的训练与推理代码，适合研究 LLM/VLM 导航智能体及地图辅助规划的学者与开发者使用。
- [**VLN-GOAT：基于因果学习的视觉语言导航方法**](https://github.com/CrystalSixone/VLN-GOAT) - VLN-GOAT（CrystalSixone/VLN-GOAT）是CVPR 2024收录的视觉语言导航（VLN）因果学习方法库。它通过因果推理增强跨模态导航指令跟随能力，在R2R等基准上取得显著提升。主要使用PyTorch实现，面向VLN研究者，提供预训练模型与训练代码。
- [**Dynam3D：动态分层3D令牌增强VLM的VLN能力**](https://github.com/MrZihan/Dynam3D) - Dynam3D 是一种动态分层 3D 令牌方法，旨在增强视觉语言模型（VLM）在视觉-语言导航（VLN）任务中的表现。它通过将3D场景表示为分层动态令牌，使VLM能够更有效地理解空间布局和指令跟随。该工作被NeurIPS 2025接收为Oral，为连续VLN和VLM导航代理提供了新思路。适用于研究VLN、3D语义导航和VLM推理的研究人员。
- [**YouTube-VLN：利用海量YouTube视频的视觉语言导航预训练**](https://github.com/JeremyLinky/YouTube-VLN) - 该项目为ICCV'23提出的VLN预训练框架，利用海量YouTube视频（而非人工标注的导航轨迹）学习视觉与语言对齐，从而提升导航指令跟随能力。通过大规模视频中隐含的时序与上下文信息，模型可学习到更鲁棒的跨模态表示，并在R2R等基准上取得显著改进。适用于希望减少人工标注成本、探索自监督/弱监督VLN方法的研究者。
- [**AO-Planner：面向连续VLN的可通行性导向基础模型规划器**](https://github.com/chen-judge/AO-Planner) - 该项目是AAAI 2025论文“Affordances-Oriented Planning using Foundation Models for Continuous Vision-Language Navigation”的官方实现，专注于连续视觉语言导航（VLN-CE）任务。它利用基础模型（如视觉语言模型）进行可通行性导向的规划，使智能体能够在无预定义图的连续3D环境中根据自然语言指令导航。主要技术包括多模态感知、可通行性推理和分层规划。目标用户为VLN、具身AI和机器人导航领域的研究者。
- [**VLN-SRDF：自优化数据飞轮引导的语言导航学习**](https://github.com/wz0919/VLN-SRDF) - 该项目是VLN论文“Bootstrapping Language-Guided Navigation Learning with Self-Refining Data Flywheel”的官方实现，提出通过自优化数据飞轮机制持续提升语言引导导航模型的性能。核心方法利用迭代训练与数据自动精炼，无需额外人工标注即可增强指令跟随与跨模态理解能力。适用于研究VLN数据高效训练和持续学习的学者。
- [**DifNav：基于扩散策略与DAgger的VLN方法**](https://github.com/Tokishx/DifNav) - DifNav 是一个面向视觉语言导航（VLN）的扩散策略方法，采用 DAgger 框架提升导航决策性能。项目提供了完整的代码实现，支持在 VLN 环境下训练与评估，核心贡献是将扩散模型与模仿学习结合以实现鲁棒的指令跟随导航。适用于研究 VLN 中基于生成模型的策略优化和连续决策的科研人员。
- [**C-Instructor：基于思维链提示的可控导航指令生成**](https://github.com/refkxh/C-Instructor) - C-Instructor 是 ECCV 2024 提出的可控导航指令生成方法，利用思维链提示（Chain-of-Thought Prompting）逐步生成高质量、可控制的路径描述。该项目为视觉语言导航（VLN）任务（如 R2R、RxR）提供指令生成工具，支持环境布局控制与指令多样性。核心实现基于预训练语言模型与步进式推理，适用于构建、扩充 VLN 数据集以及辅助智能体训练的研究者。
- [**GoViG：融合视觉特征与目标信息的VLN指令生成**](https://github.com/F1y1113/GoViG) - GoViG是一个面向视觉语言导航（VLN）的指令生成框架，通过融合视觉特征与目标信息，利用Transformer模型自动生成与导航路径匹配的自然语言指令。该项目提供了完整的训练与推理实现，可用于扩充VLN数据集或辅助智能体训练，直接服务于VLN生态。适合需要合成高质量导航指令的VLN研究者与工程师。
- [**LaViRA：语言-视觉-机器人动作转换的零样本连续VLN**](https://github.com/NJU-R-L-Group-Embodied-Lab/lavira-code) - LaViRA 是一个面向连续环境零样本视觉语言导航（VLN-CE）的开源框架，通过语言-视觉-机器人动作转换（Language-Vision-Robot Actions Translation）实现指令跟随。其核心创新在于无需预定义图结构，直接利用视觉语言模型将自然语言指令映射为机器人动作，支持 Habitat 等仿真环境。该代码库提供完整训练和评估流程，适用于追求 Sim-to-Real 泛化的 VLN 研究人员。
- [**Memoir：梦境回忆引导的体验检索用于记忆持久VLN**](https://github.com/xyz9911/Memoir) - Memoir 是 TPAMI-26 论文 'Dream to Recall: Imagination-Guided Experience Retrieval for Memory-Persistent Vision-and-Language Navigation' 的官方实现。它提出了一种基于世界模型预测未来状态、从记忆中检索相关经验来指导导航决策的方法，核心包括梦境重放和想象引导，显著提升 VLN 长程导航性能。该项目直接服务于 VLN 研究者，特别是关注记忆增强与世界模型方法的群体。
- [**AlldayWalker：面向全天候多场景的终身视觉语言导航**](https://github.com/Ganvin-Li/AlldayWalker) - AlldayWalker 是一个面向全天候多场景的终身视觉语言导航（VLN）框架，通过 Tucker 分解适应（Tucker Adaptation）实现跨场景持续学习。该项目基于 Habitat 仿真环境，支持在动态光照和多样化室内环境中执行自然语言指令导航，无需预定义图结构。主要供研究 VLN 持续学习与域适应的研究人员使用。
- [**Taga-VLM：拓扑感知全局动作推理的离散与连续VLN方法**](https://github.com/APEX-BJUT/Taga-VLM) - TagaVLM是ICRA 2026论文的官方实现，提出拓扑感知的全局动作推理方法，用于离散和连续环境下的视觉语言导航（VLN）。该方法通过建模环境拓扑结构来提升长距离指令跟随与跨场景泛化能力，目标用户为研究VLN的科研人员和工程师。

## 工具与实用程序
*用于VLN研究的评估脚本、可视化工具与辅助库。*
- **[工具名称]** – 用途。 [链接]

---


- [**awesome-embodied-vla-va-vln：具身VLA/VA/VLN精选列表**](https://github.com/jonyzhang2023/awesome-embodied-vla-va-vln) - 该仓库是一个精心策划的列表，汇集了具身智能领域的最新研究，核心聚焦于视觉-语言-动作（VLA）模型、视觉语言导航（VLN）及相关多模态学习方法。它涵盖了从经典VLN任务变体到连续VLN、LLM/VLM驱动智能体等前沿方向，并收录了重要论文、数据集与仿真器。目标用户为从事具身智能和VLN研究的研究人员与开发者，可作为系统性的文献索引和入门指南。
- [**NaVid-VLN-CE：NaVid与Uni-NaVid连续VLN评估代码**](https://github.com/jzhzhang/NaVid-VLN-CE) - 该仓库提供了NaVid和Uni-NaVid在连续视觉语言导航（VLN-CE）任务上的评估代码，支持在Habitat模拟器中进行指令跟随导航实验。项目基于视觉-语言模型（VLM）作为导航规划器，无需预定义导航图即可在3D环境中实现零样本跨场景导航。代码包含训练好的模型权重和评估脚本，目标用户为VLN研究人员和机器人导航开发者。
- [**InternNav：通用导航基础模型开放平台**](https://github.com/InternRobotics/InternNav) - InternNav 是由 InternRobotics 开发的开放平台，旨在构建通用的导航基础模型。它紧密关联 Vision-Language Navigation (VLN)，通过集成视觉-语言-动作模型 (VLA) 和多模态大语言模型 (VLM)，支持基于自然语言指令的连续导航决策。项目提供预训练模型和交互式示范，适用于室内机器人导航场景，目标用户为从事具身导航、跨模态路线跟随及空间智能研究的开发者和研究人员。
- [**awesome-embodied-vision：具身视觉与VLN阅读清单**](https://github.com/ChanganVR/awesome-embodied-vision) - 该项目是一个关于具身视觉（Embodied Vision）研究主题的精选阅读清单，涵盖视觉导航、视觉探索等方向，并专门包含视觉语言导航（VLN）子领域的论文和资源链接。它整理了从经典算法到最新预训练模型的系统性索引，为 VLN 研究者提供了文献入门和前沿追踪的便捷入口。适合从事具身导航、指令跟随、多模态感知等方向的研究人员和学生参考。
- [**VLN-Survey-with-Foundation-Models：VLN与基础模型综述**](https://github.com/zhangyuejoslin/VLN-Survey-with-Foundation-Models) - 该仓库提供了一份关于视觉语言导航（VLN）与基础模型（Foundation Models）的全面综述，收录于TMLR 2024。它系统整理了VLN领域中使用大规模语言模型、视觉-语言模型作为规划器或导航核心的最新研究，涵盖经典任务和连续VLN等变体，并持续更新。适合希望了解VLN前沿进展的研究人员与开发者。
- [**Awesome-VLA-UAVs：面向无人机的VLA/VLN精选资源列表**](https://github.com/TheBrainLab/Awesome-VLA-UAVs) - 该项目是一个精选资源列表，收录了面向无人机（UAV）的视觉-语言-动作/导航（VLA/VLN）模型、论文、数据集及相关工具。它专门聚焦于VLN技术在无人机领域的应用，涵盖指令跟随、跨模态导航等方向，为研究人员和开发者提供了系统性的参考入口。主要实现了VLN与无人机任务（如自主巡检、目标搜索）的直接集成，包含经典模型、最新基准及开源实现。
- [**Awesome-Vision-Language-Robotics-with-Code-and-Datasets：开源视觉语言导航与操作大全**](https://github.com/DaojiePENG/Awesome-Vision-Language-Robotics-with-Code-and-Datasets) - 该仓库是一个精选列表，系统整理了开源视觉语言导航（VLN）与操作（VLM）相关的工作，涵盖最新模型、基准测试和工具。其核心特点在于专门聚焦VLN领域，为具身智能体理解视觉、语言并执行任务提供资源。适用于从事具身AI的研究人员和开发者，促进创新。
- [**Awesome-Vision-and-Language-Navigation：持续更新的VLN资源精选列表**](https://github.com/iminolee/Awesome-Vision-and-Language-Navigation) - 该项目是一个持续更新的视觉与语言导航（VLN）资源精选列表，系统收录了VLN领域的重要论文、基准、模拟器、数据集和开源工具。作为专门面向VLN的Awesome List，它直接服务于VLN研究者和工程师，便于快速获取领域核心资源与最新进展。
- [**LLM4VLM：利用大语言模型生成中文指令实现零样本跨语言VLN**](https://github.com/TyrionXu-016/LLM4VLM) - LLM4VLM 利用大语言模型生成中文指令，用于零样本跨语言视觉语言导航。通过生成跨语言指令增强数据，弥补现有 VLN 数据集在中文领域的缺失，提升模型在中文环境下的泛化能力。该项目面向 VLN 研究者，特别是对多语言导航或零样本跨语言适应感兴趣的群体。
- [**Awesome-Aerial-Vision-Language-Navigation：空中视觉语言导航资源精选**](https://github.com/Sautenich/Awesome-Aerial-Vision-Language-Navigation) - 该项目是一个专注于空中视觉语言导航（Aerial Vision Language Navigation）的精选资源列表，作为视觉语言导航（VLN）的全新分支。它收录了相关的论文、工具和数据集，致力于推动无人机等空中平台在自然语言指令下进行环境感知与导航的研究，面向对空中自主导航和跨模态理解感兴趣的研究者。
- [**VLN-CE-Docker：隔离依赖环境的VLN-CE评估容器**](https://github.com/jianzhou0420/VLN-CE-Docker) - 该项目提供了一个Docker化的VLN-CE评估客户端，用于隔离遗留依赖（如habitat-sim 0.1.7和PyTorch 1.9），解决环境配置冲突问题。通过容器化封装，简化了连续视觉语言导航（VLN-CE）任务中评估流程的复现与部署。适用于需要稳定运行VLN-CE基准测试的研究人员。
- [**MiniVLA-Nav：轻量级视觉-语言-动作导航框架**](https://github.com/rantaluca/MiniVLA-Nav) - MiniVLA-Nav 是一个精简的视觉-语言-动作导航项目，使用 CLIP 进行跨模态指令理解与视觉定位，结合 PyBullet 物理模拟器构建 3D 环境进行仿真。该项目为 VLN 研究与教学提供了轻量级的实验框架，适合初学者或快速原型验证。
- [**xNav-data-preprocess：VLN数据集转LeRobot格式预处理工具**](https://github.com/MEmbodied/xNav-data-preprocess) - 该项目提供将VLN数据集（如R2R、RxR）预处理为LeRobot格式的工具，支持将视觉语言导航数据标准化为机器人学习框架兼容的结构。通过转换数据表示，便于将VLN领域的研究成果迁移到机器人导航训练中。适用于需要利用VLN数据训练机器人策略的研究人员或工程师。
- [**peTrain：基于仿真器的宠物机器人VLN训练框架**](https://github.com/lyteabovenyte/peTrain) - 该项目旨在利用AI方法训练智能宠物，基于Habitat和AI2-THOR模拟器构建，特别集成了VLN-CE（连续视觉语言导航）技术。它提供3D环境下的导航训练框架，支持计算机视觉和强化学习。适合研究人员和开发者探索宠物机器人的语言导航能力。
- [**WCGEN：世界一致的VLN数据生成工具**](https://github.com/SteveLee1999/WCGEN) - 该项目是“World-Consistent Data Generation for Vision-and-Language Navigation”的官方实现，旨在通过生成世界一致的轨迹数据来增强VLN模型的训练。它利用3D环境（如Matterport3D）合成多模态导航样本，提升模型在跨场景泛化与sim-to-real迁移中的表现。适用于VLN数据增强、预训练和鲁棒性研究。
- [**VLN-TimeLine：视觉语言导航研究进展时间线**](https://github.com/BlackMagic02/VLN-TimeLine) - 该项目提供了一个关于视觉语言导航（VLN）研究进展的时间线，系统梳理了从早期工作到最新突破的关键论文、模型和数据集。它通过可视化时间轴帮助研究者快速了解VLN领域的发展脉络，包括R2R、RxR等经典任务和BEVBert、NavGPT等前沿方法。适用于VLN领域的新入门者或需要文献综述的研究人员。
- [**freeaskworld_vln_zero：VLN-Zero零样本导航方法移植实现**](https://github.com/yiziwang02/freeaskworld_vln_zero) - 该项目提供了VLN-Zero方法的代码移植与可复现实现，专注于视觉语言导航中零样本（Zero-Shot）指令跟随任务。它复现了相关工作并支持在Freeaskworld框架内运行，适合研究人员评估和扩展VLN-Zero模型。
- [**vln-paper：VLN学术论文收集列表**](https://github.com/ZhenshengXieHit/vln-paper) - 该仓库是一个专门收集和整理Vision-Language Navigation (VLN) 领域学术论文的列表项目。它汇集了VLN相关研究文献，包括经典基准、模型和最新进展，为研究人员提供了便捷的文献索引。主要功能是作为VLN论文的集中资源库，适合需要快速查阅VLN论文的研究者。
- [**Uni-NaVid-ROS2：将Uni-NaVid模型集成到ROS2机器人系统**](https://github.com/t0dy/Uni-NaVid-ROS2) - Uni-NaVid-ROS2 是对 Uni-NaVid 模型的 ROS2 适配仓库，旨在将基于视觉语言模型（VLM）的导航代理集成到机器人操作系统（ROS2）中。它实现了 Uni-NaVid 在连续环境下的指令跟随与导航能力，支持室内导航任务。该项目面向寻求将 VLN 模型部署至实际机器人系统的研究者和开发者。
- [**NavManager：处理R2R导航数据的PHP代码库**](https://github.com/rvdata/NavManager) - 该项目是用于处理Room-to-Room（R2R）导航数据的PHP代码库，提供数据预处理和解析功能，直接服务于Vision-Language Navigation（VLN）任务。它支持R2R数据集的操作，适用于需要处理VLN标准数据的开发者和研究者。
- [**vlnce-python3.8-install：VLN-CE在Python 3.8环境下的安装指南**](https://github.com/sungjunek/vlnce-python3.8-install) - 该项目为VLN-CE（Continuous Vision-Language Navigation）提供在Python 3.8环境下的安装指南，旨在帮助研究者快速搭建连续VLN实验环境。作为VLN-CE生态的直接工具性资源，它解决了依赖冲突和环境配置痛点，目标用户为从事连续VLN研究的开发者和科研人员。
- [**NavDSL：面向VLN的领域特定语言框架**](https://github.com/leslie-arch/NavDSL) - NavDSL 是一个面向视觉语言导航（VLN）任务的开源项目，采用领域特定语言（DSL）来简化导航指令的建模与执行。项目旨在提供一种轻量化的框架，使研究人员能够更高效地定义和测试基于语言指令的导航策略。其核心创新在于将 VLN 任务中的指令理解与路径规划抽象为 DSL 语法，降低开发门槛。适用于需要快速原型设计与验证的 VLN 研究者。
- [**VLNCE_graph_dataset_construction：构建连续VLN图数据集工具**](https://github.com/yujie-jia/VLNCE_graph_dataset_construction) - 该项目旨在构建用于Continuous VLN（VLN-CE）任务的图数据集。它提供了从3D环境（如Habitat）中提取拓扑图、构建可导航图结构的工具，支撑基于图的导航方法在连续空间中的训练与评估。适用于从事VLN-CE、地图导航或图推理的研究者与开发者。
- [**py-xiaozhi：集成VLN导航功能的青龙Lite机器人扩展**](https://github.com/cyrusliu1984/py-xiaozhi) - 这是一个针对青龙Lite机器人定制的扩展仓库，在原始项目基础上新增了基于视觉-语言导航（VLN）模型的导航功能、运动控制调用和本地知识库。用户可通过MCP接口调用VLN模型实现指令跟随导航，适合研究机器人指令跟随的开发者。
- [**bibo_data：VLN合成数据生成工具**](https://github.com/Giqure/bibo_data) - 该项目专注于生成VLN（Vision-Language Navigation）合成数据，提供Python工具用于创建导航指令与环境对齐的仿真数据集。通过合成数据增强训练样本，支持室内导航场景的指令跟随任务，适用于VLN模型预训练或数据扩充。目标用户为需要低成本获取多样化训练数据的VLN研究者。
- [**BEVInstructor：基于鸟瞰图与大语言模型的导航指令自动生成**](https://github.com/FanScy/BEVInstructor) - BEVInstructor 是 ECCV 2024 提出的一种导航指令生成方法，利用鸟瞰图（BEV）感知和大语言模型（LLM）从未标记的 3D 场景中自动生成高质量导航指令。通过将 BEV 语义特征输入 LLM 并设计结构化提示，该方法能够产出与路径高度对齐的自然语言描述。该项目为 VLN 任务中的指令生成提供了自动化工具，适用于需要大量指令标注的 VLN 数据集构建与模型预训练场景。
- [**ILA4VLN：通过光照操纵实现VLN黑盒对抗攻击**](https://github.com/LiChenyang0820/ILA4VLN) - ILA4VLN是一个针对视觉语言导航（VLN）的黑盒对抗攻击框架，通过操纵室内光照条件来评估和提升VLN模型的鲁棒性。该工作发表于CVPR 2026，提供了在3D环境（如Matterport3D）中生成光照扰动的实现，可用于测试现有VLN代理（如基于Transformer的模型）对光照变化的脆弱性。适用于研究VLN安全性和鲁棒性的学者。
- [**VLN_environment：快速搭建离散与连续VLN环境的工具**](https://github.com/lyxshuishui/VLN_environment) - 该项目提供了一个快速搭建连续与离散视觉语言导航（VLN）环境的工具，支持 Matterport3D 和 Habitat 等主流仿真器的配置，简化了 R2R、VLN-CE 等任务的实验设置。目标用户为 VLN 研究者与开发者，尤其适合需要快速验证模型的环境搭建场景。
- [**oobvlm：即插即用的VLM导航框架**](https://github.com/YichengDuan/oobvlm) - 该开源项目提供一个即插即用的导航框架，基于视觉语言模型（VLM）实现指令跟随与自主导航。它直接集成VLM作为规划器或推理器，适用于连续环境下的零样本导航任务，支持室内和室外场景。目标用户为VLN和具身AI研究者，可快速部署VLM导航代理。
- [**rpc：连接Habitat模拟器与VLN模型的RPC通信框架**](https://github.com/HarryFang30/rpc) - 该项目提供基于RPC的通信框架，用于连接Habitat模拟器与Vision Language Navigation（VLN）模型，支持远程过程调用和分布式执行，可简化VLN智能体的训练与评估流程。主要面向VLN研究者，帮助快速搭建环境-模型交互管线。

## 贡献
欢迎贡献！请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解指南。
（你可以创建一个简单的 CONTRIBUTING.md 来说明如何添加论文/项目。）

## 许可证
[![CC0](https://licensebuttons.net/p/zero/1.0/80x15.png)](http://creativecommons.org/publicdomain/zero/1.0/)

---

<div align="center">

## 🤖 Auto-Generated

This awesome list is automatically maintained by [GPT-Awesome-List-Generator](https://github.com/shaoxiang/GPT-Awesome-List-Generator).

</div>