# 내용 정리

### 헬스케어 데이터의 종류<br>

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


- - -

### 실습
<details>
<summary>파일 구조</summary>
📁 AI헬스케어데이터정제및가공<br>
    &emsp;📁 dataset<br>
        &emsp;&emsp;📁 brain_tumor<br>
            &emsp;&emsp;&emsp;📁 images<br>
                &emsp;&emsp;&emsp;&emsp;📁 test<br>
                &emsp;&emsp;&emsp;&emsp;📁 train<br>
            &emsp;&emsp;&emsp;📁 labels<br>
                &emsp;&emsp;&emsp;&emsp;📁 test<br>
                &emsp;&emsp;&emsp;&emsp;📁 train<br>
            &emsp;&emsp;&emsp;📁 total<br>
                &emsp;&emsp;&emsp;&emsp;📁 test<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 images<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 labels<br>
                &emsp;&emsp;&emsp;&emsp;📁 train<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 images<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 labels<br>
                &emsp;&emsp;&emsp;&emsp;📁 val<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 images<br>
                    &emsp;&emsp;&emsp;&emsp;&emsp;📁 labels<br>
                &emsp;&emsp;&emsp;&emsp;📄 dataset.yaml<br>
        &emsp;&emsp;📁 chest_xray<br>
            &emsp;&emsp;&emsp;📁 test<br>
                &emsp;&emsp;&emsp;&emsp;📁 NORMAL<br>
                &emsp;&emsp;&emsp;&emsp;📁 PNEUMONIA<br>
            &emsp;&emsp;&emsp;📁 train<br>
                &emsp;&emsp;&emsp;&emsp;📁 NORMAL<br>
                &emsp;&emsp;&emsp;&emsp;📁 PNEUMONIA<br>
            &emsp;&emsp;&emsp;📁 val<br>
                &emsp;&emsp;&emsp;&emsp;📁 NORMAL<br>
                &emsp;&emsp;&emsp;&emsp;📁 PNEUMONIA<br>
        &emsp;&emsp;📁 cnn<br>
            &emsp;&emsp;&emsp;📁 cat<br>
            &emsp;&emsp;&emsp;📁 dog<br>
        &emsp;&emsp;📄 diabetes.csv<br>
    &emsp;📁 models<br>
        &emsp;&emsp;📁 YOLO_brain-tumor<br>
            &emsp;&emsp;&emsp;📁 weights<br>
                &emsp;&emsp;&emsp;&emsp;📄 best.pt<br>
                &emsp;&emsp;&emsp;&emsp;📄 last.pt<br>
            &emsp;&emsp;&emsp;📄 confusion_matrix.png<br>
            &emsp;&emsp;&emsp;📄 results.png<br>
            &emsp;&emsp;&emsp;📄 val_batch0_labels.jpg<br>
            &emsp;&emsp;&emsp;📄 val_batch0_pred.jpg<br>
        &emsp;&emsp;📄 BC_best.pt<br>
        &emsp;&emsp;📄 BC_last.pt<br>
        &emsp;&emsp;📄 NN-0224.pth<br>
    &emsp;📄 cnn_cat-dog_classification.ipynb<br>
    &emsp;📄 cnn_mnist_classification.ipynb<br>
    &emsp;📄 cnn_pneumonia_classification.ipynb<br>
    &emsp;📄 mlp_breast-cancer_classification.ipynb<br>
    &emsp;📄 nn_diabetes_classification.ipynb<br>
    &emsp;📄 README.md<br>
    &emsp;📄 yolo_brain-tumor_detection.ipynb<br>
</details>
<br>

**1. nn_diabetes_classification.ipynb → Neural Networks를 이용한 당뇨병 예측**
> 데이터셋: https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database
> <details><summary>당뇨병</summary>
> - 고혈당을 유발하는 대사성 질환<br>
> - 인슐린 호르몬은 혈액 속의 당을 세포로 옮겨서 저장하거나 에너지로 사용하지만 당뇨병 환자의 경우, 몸이 충분한 인슐린을 만들지 못하거나 만든 인슐린을 효과적으로 사용하지 못하는 상황이 발생</details>

**2. mlp_breast-cancer_classification.ipynb → MLP를 이용한 유방암 예측**
> 데이터셋: sklearn.datasets.load_breast_cancer

**3. cnn_cat-dog_classification.ipynb → CNN을 이용한 고양이/강아지 예측**
> 데이터셋: 고양이, 강아지 사진 각각 2장

**4. cnn_mnist_classification.ipynb → CNN을 이용한 손글씨 숫자 예측**
> 데이터셋: keras.datasets.mnist.load_data

**5. cnn_pneumonia_classification.ipynb → CNN을 이용한 폐렴 예측**
> 데이터셋: https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia
> <details><summary>폐렴</summary>
> - 폐포라고 알려진 작은 공기주머니에 주로 영향을 미치는 폐의 염증 상태<br>
> - 일반적으로 바이러스나 박테리아에 감염되어 발생 (다른 미생물, 특정 약물 또는 자가면역질환과 같은 조건에 의해 발생하는 경우는 드물다고 알려져 있음)<br>
> - 증상: 습성적이거나 건조한 기침, 가슴 통증, 발열, 호흡 곤란 등의 조합을 포함하며, 상태의 심각도는 가변적임<br>
> - 관련 위험 인자: 낭포성 섬유증, 만성 폐쇄성 폐질환(COPD), 천식, 당뇨병, 심부전, 흡연 이력, 뇌졸중과 같은 기침 능력 저하, 면역 체계 약화 등<br>
> - 진단: 보통 증상과 신체 검사를 기반으로 하며, 흉부 엑스레이, 혈액 검사, 가래 배양 등이 진단 확인에 도움이 될 수 있음<br>
> - 폐렴은 지역사회 또는 병원에서 획득한 폐렴이나 의료 관련 폐렴과 같이 감염된 위치에 따라 분류될 수도 있음</details>

**6. yolo_brain-tumor_detection.ipynb → YOLO를 이용한 뇌종양 객체 인식**
> 데이터셋: https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets



- - -