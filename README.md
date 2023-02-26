# KoGPT-Chatbot
KoGPT2 기반 일상 대화 및 지식 대화 챗봇

# Base model
https://github.com/SKT-AI/KoGPT2

# Dataset 
한국어 챗봇 트레이닝용 문답 페어 데이터 

## Format 
Question,Answer,Category 

Category : 
일상 0, 
이별/분노/슬픔 등(부정) 1, 
사랑/기쁨(긍정) 2,
지식 3


## Dataset 
1. 일상, 이별, 사랑 데이터 
https://github.com/songys/Chatbot_data

2. AI hub 주제별 텍스트 일상 대화 데이터

3. AI hub 감성 대화 말뭉치 

4. Youtube 자막

5. (번외) 1:1 카카오톡 대화 (페르소나)
<img width="491" alt="image" src="https://user-images.githubusercontent.com/21952143/221425074-1da3bc40-f91d-4cb6-bf0f-2a5494d34274.png">
카카오톡 > 대화 설정 > 저장공간관리 > 대화 저장
* 이때 csv 변경하기, 파일명에서 이모지제외 (talk_data.csv 처럼 간단하게) 


# CLI

## Train 
1) Basic (Dataset 1,2,3)
```
!CUDA_VISIBLE_DEVICES=1 python train.py --train --gpus 1 --max_epochs 10
```


2) With kakaotalk couple data
```
!CUDA_VISIBLE_DEVICES=1 python train.py --train --gpus 1 --max_epochs 10 --talk_data {카카오톡 경로}
```

## Inference
```
!CUDA_VISIBLE_DEVICES=0 python train_torch.py  --model_params model_chp/last.ckpt --gpus 1 --chat
```

# Reference 
아래 레포의 코드를 참고하여 작성되었습니다. 
https://github.com/haven-jeon/KoGPT2-chatbot


