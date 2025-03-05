---
layout: single
title: "Causal Inference(1)"
categories: Study
tag: [lecture]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---


Introduction
=== 
to understand causal inference properly, we have to focus on the difference between traditional statistical methods and causal inference. 
the term causal effect can be used to investigate the causality among variables. 
- why is causal inference difficult? we usually investigate the causality based on observed data, which means that it is difficult to find causative factor of the problem.
- example topic: tobacco somking and cancer, Diabetes and Zero Drink, electronic cigarette and health etc.

Definition of causal effect 
===

Causation and Association are not the same. 
---
Messerli, Franz H. "Chocolate consumption, cognitive function, and Nobel laureates." N Engl J Med 367.16 (2012): 1562-4.
- the data shows obvious positive correlation between chocolate consumption and Nobel laureates per 10 million population: Did Chocolate Contribute to the Nobel Prize?
- Compounding variable(교란변수) woulb have been contributed to the result, such as Socioeconomic status. Additionally, if we could control the compounding variable, we would be able to know the relationship between the variables. 
- Correlation(Association) between X and Y: X influences Y or Y influences X
- X and Y would be able to have high correlation regardless of causality if they are influenced by a common mechanism.
- Standard statistical analysis (e.g. Regression) is to infer associations among variables and to "construct the prediction model from observed data."
- Causal analysis is about counterfactual prediction: What would have happened to the same subjects had they were exposed to a different (counterfactual) condition?
  - counterfactual prediction: 같은 사람/국가가 서로 다른 exposure로 분리해서 봐야 하는데, 시공간적으로 두 가지를 모두 관찰하는 것은 현실세계에서 불가능함. 즉, if we can investigate the result A, we miss the result B.
  - 즉, 같은 사람이 관심 있는 exposure(e.g. 약 섭취)를 다르게 두었을 때, 어떤 일이 벌어지는가?를 알고자 하는 것이 causal analysis. 일반적인 관찰 연구에서 정확한 통제 하에 데이터를 얻는 것은 불가능함. 


Basic steps for Causal Inference
---
1. Treatment (exposure) and Outcome from the scientific questions.
   - build scientific question, make problem simple, and determining a variable that is believed to be the actual cause(e.g. medicine, treatment)
   - we have question if we change the treatment, response would be change based on the cause?
   - 원인이 되는 변수
   - interest: if Treatment change, outcome also would be changed?
2. Population of interest
   - There would be a population that wants to confirm the above problem e.g. smoking-lung cancer
3. Potential outcomes for each level of the treatment
   - e.g. define expected response based on eat / do not eat, score 1~5
   - 즉, 특정한 원인 상황에 따라 예상되는 결과; 약을 먹으면 -> 안 죽을 것, 건강점수가 5점이면 -> 병이 없을 것, 실제로 일이 일어났을 때 생길 수 이슨 잠재적인 효과 서술(관찰과 별개로 정의를 그렇게 한다는 것)
4. Estimand (causal target parameter)
   - e.g. lung function score based on smoking status. : 즉, 추정하고 싶은 대상, 우리가 관심있는 결과를 데이터로부터 잘 추정해서 effect등을 확인하고픔 -> 이를 잘 학인하기 위해서는 우리는 모든 데이터를 얻는 것은 불가능하므로, 반드시 특정 가정에 의존해서 풀어야 함. 
5. State the Assumptions.
   - if the assuptions are wrong, next step also is unreliable. 
6. Estimation of causal effect
7. Evaluation assumptions (Sensitivity Analysis)
   - Sensitivity Analysis: when the assuptions are wrong, how much the effect would be changed?
   - change little -> low sensitivity / change a lot -> high sensitvity


Examples: Heart transplant intervention had a causal effect on survival?
---
Treatment/Exposure: heart transplant  
Outcome: survive or death  
Two Random variables (may have different values for different individuals)  
- A: binary treatment variable (1: treated, 0: untreated)
- Y: binary outcome variable (1: death, 0: survival)  

Notations:
- y, a: particular value of random variable Y, A, respectively.
- $Y^{a=k}$ : Y under treatment a = k(k= 0, 1). Outcome variable that would have been observed under the treatment value a = k.  
NOTE: Y a=k is still random variable. : 즉, a=k라고 가정했을 때 관찰될 것으로 기대되는 결과 Y를 의미함. 실제로 이러한 지 알 수 있고 없고와는 별개로 이러할 것이라고 가정하는 것 
For Zeus: $Y^{a=1}$ = 1 and $Y^{a=0}$ = 0 (실제로 이렇다락 보다는 a=1이라고 가정했을 때 어떤 일이 벌어졌을까에 대한 결과를 의미함)

Causal effect for individual
The treatment A has a causal effect on an individual’s outcome Y if $Y^{a=1}$ != $Y^{a=0}$ *for the individual*.
However, $Y^{a=1}$ and $Y^{a=0}$ are potential (counterfactual) outcomes!
- For each individual, one of the counterfactual outcomes is actually factual.
- Individual causal effects are defined as a contrast of the values of counterfactual outcomes, but only one of those outcomes is observed for each individual ⇒ Missing data problem (we only have half of the interest data)
(개인 수준에서는 저렇게 인과를 볼 수 있음, 하지만, 저 또한 개인에게서 두 경우 모두 관찰은 불가능함. 둘 중 하나는 어쩔 수 없이 missing이 생기는 데이터이며, 하나의 결과는 확실히 알 수 있음)  
 - Zeus: $Y^{a=1}$ = 1= Y (observed outcome)  

**Consistency: If A= a, $Y^{a}$ = $Y^{A}$ = Y**
 - if someone have a treatment=a, the corresponding outcome and assuption should be same.
 - 즉, 어떠한 a라는 처치를 받았고, 우리가 이를 했을 때의 예상되는 결과가 $Y^{a}$인데, 이것이 우리가 관측한 결과와 같다는 가정임. 당연한 가정임. 이것마저 없고 깨지면 할 수 있는 것이 없음.
 - - 물론 위배되는 케이스도 있음: 광고를 봤으니 본 행동을 해야 하는데 안 하는 경우

Identifying individual causal effects is generally not possible.  
- Ideal table: All Counterfactual outcome for population (여러개의 treatment를 했을 때에 대한 개개인의 결과들이 모두 있는 경우). then, we can calculate $P(Y^{a=1}=1)$ and $P(Y^{a=0}=1)$ (치료를 받고 죽은 확률, 치료를 받지 않고 죽은 확률)
- **(Average) causal effect** of A on Y is present if $P(Y^{a=1}=1)$ != $P(Y^{a=0}=1)$
  - that is, when people show different response based on the treatment, we would be able to consider that there is causal effect.
  - When Y is not binary, $E(Y^{a=1})$ != $E(Y^{a=0})$   
**Finally**, we want to calculate above statistics by using observed data (위 데이터는 현실적으로 관찰이 불가능함)
- Note: Absence of an average causal effect does not imply absence of individual effects.
  - 즉, 개개인의 인과와 전체 모집단의 평균적인 인과는 별개의 문제임. 평균적으로 없다고 해서 개개인의 인과가 반드시 없는 것이 아님. 위 예제에서 평균적으로 했을 때와 안 했을 때 모두 생존률이 50%이기 때문에, 인과가 없다고 했지만, 수술 했을 때와 안 했을 때의 결과가 다른 사람이 있다면 그 사람 개인에게는 인과가 있는 것임.   
Sharp causal null hypothesis is true if $Y^{a=1}\_i = Y^{a=0}\_i for all i$
 - 모든 사람이 저래야 individual effect가 없다고 할 수 있음. -> 거의 없을 것

Measures of causal effect
---
We can represent the causal null by 
**Causal risk difference**: $P(Y^{a=1}=1)-P(Y^{a=0}=1) = 0$ (no difference = no causality)

**Causal risk ratio**: $P(Y^{a=1}=1)$/$P(Y^{a=0}=1) = 1$ (same = no causality)

**Causal odds ratio**: $P(Y^{a=1}=1)/P(Y^{a=1}=0)$ / $P(Y^{a=0}=1)/P(Y^{a=0}=0) = 1$ (same = no causality)


Random variability
---
Sampling variability: In practice, investigators only collect information on a sample of the population of interest. Cannot compute exact $P(Y^{a=1}=1)$ Can Estimate it only.
- 모든 모집단 데이터를 얻는 것 또한 불가능하기 때문에, 샘플링 variability 또한 존재할 수밖에 없음. -> 추정 필요함   
Nondeterministic counterfactuals: When individual’s counterfactual outcomes are not fixed. 
- 수술받은 개인들이라도 모두 결과가 같은 것이 아님. 개개인 별로 수술 후 죽음/안죽음, 수술 안 하고 죽음/안 죽음 등의 매칭이 다르게 될 수 있음.

Causation vs Association
---
In real world: **half of counterfactuals are missing**. With the observed outcome Y(not potential outcome Y),  $P(Y=1|A=a)$ is the proportion of individuals that developed the outcome Y among those individuals in the population of interest that happened to receive treatment value a.
- 일반적인 상황: 개개인의 수술 여부(A)와 그에 따른 사망/생존 결과(Y) 정도만 알 수 있음.
- $P(Y=1|A=1) != P(Y=1|A=0)$ <=> A and Y are not independent. (<=> A and Y are associated)
  - independent: $P(Y \cap A) = P(A)P(Y) -> P(Y|A) = P(Y)$
- if $P(Y=1|A=1) = P(Y=1|A=0) = P(Y)$, independent

chapter1
---
Inferences about causation are concerned with what if questions in counterfactual worlds, such as "what would be the risk if everybody had been treated?" and "what would be the risk if everybody had been untreated?",  
(Marginal probability)

whereas inferences about association are concerned with questions in the actual world, such as "what is the risk in the treated?" and "what is the risk in the untreated?"  
(Conditional probability)



Textbook Reference
---
Hernán MA, Robins JM (2020). Causal Inference: What If (pdf: https://miguelhernan.org/whatifbook)
Imbens, Guido , Rubin, Donald B (2015). Causal Inference for Statistics, Social, and Biomedical Sciences
Pearl, Judea (2009). Causality
