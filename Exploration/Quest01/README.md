# AIFFEL_quest_rs
18기 유비 레포지토리
# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 코더의 이름을 작성하세요.
- 리뷰어 : 김정민(Kimjeongmin92)


# PRT(Peer Review Template)
- [o]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
  - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
       네, 확인 되었습니다.
    
  - 중요! 해당 조건을 만족하는 부분을 캡쳐해 근거로 첨부
       DeepLabV3 모델을 이용해 사람 영역을 분리하고, 배경 blur 처리가 적용된 결과 이미지입니다.
       최종 출력 이미지가 포함되어 있어 프로젝트 목표인 인물모드 구현 여부를 확인할 수 있었습니다.

  
    <img width="735" height="439" alt="image" src="https://github.com/user-attachments/assets/f49e3e16-759e-4265-b200-beda8059afb8" />

<img width="798" height="433" alt="image" src="https://github.com/user-attachments/assets/2ff73011-8eae-4267-8b1b-67dfc701bb25" />



- [o]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**

    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
      segmentation mask를 생성한 뒤, cv2.bitwise_not, cv2.bitwise_and, np.where()를 활용하여 피사체 영역과 배경 영역을 분리하고 합성하는 부분이 잘 표현되었습니다.
      img_bg_mask = cv2.bitwise_not(img_mask_color)
      img_bg_blur = cv2.bitwise_and(img_orig_blur, img_bg_mask)
      img_concat = np.where(img_mask_color == 255, img_orig, img_bg_blur)
      
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부

<img width="839" height="766" alt="image" src="https://github.com/user-attachments/assets/ecc02ce7-0830-4c66-8597-ec95f06a542e" />

<img width="708" height="429" alt="image" src="https://github.com/user-attachments/assets/c3b4beab-f76a-4dc7-bffa-6340d93c325f" />


        
- [o]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인

사람 사진을 이용한 인물모드 구현 이후, 고양이 사진에도 같은 semantic segmentation 방식을 적용하였고, 배경을 blur 처리하는 동물 아웃포커싱 실험을 진행했습니다. 그리고, 저와 달리 고양이 본체만 있는 사진이라서 보다 요구사항에 정확하게 결과물이 나왔습니다.

        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부

<img width="772" height="409" alt="image" src="https://github.com/user-attachments/assets/cdadc0b3-2c59-44bd-b4dc-7da632c0b101" />

<img width="773" height="497" alt="image" src="https://github.com/user-attachments/assets/1a6ff6ce-edd6-4419-9077-73b1097e802a" />

        
- [o]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
특히 인물모드 구현의 핵심이 단순한 blur 처리가 아니라 segmentation mask의 정확도에 있다는 점을 잘 짚었습니다.

        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
     
        - <img width="750" height="473" alt="image" src="https://github.com/user-attachments/assets/993a4741-c4e9-49ac-af7d-13139dce98b8" />

        <img width="975" height="424" alt="image" src="https://github.com/user-attachments/assets/6ab46e9c-a8c6-48a5-b328-95bb471001f4" />

        

- [o]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
   이미지 불러오기, 마스크 생성, 배경 합성 과정에서 반복되는 코드가 있었습니다.
   사람 이미지와 고양이 이미지에 비슷한 로직이 반복되므로, 함수로 정리하면 코드가 더 간결하고 재사용하기 쉬울 것 같습니다.

        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          
          <img width="873" height="473" alt="image" src="https://github.com/user-attachments/assets/6f2c2873-de0c-4a13-8f17-23562955c3b9" />

<img width="718" height="396" alt="image" src="https://github.com/user-attachments/assets/3d290e48-1d44-4a67-865b-9daf55c677f4" />


# 회고(참고 링크 및 코드 개선)
```
# 리뷰어의 회고를 작성합니다.

이번 코드 리뷰를 통해 인물모드 구현에서 가장 중요한 부분은 segmentation mask의 품질이라는 점을 확인했습니다.
DeepLabV3를 사용하면 사람이나 고양이 영역을 분리할 수 있지만,
저의 경우는 머리카락, 털, 히잡처럼 경계가 복잡한 부분에서는 오분류가 발생할 수 있었습니다.

좋았던 점은 기본 인물모드뿐 아니라 고양이 아웃포커싱과 배경전환 크로마키 합성까지 시도하면서 각자가 사용한 사진이 다르기에 발생할 수 있는 문제점과 개선점이 달랐다는 점에서 재밌었는데... 알고 재밌는 건지 그냥 재밌는 건지... 그것이 알고 싶습니다...

개선점으로는 반복되는 이미지 처리 과정을 함수화하면 코드가 더 간결하고 효율적으로 바뀔 수 있을 것 같다고 하지만
솔직하게 이 부분은 아직 저도 이해하지 못해서 복습이 필요한 것 같습니다.

# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
