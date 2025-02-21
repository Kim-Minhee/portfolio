# 내용 정리

### 헬스케어 데이터의 종류
<br>

**1. 초음파 영상(Ultrasound imaging)**
> 우리 귀에 들리지 않는 높은 주파수의 음파를 인체 표면에서 인체 내부로 보낸 후, 내부에서 **반사되는 음파**를 영상화
><details><summary>초음파 검사 예시</summary>
> 1. A 모드(Amplitude mode): 대상 물체의 경계면에서 반사되는 초음파 신호 측정<br>
> 2. B 모드(Brightness mode, 2D 모드): 반사되는 신호의 강도를 밝기로 표현<br>
> 3. M 모드(Time-motion recoding mode, TM mode): B 모드 영상을 시간적으로 기록한 것<br>
> 4. D 모드(Doppler mode, TM mode): 심장 컬러 도플러</details>

**2. 내시경 영상(Endoscopy)**
> 인체 내부 기관에 대하여 좁은 구멍을 통해 기계를 삽입하여 관찰하기 위한 장치

**3. 방사선 촬영(X-Ray)**
> X-선을 인체에 투과하여 내부 조직의 상태를 볼 수 있는 검사 방법
> * 방사선: 입자 방사선(알파선, 베타선, 중성자선), 전자파 방사선(X선, 감마선)
><details><summary>$X-ray Dose \approx kV, mA, sec$</summary>
> - kV(voltage): X-ray beam energy level → 이미지 밝기 조절 가능<br>
> - mA(current): 발생 과정과 연관이 있는 전자의 수 → 이미지의 대조도(contrast) 조절 가능<br>
> - sec(seconds): 노출 시간</details>

**4. CT 촬영**
> X-선을 투과시켜 그 흡수 차이를 컴퓨터로 재구성하여 인체의 단면영상(Cross-sectional Image)을 얻거나 3차원적인 입체영상을 얻는 영상진단법
><details><summary>X-ray와의 차이</summary>
> - X-ray는 단면을 한번 찍는 반면, CT는 X-선으로 여러 사진을 연속적으로 찍어 입체적으로 볼 수 있음<br>
> - 뼈의 단면을 볼 수 있으며, X-ray 보다 더욱 정확하고 세밀하게 촬영 가능<br>
> - 검사 시간이 짧아 급한 환자의 경우 많이 사용되지만, X-ray보다는 방사선양이 많기 때문에 임산부는 조심해야 함</details>
><details><summary>종류</summary>
> - Brain CT(두부 검사)<br>
> - Chest CT(흉부 검사)<br>
> - Abdomen CT(복부 검사)<br>
> - CT Angio(혈관조영 검사)<br>
> - Heart CT(심장 검사)</details>

**5. 자기공명영상(MRI)**
> 강한 자기장 내에 위치시킨 인체에 라디오파를 전사해서 **반향되는 자기장을 측정**하여 영상을 얻는 진단 검사

**6. 양전자방출단층 촬영술(PET)**
> 몸 속의 생화학 변화를 영상화 할 수 있는 첨단 영상진단 기법


##
### 실습
<br>

1. diabetes_classification.ipynb → 당뇨병 예측
> * 데이터셋: https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database
><details><summary>당뇨병</summary>
> - 고혈당을 유발하는 대사성 질환<br>
> - 인슐린 호르몬은 혈액 속의 당을 세포로 옮겨서 저장하거나 에너지로 사용하지만 당뇨병 환자의 경우, 몸이 충분한 인슐린을 만들지 못하거나 만든 인슐린을 효과적으로 사용하지 못하는 상황이 발생</details>
2. 