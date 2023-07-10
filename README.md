# 💻 GAN_Nebula <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/> <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=TensorFlow&logoColor=white"/> <img src="https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=Keras&logoColor=white"/> 
## 👉 GAN으로 성운 이미지 만들기
## ✅ Toy 프로젝트 계기
* 이미지 생성 AI의 근간인 DCGAN을 실제로 경험해 보고 싶었음.
* 책 속 예제만 따라하는 것보다, 새로운 데이터를 프로젝트에 적용해 보는 것이 경험 쌓는 면에서 더 도움 될 것 같아서 도전하였음. 

## 📌 데이터 선정 계기
* 책 속 예제는 흑백 MNIST 적용 사례만 나와 있어서, RGB 색이 골고루 섞여 있는 데이터를 다뤄보고 싶었음.
* 고민 끝에 성운(별 생성 초기 모습)이 적절하다는 생각이 들어서 사용 데이터로 결정하게 되었음.
* 데이터 출처 : https://www.kaggle.com/datasets/akhileshravi/nebula-images

## 🔧 GAN 동작 원리
* GAN(Generative Adversarial Networks)은 생성적 적대 신경망을 의미함. GAN의 핵심 개념은 Generator와 Discriminator임. 이 둘이서 적대적으로 경합을 벌임.
* GAN 개념의 창시자인 'Ian Goodfellow(이안 굿펠로우)'는 GAN을 위조 지폐범과 경찰 관계로 비유했음. 여기서 위조 지폐범은 Generator를 의미하고, 경찰은 Discriminator를 의미함.
* Generator은 Discriminator를 속이는 것을 목표로 하고, Discriminator은 Generator가 생산한 데이터의 진위를 가려내는 역할을 함.
* GAN 알고리즘을 통해 우리가 얻고자 하는 것은 '효과적인 생성 AI(=유능한 위조 지폐범)'임. 따라서 Discriminator의 성장은 필요하지 않고, Generator의 발전만 필요로 함. 이러한 이유 때문에 Discriminator만 trainabe=False로 설정함. (가중치는 Generator만 학습함.)

## 🔸 학습 데이터 예시
<img src="https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/56d3434b-f47c-41d2-ba18-1146daa12b64" width="64" height="64"/>
<img src="https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/f015191a-fb3f-42b9-9b6b-aeda9525f449" width="64" height="64"/>
<img src="https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/61c89029-995b-4185-80ad-fc7dcb63fb03" width="64" height="64"/>
<img src="https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/1f269050-c399-439c-a37d-989f909dfa70" width="64" height="64"/>
<img src="https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/013a1d2f-3748-4223-bcaf-5a459fd883f0" width="64" height="64"/>

## 🔹 최종 결과
![image](https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/b003663a-73ce-4e4b-8018-9cd01b572000)

## 🙈 프로젝트 난관 극복 방식 (+ 실패 이미지 포함)
* 기존 흑백 MNIST 코드를 변형해서 성운 이미지를 생성하면 이상한 이미지를 생성했음. (동묘 구제룩 패턴...?)
![image](https://github.com/MOONisYOUNG/GAN_Nebula/assets/87643414/b7518747-96ca-4a4d-a12c-8b7f0190919e)
* 위와 같은 현상을 해결하기 위해서 MNIST보다 복잡한 이미지(ex. 얼굴 등)를 적용한 코드 예제를 찾게 되었음.
* 얼굴 등의 복잡한 이미지를 적용한 코드는, 학습 데이터와 진짜 데이터를 합친 후에 노이즈를 넣어서 train시켰음. (100% 랜덤 노이즈보다는 해당 방식이 더 합리적으로 학습 가능하기 때문으로 보임. 이미지 데이터에는 단서를 주고, 레이블 데이터의 진위 관계는 흐림으로써 학습 효과를 높이는 듯...)

## 🧷 참고 자료
* MNIST GAN 코드 자료 참고 : [모두의 딥러닝 2판 (조태호 지음, 길벗 출판사)](https://github.com/gilbutITbook/080228/blob/master/deeplearning/run_project/20_GAN.ipynb) 
* 얼굴 생성 GAN 코드 자료 참고 : [Deep Learning with Python, Second Edition (François Chollet 지음)](https://github.com/fchollet/deep-learning-with-python-notebooks/blob/master/chapter08_intro-to-dl-for-computer-vision.ipynb)
* [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks 논문](https://arxiv.org/abs/1511.06434)
* [Generative Adversarial Networks 논문](https://arxiv.org/abs/1406.2661)

## ✔️ 차후 할 일
* DCGAN 발전 형태 논문 읽기 및 구현하기
* Discriminator 자리에 ResNet 등의 모델 넣어보기
* Pytorch로 GAN 구현하기
