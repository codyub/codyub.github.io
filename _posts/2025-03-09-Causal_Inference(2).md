---
layout: single
title: "Causal Inference(2)"
categories: Study
tag: [lecture]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---

Introduction: 2. Randomized experiments 
===
In general, we will not know both potential outcomes in a real world. Rather, we can only know observed outcome(onely one of the counterfactual oucomes is know for each individual). To conduct causal inference, we have to assume some conditions.
This missing data creates a problem because it appears that we need the value of both counterfactual outcomes to compute effect measures. Thus, most of data are only good to compute association
measures.

Randomized experiments
---
# 1. Randomization
---
randomization ensures that **those missing values occurred by chance**. As a result, effect measures can be computed in randomized experiments despite the missing data.
- ideal randomized experiment: no loss to follow-up, full adherence to the assigned treatment over the duration of the study(연구기간동안 치료법 준수), a single version of treatment, and double blind assignment(플라시보/치료)
  1. assign indiviudual to the white or grey group by using coin(=randomly).
  2. assign white group to the treatment group(P(Y=1|A=1)) and grey group to the non-treatment group(P(Y=1|A=0)).
  3. Then, we can compute motality
 


# 2. Exchangeability(exogeneity): $A ㅛ Y^a$ for all a
---
**$P(Y^a = 1 \mid A=1) = P(Y^a = 1 \mid A=0) = P(Y^a = 1)$**  
more realistic randomized experiments: if the research assistants had misinterpreted our instructions and had treated different group(reversal of treatment status) -> **The association measure would not change**.
- Because individuals were randomly assigned to white and grey groups, the proportion of deaths among the exposed    
- 즉, 어차피 처음 랜덤으로 사람을 나눴을 때도 그 두 집단의 차이를 모르고 그냥 나눴기 때문에, 반대로 준다고 해서 계산 비율에는 차이가 없어야 정상적인 실험임.   
The risk of death in the white group would have been the same as the risk of death in the grey group had individuals in the white group received the treatment given to those in the grey group.
- 즉, 위와 같이 처음 랜덤으로 사람을 나눴으므로, 두 집단의 죽음에 대한 리스크가 같아야함.
- 집단과 죽음에 대한 리스크가 독립인 것  
<br/>

Because the counterfactual risk under treatment value a is the same in both groups A = 1 and A = 0, we say that the actual treatment A does not predict the counterfactual outcome $Y^a$  
- A는 어떻게 그룹이 나눠진 것인가를 의미함. 여기서 혼동하지 말아야할 부분은, 이 사람들에게 치료를 하고 말고가 아니라 여기서는 그냥 그룹 나눴음의 의미로 사용된 것임: A=1 : grey(treated), A=0 : white(untreated)  
- potential treatment value : a (a=0 or 1), 이 값은 실제로 우리가 치료를 했는가 안 했는가에 대한 변수임. A는 최초에 임의로 나눴던 그룹을 의미하고, a는 treatment에 대해 실질적으로 개입에 대한 것임  
- 사실상 sample mean -> population mean 추정 같은 느낌  
- 즉, 그래서 이에 따라, 그룹은 그냥 랜덤으로 나눠진 것이므로, 사실상 의미가 없기 때문에, 처치가 같아지면 두 집단이 그 treatment에 대한 반응은 같은 비율로 나타나야 랜덤하게 잘 분류한 것이라는 것  
- 그래서 만약 $P(Y^a = 1 \mid A=1) \neq P(Y^a = 1 \mid A=0)$ 이라면, Exchangeability condition이 만족하지 못하는 것  
- 하지만, 실질적으로 반쪽자리 데이터에서 이러한 정보를 아는 것은 어려움 -> 그래서 가정  
- Randomization is so highly valued because it is expected to produce exchangeability.     
<br/>
**In ideal randomized experiments, association is causation.**  
<br/>

make sure you understand the difference between $A ㅛ Y^a$ and $A ㅛ Y$
- $A ㅛ Y^a$: defined as independence between the counterfactual outcome and the observed treatment. does not imply independence between the observed outcome and the
observed treatment $A ㅛ Y$
 - 처치를 받은 그룹과 받지 않은 그룹이 본질적으로 동일하다면, 특정 처치 a에 대한 반사실적 결과는 처치와 독립적이다 라는 의미. 처치군과 비처치군이 동일한 조건이라면, 반사실적 세계에서 동일한 처치를 받았을 때 같은 결과를 가질 거라고 보는 것
 - e.g. 실험이 완벽하게 무작위화되었다고 가정. 즉, 환자들이 신약을 받았는지 여부가 그들의 건강 상태나 다른 특성과 무관하게 랜덤으로 결정. -> 이 경우, 처치군과 비처치군은 비슷한 특성을 가진 그룹이라고 볼 수 있어서 $A ㅛ Y^a$가 성립함을 알 수 있음. 즉, 신약을 받았든 안 받았든 상관없이 "만약 같은 처치를 했다면" 두 그룹의 생존 확률은 같아야함.
 - e.g. 실제 실험 결과를 보았더니, 실제로 신약을 받은 그룹의 생존율이 80%, 신약을 받지 않은 그룹의 생존율이 50%였다. -> 여기서 신약을 받은 그룹의 생존율이 더 높으니까, Y는 A와 독립적이지 않아서, $A ㅛ Y$가 성립하지 않는다는 것을 알 수 있음. 
 - "교환성이 있으면 반사실적 결과와 처치는 독립적이다." → 즉, 만약 모든 사람이 같은 처치를 받았다고 가정하면, 그 결과는 처치 여부와 무관해야 함.
 - 하지만 "관찰된 결과는 실제 처치의 영향을 받기 때문에 처치와 독립적이지 않다." → 즉, 처치가 실제로 효과가 있다면, 처치 여부에 따라 결과가 달라지므로 $A ㅛ Y$는 아님.
 - 즉, 교환성이 있어도 실제 관찰된 결과는 처치와 연관될 수 있으며, 위는 가정일 뿐이다.
 - 반사실적 독립 → 처치가 결과에 영향을 주지 않는다면 성립 → "인과가 없다"고 가정하는 것
<br/>

나의 처음 이해: 두 그룹을 랜덤하게 나눴으므로, 각 그룹이 처치를 받았을 때의 사망, 처치를 받지 않았을 때의 사망이 같아야 함이라고 이해함.
이후에는 노테이션이 바뀌었는데, A가 a의 역할을 한 느낌... -> 어렵다!
- 즉, 어떠한 treatment를 받는지는 랜덤이고, 이에 대해 어떠한 일이 일어날 것인가인 $Y^a$는 바뀌지 않는다는 것
- 근데 그럼 exchangeability condition을 만족하지 않는다고 계산했는데, 이걸 만족하지 않는다는 것이 어떠한 의미를 갖는 것인가? 인과 관계가 있다? 아님
- 두 집단의 동질성에 대한 부분으로, 두 집단의 동질하지 않으면, 그 두 집단이 뭔가 다른 특성이 있어서 사실 그게 원인일 수 있기 때문에(제 3의 원인) 가정하는 것임
<br/>

Can we then conclude that our study is not a randomized experiment if we determined that exchangeability does not hold
in our heart transplant study? NO!
1. First, a twenty-person study is too small to reach definite conclusions.
 - Random fluctuations arising from sampling variability could explain almost anything. (discuss ch10)
2. it is still possible that a study is a randomized experiment even if exchangeability does not hold in infinite samples. 

# 3. Conditional Randomization
---
제 3의 변수의 조건 기반으로 다른 확률을 갖고 랜덤하게 treatment를 배정하게 할 수도 있음.
- e.g. 환자가 수술 받거나 받지 않을 확률을 다르게 부여: L=1(중증) -> A=1(수술) 확률 70% , L=0(심각하지 않음) -> A=1(수술) 확률 30%
<br/>

- L: Prognostic factor(예후 인자 e.g. 병의 심각도) (1 if the individual was in critical condition, 0 otherwise)
- Marginally vs Conditionally randomized experiments  
- Conditional Exchangeability: $A ㅛ Y^a \mid L$
<br/>

In marginal experiment, causal risk ratio 
- $P(Y^{a=1} = 1) \div P(Y^{a=10 = 1) = P(Y = 1 \mid A=1) \div P(Y = 1 \mid A=0)$  
- $P(Y^{a=1} = 1) = P(Y^{a=1} = 1 \mid A=1) \quad by \quad A ㅛ Y^a, = P(Y = 1 \mid A=1) \quad by \quad A=1 -> Y^{a=1} = Y$  
<br/>

In conditional experiment, compute: $P(Y^{a=1} = 1 \mid L=1) \div P(Y^{a=0} = 1 \mid L=0)$ (L=1 그룹 내에서의 사망비율)
- $P(Y^{a=1} = 1 \mid L=1) = P(Y^{a=1} = 1 \mid L=1, A=1) = P(Y = 1 \mid L=1)$ (우리가 관찰한 값의 기호로만 표현)
- In general, they are different 
<br/>

However, our interest could not be to consider L=1 and L=0 separately. Rather, we want to show marginal causal risk ratio: $P(Y^{a=1} = 1) \div P(Y^{a=0} = 1)$ from conditionally random experiment.
1. Standardization:
   - $P(Y^{a} = 1) = \sum_{l} P(Y^{a} = 1 \mid L=l)P(L=l) = \sum_{l} P(Y^{a} = 1 \mid L=l, A=a)P(L=l) \quad by \quad conditional \quad exchangeability$
   - 설명: 
2. Inverse Probability weighting(IPW):
   - 해당되는 자료가 샘플과의 selection probability가 다른 것을 역으로 보정하면 일반적인 분석 방법으로 계산할 수 있을 것이다라는 가정
     1. Assign individual to the L 
     2. Assignment of A probabilities for each L
     3. observe Y
     4. Since $A ㅛ Y^a \mid L $, without consideration whether A is 1 or 0, we can divide results Y simply given L, which means that we can sum up the results within each L)
     5. Then, we can calculate $P(Y^{a=0} = 1) or $P(Y^{a=1} = 1)$ by just counting Y??? <- 이거 다시 확인 필요

- standardization and IPW are equivalent
<br/>

Pseudo-Population: $A ㅛ Y$
Idea: Associational risk ratio in pseudo population = causal risk ratio in both pseudo and original population.
- original data에서 몇 배를 증가 혹은 감소시킬 weight을 적용시켜 불리거나 줄이면 데이터는 변형이 있겠지만, 변형된 데이터는 가상 모집단으로 불리고, 이 경우에서는 $A ㅛ L$ 이다.
- IPW를 이용해 independence를 적용시키면, L과 A간의 연결고리가 끊긴다. 원래는 L에 따라 A가 더 혹은 덜 빈번하게 일어나는데, 위를 적용하면 L과 A가 독립으로 randomization 일어난 것처럼 보일 수 있음.
- L이 무관해지고, A와 Y에만 집중하면 되므로, 마치 marginal randomizaed experiment 수행한 것처럼 보여짐. 

chapter2
---



Textbook Reference
---
Hernán MA, Robins JM (2020). Causal Inference: What If (pdf: https://miguelhernan.org/whatifbook)   
Imbens, Guido , Rubin, Donald B (2015). Causal Inference for Statistics, Social, and Biomedical Sciences  
Pearl, Judea (2009). Causality
