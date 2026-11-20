## F411_LAB 최종 작업 정리 — 초음파 + 온습도 + FreeRTOS

  - CubeMX에서 FreeRTOS 추가, 태스크 분리, UART mutex

  - 시리얼로 확인
    
<img src="https://github.com/user-attachments/assets/ac7f44a7-5e77-440f-b4bd-24629f15344f" width="700">
 <br><br>

 - 오실로스코프로 확인
   
<img src="https://github.com/user-attachments/assets/f7e4e5d4-784d-4e57-a2bb-10e557bdac57" height="380">

<img src="https://github.com/user-attachments/assets/9481515e-bcdf-44cf-860f-44920553c37b" height="380">
<br><br>


## PC에서 MNIST 숫자 인식 → TFLite 변환 → MCU 배포 시뮬레이션 실습

  - 실습 결과
    
<img src="https://github.com/user-attachments/assets/11efcee9-e179-43b4-8f51-1f983ae75f32" width="700">
<img src="https://github.com/user-attachments/assets/0f486a20-303b-4692-b0fb-92ce0134b7d6" width="700">
<br><br>

  - TFLite 변환 및 양자화
   
<img src="https://github.com/user-attachments/assets/a6a7f080-7682-4f17-99d3-902e283966c0" width="700"/>
<br><br>

  - PC에서 TFLite 모델 추론 및 검증
    
<img width="636" height="199" alt="image" src="https://github.com/user-attachments/assets/a526c781-54b3-4d03-89ef-459ce9b2db21" />
<br><br>

  - 시각화: PC 모델 vs TFLite 모델 결과 비교

<img width="689" height="414" alt="image" src="https://github.com/user-attachments/assets/a12b355a-b10c-434e-9d34-7b7801171c34" />
<br><br>

  - 최종비교: 모델 크기 / 추론 시간 / 정확도 비교
    
<img width="654" height="292" alt="image" src="https://github.com/user-attachments/assets/79a125ed-3007-4686-801b-4940f773abfc" />
<br><br>

  - *결론: TinyML이 필요한 이유*

1. 모델 크기 (Memory)

   PC: 427KB → MCU: 115KB
   
   양자화만으로 73%로 줄일 수 있다.

2. 추론 속도 (Latency)
   
   Float32: 0.011ms → Int8: 0.006ms
   
   정수 연산이 실수보다 빠르다.

3. 정확도 (Accuracy)

   97.16% → 97.15% (손실 단 0.01%p)

   현저한 성능 저하 없이 경량화가 가능하다.


   ## STM32F411에 AI 모델 추가

   
