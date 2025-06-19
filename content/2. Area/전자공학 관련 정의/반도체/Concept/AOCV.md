# Advanced On Chip Variation

>[!definition] AOCV
**AOCV**는 [[OCV]]에서 고려한 PVT 중 **Process**에 의한 타이밍 영향을 보다 정밀하게 모델링하기 위한 기법으로, OCV를 확장한 모델링 개념

기존 OCV는 칩에서 고정된 derating factor를 사용하는 반면, **AOCV**는 path의 특성, 특히 **path-depth**와 **cell 간 거리**에 따라 **derating factor**를 차등 적용함으로써 더 현실적인 타이밍 분석이 가능해진다.

1. **Path Depth 기반 모델링**
   Path depth는 logic cell이 순차적으로 연결된 깊이를 의미하며, depth가 깊어질수록 variation 효과가 평균화되어 variation의 영향이 줄어든다. AOCV는 이를 반영해 path depth가 증가할수록 derating factor를 완화시킨다.
2. **Cell Distance 기반 모델링**
   Distance는 path 상의 cell 간의 물리적 거리로, 가까울수록 공정 조건의 상관 관계가 높아져([[Variation#Systematic Variation|systematic variation]] 영향 증가), variation 효과가 줄어드는 경향이 있다. AOCV는 이 거리 정보도 고려하여 derating을 조정한다.
3. **Non-Systematic Variation 대응**
   AOCV는 특히 [[Variation#Non-Systematic Variation|non-systematic (random) variation]]에 대해 더 정밀한 모델링이 가능하다. 기존 OCV 모델은 worst-case 가정으로 인해 보수적인 분석이 이루어지지만, AOCV는 실제 layout 및 path 특성을 반영함으로써 타이밍 margin을 보다 정확하게 산출할 수 있다.

--- 
>[!reflection]
>AOCV는 path의 path depth, cell distance를 바탕으로 variation에 따른 타이밍 margin을 더 정밀하게 추정하는 기법