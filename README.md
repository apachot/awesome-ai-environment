# Awesome AI & Environment

> A curated reference hub on the environmental impacts of AI and on AI applications for climate and environmental action.

This repository aims to document the most useful papers, tools, datasets, policy resources, and open questions at the intersection of artificial intelligence and the environment.

It is designed for researchers, policymakers, journalists, startups, students, and practitioners who need a structured starting point rather than hype. The emphasis is on traceable references, methodological clarity, and balanced coverage of both sides of the field:

- AI as an environmental burden: energy use, carbon emissions, hardware supply chains, water, and data center externalities.
- AI as an environmental instrument: climate modeling, grid optimization, monitoring, adaptation, biodiversity, and resource management.

The repository does not assume that one number or one benchmark settles the question. Environmental assessment depends on system boundaries, hardware assumptions, electricity mix, allocation choices, and deployment scale.

## Contents

- [Overview](#-overview)
- [Foundational Papers](#-foundational-papers)
- [Environmental Impact of LLMs](#-environmental-impact-of-llms)
- [Training vs Inference](#-training-vs-inference)
- [Measurement Methodologies](#-measurement-methodologies)
- [Carbon Accounting and Life-Cycle Assessment](#-carbon-accounting-and-life-cycle-assessment)
- [Energy, Hardware, and Data Centers](#-energy-hardware-and-data-centers)
- [AI for Climate and Environmental Applications](#-ai-for-climate-and-environmental-applications)
- [Policy, Regulation, and Governance](#-policy-regulation-and-governance)
- [Datasets](#-datasets)
- [Tools and Calculators](#-tools-and-calculators)
- [Benchmarks and Leaderboards](#-benchmarks-and-leaderboards)
- [Critiques, Limitations, and Controversies](#-critiques-limitations-and-controversies)
- [French Ecosystem and French-Language Resources](#-french-ecosystem-and-french-language-resources)
- [Research Gaps and Open Questions](#-research-gaps-and-open-questions)
- [Contributing](#contributing)
- [Related Projects](#related-projects)

## 🌍 Overview

This repository covers two partially overlapping literatures:

- Environmental footprint of AI systems: training, inference, embodied impacts, electricity, carbon, water, and infrastructure.
- AI for environmental benefit: climate mitigation, adaptation, earth observation, monitoring, forecasting, and decision support.

The field is fragmented. Many claims are difficult to compare because authors report different units, scopes, workloads, hardware setups, and regional electricity assumptions. A useful reference list therefore needs curation, not just accumulation.

## 📚 Foundational Papers

These are among the most influential references for framing the environmental discussion around modern machine learning.

- [Energy and Policy Considerations for Deep Learning in NLP](https://aclanthology.org/P19-1355/) (Strubell, Ganesh, McCallum, 2019): Early and widely cited warning that state-of-the-art NLP training has material financial and environmental costs, and that reporting standards matter.
- [Quantifying the Carbon Emissions of Machine Learning](https://arxiv.org/abs/1910.09700) (Lacoste, Luccioni, Schmidt, Dandres, 2019): Introduced an emissions calculator and helped formalize the idea that geography, hardware, and runtime strongly shape AI-related emissions.
- [Green AI](https://dl.acm.org/doi/abs/10.1145/3381831) (Schwartz, Dodge, Smith, Etzioni, 2020): Landmark argument for complementing accuracy-based evaluation with efficiency, cost, and reproducibility considerations.
- [On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?](https://dl.acm.org/doi/abs/10.1145/3442188.3445922) (Bender, Gebru, McMillan-Major, Shmitchell, 2021): Not an environmental paper alone, but central to broader debates on the social, epistemic, and environmental costs of scaling language models.
- [Carbon Emissions and Large Neural Network Training](https://www.kathimerini.gr/wp-content/uploads/2024/07/2104-10350_1.pdf) (Patterson et al., 2021): Important attempt to compare large-model training emissions while emphasizing datacenter efficiency and clean-energy-aware deployment choices.
- [A Systematic Review of Green AI](https://wires.onlinelibrary.wiley.com/doi/abs/10.1002/widm.1507) (Verdecchia, Sallou, Cruz, 2023): Useful map of the emerging Green AI literature and its main methodological strands.

## 🧠 Environmental Impact of LLMs

Large language models concentrate several environmental questions at once: massive training runs, repeated inference at scale, hardware concentration, and weak disclosure norms.

- [Evaluating the Carbon Impact of Large Language Models at the Inference Stage](https://ieeexplore.ieee.org/abstract/document/10253886/) (Everman et al., 2023): Focuses on inference rather than training and highlights that deployment-phase impacts can matter when usage is large.
- [From Words to Watts: Benchmarking the Energy Costs of Large Language Model Inference](https://ieeexplore.ieee.org/abstract/document/10363447/) (Samsi et al., 2023): Benchmark-driven look at the energy, latency, and performance trade-offs of LLM inference.
- [Measuring and Improving the Energy Efficiency of Large Language Models Inference](https://ieeexplore.ieee.org/abstract/document/10549890/) (Argerich, Patiño-Martínez, 2024): Focuses on operational efficiency and the deployment side of LLM systems.
- [Green AI: Exploring Carbon Footprints, Mitigation Strategies, and Trade-Offs in Large Language Model Training](https://link.springer.com/article/10.1007/s44163-024-00149-w) (Liu, Yin, 2024): Overview of mitigation strategies and training-related trade-offs for LLMs.
- [Towards Sustainable NLP: Insights from Benchmarking Inference Energy in Large Language Models](https://aclanthology.org/2025.naacl-long.632/) (Poddar et al., 2025): Benchmarking-oriented contribution showing the importance of workload and task design when comparing inference costs.
- [How Hungry Is AI? Benchmarking Energy, Water, and Carbon Footprint of LLM Inference](https://arxiv.org/abs/2505.09598) (Jegham et al., 2025): Relevant for moving beyond carbon-only analysis toward water and resource-aware comparisons.

## Training vs Inference

One recurring mistake in public debate is to discuss only training or only inference. Serious accounting must consider both, plus embodied infrastructure impacts where possible.

- Training is highly visible because frontier runs are concentrated, expensive, and newsworthy.
- Inference can dominate total impact when models are deployed at very large scale over long periods.
- Amortization assumptions matter: the same training run looks very different depending on model lifetime and usage volume.
- Retrieval, fine-tuning, quantization, distillation, and batching can materially change the trade-off.
- There is still no universally adopted standard for comparing total lifecycle impact across closed and open models.

Useful references:

- [Carbon Emissions and Large Neural Network Training](https://www.kathimerini.gr/wp-content/uploads/2024/07/2104-10350_1.pdf) (Patterson et al., 2021)
- [Evaluating the Carbon Impact of Large Language Models at the Inference Stage](https://ieeexplore.ieee.org/abstract/document/10253886/) (Everman et al., 2023)
- [From Words to Watts: Benchmarking the Energy Costs of Large Language Model Inference](https://ieeexplore.ieee.org/abstract/document/10363447/) (Samsi et al., 2023)
- [Energy Considerations of Large Language Model Inference and Efficiency Optimizations](https://aclanthology.org/2025.acl-long.1563/) (Fernandez et al., 2025)

## Measurement Methodologies

This is the section to read before trusting any single emissions number.

- [How to Estimate Carbon Footprint When Training Deep Learning Models? A Guide and Review](https://iopscience.iop.org/article/10.1088/2515-7620/acf81b/meta) (Bouza, Bugeau, et al., 2023): Practical review of estimation methods, tools, and recurring pitfalls.
- [Towards a Methodology and Framework for AI Sustainability Metrics](https://dl.acm.org/doi/abs/10.1145/3604930.3605715) (Eilam et al., 2023): Argues for better metric design and more consistent sustainability reporting for AI.
- [Toward Green AI: A Methodological Survey of the Scientific Literature](https://ieeexplore.ieee.org/abstract/document/10418137/) (Barbierato, Gatti, 2024): Useful survey of methodological trends in Green AI.
- [Measuring and Modeling CO2 Emissions in Machine Learning Processes](https://aile3.ijs.si/dunja/SiKDD2024/Papers/IS2024_-_SIKDD_2024_paper_23.pdf) (Hrib et al., 2024): Discusses how different trackers and modeling assumptions affect reported results.
- [Carbon Emission Quantification of Machine Learning: A Review](https://ieeexplore.ieee.org/abstract/document/11030805/) (Hasan et al., 2025): Broad review of quantification approaches and open standardization issues.

Common methodological issues:

- Operational electricity only versus full lifecycle accounting.
- Model-level accounting versus service-level accounting.
- Average grid intensity versus time- and location-specific carbon intensity.
- Chip power draw versus whole-system energy.
- Opaque datacenter assumptions for proprietary systems.
- Missing uncertainty ranges and poor reproducibility.

## Carbon Accounting and Life-Cycle Assessment

Lifecycle assessment (LCA) is still underused in AI discussions, even though chip manufacturing, servers, buildings, cooling, and end-of-life can matter substantially.

- [Quantifying the Carbon Emissions of Machine Learning](https://arxiv.org/abs/1910.09700) (Lacoste et al., 2019): Operational accounting focus, often used as an entry point.
- [Carbon Footprint of AI Data Centers: A Life Cycle Approach](https://www.energy-proceedings.org/wp-content/uploads/icae2024/1728494991.pdf) (d'Orgeval et al., 2024): Explicit LCA framing for AI data centers.
- [MLCA: A Tool for Machine Learning Life Cycle Assessment](https://ieeexplore.ieee.org/abstract/document/10805338/) (Morand, Ligozat, Névéol, 2024): Tool-oriented contribution aimed at fuller lifecycle reasoning.
- [Toward a Life Cycle Assessment for the Carbon Footprint of Data](https://dl.acm.org/doi/abs/10.1145/3727200.3727206) (Mersy, Krishnan, 2024): Extends the discussion from models to the footprint of data itself.
- [Generative AI Impact Assessment Through a Life Cycle Analysis of Multiple Data Center Typologies](https://www.sciencedirect.com/science/article/pii/S0306261925020185) (d'Orgeval et al., 2026): One of the more ambitious efforts to include both training and inference in an LCA framework.
- [Advances in Application of Machine Learning to Life Cycle Assessment: A Literature Review](https://link.springer.com/article/10.1007/s11367-022-02030-3) (Ghoroghi et al., 2022): Useful for readers connecting AI sustainability research with the broader LCA field.

## Energy, Hardware, and Data Centers

Environmental impact is not only a model issue. It is also an infrastructure issue.

- [Carbon Emissions and Large Neural Network Training](https://www.kathimerini.gr/wp-content/uploads/2024/07/2104-10350_1.pdf) (Patterson et al., 2021): Highlights the role of hardware efficiency and datacenter characteristics.
- [Carbon Footprint of AI Data Centers: A Life Cycle Approach](https://www.energy-proceedings.org/wp-content/uploads/icae2024/1728494991.pdf) (d'Orgeval et al., 2024): Relevant for moving discussion from isolated GPUs to full facilities.
- [Life Cycle Assessment of Edge Data Centers: Case Study in Presence of Renewable Energy and Refurbished Servers](https://dl.acm.org/doi/abs/10.1145/3724127) (Samaye, Ouffoué, Gamatié, 2025): Useful for thinking beyond hyperscale clouds.
- [Assessment of Carbon-Aware Flexibility Measures From Data Centres Using Machine Learning](https://ieeexplore.ieee.org/abstract/document/9916120/) (Misaghian et al., 2022): Connects data-center operations, flexibility, and carbon-aware management.

Topics that deserve more systematic coverage:

- Embodied emissions of accelerators and networking equipment.
- Water use and local water stress.
- Land use and permitting.
- Grid congestion and temporal matching of clean electricity.
- Rebound effects from cheaper inference and wider adoption.

## 🌱 AI for Climate and Environmental Applications

This repository is not only about AI's footprint. AI can also help reduce emissions, improve adaptation, and strengthen environmental monitoring, although impact claims should be assessed critically.

- [Tackling Climate Change with Machine Learning](https://dl.acm.org/doi/abs/10.1145/3485128) (Rolnick et al., 2022): Canonical survey of high-impact climate mitigation and adaptation opportunities for ML.
- [Machine Learning and Artificial Intelligence to Aid Climate Change Research and Preparedness](https://iopscience.iop.org/article/10.1088/1748-9326/ab4e55/meta) (Huntingford et al., 2019): Early overview of how AI can support climate science and preparedness.
- [The AI Gambit: Leveraging Artificial Intelligence to Combat Climate Change](https://link.springer.com/article/10.1007/s00146-021-01294-x) (Cowls, Tsamados, Taddeo, Floridi, 2023): Useful for linking technical opportunity with governance and policy recommendations.
- [Machine-Learning-Based Evidence and Attribution Mapping of 100,000 Climate Impact Studies](https://www.nature.com/articles/s41558-021-01168-6) (Callaghan et al., 2021): Good example of AI used to synthesize climate evidence at scale.
- [Predicting Global Patterns of Long-Term Climate Change From Short-Term Simulations Using Machine Learning](https://www.nature.com/articles/s41612-020-00148-5) (Mansfield et al., 2020): Example of AI assisting climate modeling and computational efficiency.
- [Climate Change AI](https://www.climatechange.ai/): Major community hub connecting machine learning with climate action, workshops, educational material, and domain-specific initiatives.

Application areas:

- Electricity systems and demand response.
- Buildings and energy efficiency.
- Agriculture and land use.
- Disaster risk and early warning.
- Air quality and pollution forecasting.
- Biodiversity monitoring and conservation.
- Water systems and hydrology.
- Climate science and Earth observation.

## Policy, Regulation, and Governance

Governance discussions often lag behind the technical literature. This section collects resources for environmental disclosure, reporting, standards, and institutional oversight.

- [OECD AI Principles](https://oecd.ai/en/ai-principles): High-level governance framework relevant to transparency and accountability.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework): Useful for institutional risk framing, though not specific to environmental accounting.
- [EU AI Act](https://artificialintelligenceact.eu/): Major regulatory development for AI governance in Europe; environmental reporting remains limited, but the Act matters for system classification and compliance design.
- [Software Carbon Intensity (SCI) Specification](https://sci.greensoftware.foundation/): Practical standardization effort from the Green Software Foundation, relevant to software and service-level carbon accounting.
- [Towards a Methodology and Framework for AI Sustainability Metrics](https://dl.acm.org/doi/abs/10.1145/3604930.3605715) (Eilam et al., 2023): Useful bridge between technical metrics and governance needs.
- [The Global Landscape of Environmental AI Regulation: From the Cost of Reasoning to a Right to Green AI](https://arxiv.org/abs/2603.00068) (Ebert et al., 2026): Early overview of a fast-moving regulatory discussion.

## Datasets

Datasets are split here between environmental-impact accounting inputs and climate or environmental application datasets.

- [Electricity Maps](https://www.electricitymaps.com/): Carbon intensity data useful for location-aware and time-aware emissions estimation.
- [Our World in Data CO2 and Greenhouse Gas Emissions](https://ourworldindata.org/co2-and-greenhouse-gas-emissions): Broad background dataset for contextualizing claims about AI and sectoral emissions.
- [Copernicus Climate Data Store](https://cds.climate.copernicus.eu/): Major access point for climate and reanalysis datasets.
- [CMIP6](https://www.wcrp-climate.org/wgcm-cmip/wgcm-cmip6): Core climate-model intercomparison data ecosystem.
- [ERA5 Reanalysis](https://cds.climate.copernicus.eu/datasets/reanalysis-era5-single-levels): Widely used climate and weather reanalysis product.
- [Sentinel Data](https://dataspace.copernicus.eu/): Earth observation data for land, ocean, atmosphere, and environmental monitoring applications.
- [Landsat Missions](https://www.usgs.gov/landsat-missions): Long-running satellite program relevant to land cover, water, forestry, and environmental change.

## Tools and Calculators

Most tools estimate a subset of the problem. They are useful, but none should be treated as a universal truth machine.

- [Machine Learning Emissions Calculator](https://mlco2.github.io/impact/) (from Lacoste et al.): Simple calculator for training-related emissions estimates.
- [CodeCarbon](https://github.com/mlco2/codecarbon): Widely used open-source package for estimating energy use and carbon emissions of code execution.
- [CarbonTracker](https://arxiv.org/abs/2007.03051) (Anthony, Kanding, Selvan, 2020): Tool for tracking and predicting the carbon footprint of training runs.
- [Eco2AI](https://link.springer.com/article/10.1134/S1064562422060230) (Budennyy et al., 2022): Emissions tracking framework for ML workflows.
- [Green Algorithms](https://www.green-algorithms.org/): Broad scientific computing calculator relevant beyond ML.
- [MLCA](https://ieeexplore.ieee.org/abstract/document/10805338/) (Morand, Ligozat, Névéol, 2024): LCA-oriented perspective for ML assessment.
- [Boavizta](https://boavizta.org/en/) and [Boavizta E-Footprint](https://e-footprint.boavizta.org/): Useful for embodied impact and digital equipment assessment, especially in broader digital sustainability work.

## Benchmarks and Leaderboards

This is one of the weakest areas in the field. Benchmarking exists, but environmental benchmarking is not yet standardized across models, providers, and workloads.

- [MLPerf Benchmarks](https://mlcommons.org/benchmarks/): Important reference for performance benchmarking in training and inference; not an environmental benchmark, but often relevant to efficiency discussions.
- [From Words to Watts: Benchmarking the Energy Costs of Large Language Model Inference](https://ieeexplore.ieee.org/abstract/document/10363447/) (Samsi et al., 2023): Example of workload-level energy benchmarking for LLM inference.
- [Towards Sustainable NLP: Insights from Benchmarking Inference Energy in Large Language Models](https://aclanthology.org/2025.naacl-long.632/) (Poddar et al., 2025): More recent inference benchmarking perspective.
- [Benchmarking Large Language Models: Opportunities and Challenges](https://link.springer.com/chapter/10.1007/978-3-031-68031-1_6) (Hodak et al., 2023): Useful background on why LLM benchmarking is difficult in the first place.

## Critiques, Limitations, and Controversies

The field includes active disagreements. A serious repository should preserve those disagreements rather than smoothing them away.

- [On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?](https://dl.acm.org/doi/abs/10.1145/3442188.3445922) (Bender et al., 2021): Core critique of scaling, including environmental and societal concerns.
- [Risks and Benefits of Large Language Models for the Environment](https://pubs.acs.org/doi/full/10.1021/acs.est.3c01106) (Rillig et al., 2023): Balanced discussion of direct and indirect environmental implications.
- [The Carbon Emissions of Writing and Illustrating Are Lower for AI Than for Humans](https://www.nature.com/articles/s41598-024-54271-x) (Luccioni et al., 2024): Controversial comparison paper that is useful precisely because it surfaces boundary-setting disputes, substitution assumptions, and rebound questions.
- Public estimates for proprietary systems often rely on reverse engineering, leaked assumptions, or incomplete technical disclosure.
- Carbon-only analysis can obscure water, materials, e-waste, biodiversity, and labor issues.
- Efficiency gains can reduce per-query impact while increasing total use.
- Narrow operational accounting can understate embodied infrastructure impacts.

## 🇫🇷 French Ecosystem and French-Language Resources

France has a meaningful ecosystem around digital sustainability, lifecycle assessment, and public-interest infrastructure metrics. This section should grow over time.

- [ADEME](https://www.ademe.fr/): French public agency for ecological transition; relevant for environmental methodology, lifecycle assessment, and digital footprint work.
- [Boavizta](https://boavizta.org/en/): Open community and methodology work on digital environmental assessment.
- [Hubblo](https://hubblo.org/en/): French consultancy and public-interest actor active on digital environmental impact and LCA-related work.
- [EcoInfo CNRS](https://ecoinfo.cnrs.fr/): CNRS network focused on reducing the environmental footprint of research and digital practices.
- [INRIA](https://www.inria.fr/en): Major French public research institute with AI expertise and potential relevance for responsible and sustainable AI research.
- [Arcep: Digital Sustainability Work](https://en.arcep.fr/thematiques/sustainable-digital-development.html): French telecom regulator resources on digital environmental issues.

## Research Gaps and Open Questions

This is where the repository should become especially useful over time.

- Better disclosure standards for proprietary models, including workload, hardware, and regional electricity assumptions.
- Standard methods for combining training, inference, and embodied infrastructure impacts.
- More work on water use, mineral supply chains, and non-carbon externalities.
- Service-level accounting for real-world AI products rather than model-only estimates.
- Better comparison between frontier models, smaller task-specific models, and non-AI baselines.
- Environmental assessment of retrieval-augmented generation, agents, multimodal systems, and continuous fine-tuning.
- More public datasets for datacenter and accelerator lifecycle impacts.
- Stronger evidence on rebound effects and induced demand.
- Better bridges between Green AI, LCA, energy systems, and public policy communities.

## Contributing

Contributions are welcome, especially if they improve traceability and methodological rigor.

Please prefer:

- Primary sources over summaries.
- Stable links such as publisher pages, proceedings, official project pages, or arXiv when appropriate.
- A one-sentence note explaining why a resource matters.
- Explicit notes when a number is estimated, contested, or incomplete.
- Issues or pull requests that add missing regions, languages, disciplines, or public datasets.

Please avoid:

- Marketing claims without technical backing.
- Unsourced rankings of "greenest" models.
- Broken links, link shorteners, or vague references.
- Duplicating resources across sections without a reason.

Suggested entry format:

```md
- [Title](URL) (Author, year): One-line explanation of the contribution, method, or limitation.
```

## Related Projects

- [awesome-green-ai](https://github.com/samuelrince/awesome-green-ai): One of the closest GitHub repositories to this one, focused on Green AI resources and practices.
- [sustainable-ai](https://github.com/navveenb/sustainable-ai): Repository centered on practical approaches to making AI systems more sustainable.
- [facebookresearch/SustainableAI](https://github.com/facebookresearch/SustainableAI): Research-oriented repository related to sustainable AI methods and tooling.
- [Climate Change AI](https://www.climatechange.ai/)
- [CodeCarbon](https://github.com/mlco2/codecarbon)
- [Boavizta](https://boavizta.org/en/)
- [awesome-green-software](https://github.com/Green-Software-Foundation/awesome-green-software): Broader software sustainability repository with adjacent relevance for AI infrastructure and measurement.

## License

[ADD LICENSE]
