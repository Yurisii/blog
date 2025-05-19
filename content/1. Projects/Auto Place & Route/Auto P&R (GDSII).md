## Post-Layout Simulation을 위한 파일
1. netlist 파일
2. sdf(StandardCell Delay Format) 파일

**P&R 전/후 netlist** 파일 변경점
1. 이전 : CTS 고려 없음
2. 이후 : CTS 고려 있음

**P&R 전/후 sdf** 파일 변경점
1. 이전 : 셀에 대한 딜레이만 존재
2. 이후 : Placement와 Routing이 진행되었으므로 넷 딜레이 정보가 포함

>[!note]
Time Violation 및 DRC에 문제가 없을 경우, 최종적으로 GDSII를 저장하며, 설계자에게 Post-Layout Simulation을 위한 파일을 생성하여 전달하고, 시뮬레이션에 이상이 없다면 해당 GDSII 파일을 최종으로 넘김

## GDSII
>[!definition]
>GDSII는 설계의 최종 산출물로, 실제 반도체 제조 공정에 전달되는 표준 물리 레이아웃 파일 포맷.
- ==P&R 및 모든 검증이 완료된 후 생성됨==
- 설계 레이아웃의 ==레이어 정보(Metal, contact, active layer 등)를 포함==
- 제조사는 이 GDSII 파일을 기반으로 포토 마스크를 제작한다.



### GDSII 생성 단계
1. **검증 완료**: 
   - ==모든 검증(DRC, LVS, Timing 분석)==을 통과해야 함
1. **사전 시뮬레이션 검증**: 
   - 생성된 GDSII 파일을 포토마스크 시뮬레이터 혹은 Signoff DRC 툴로 미리 검증
   - 제조 결함 사전 예측 가능
3. **Layer Mapping**: 
   - 설계 도구에서 ==사용한 레이어==가 제조 공정상의 ==실제 레이어(Poly, Metal, Diffusion 등)==에 정확히 ==매핑되었는지 확인==
   - 잘못된 매핑은 Mask 제작 오류로 이어질 수 있음

GDSII 파일은 최종적으로 제조 공정에 넘기기 전 확인이 필요. 작은 오류도 큰 문제로 이어질 수 있음.