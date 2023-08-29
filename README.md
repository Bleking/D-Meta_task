# D-Meta_task
디메타 과제 면접

## 코드 실행하기
1. 리눅스 환경에 접속하여 `cd dmeta` 커맨드를 입력하여 'dmeta' 경로로 이동합니다.
2. 이미지 cropping을 하기 위해 다음과 같이 터미널에 입력하면 잘린 이미지 조각들이 'meta/cut/' 경로에 형성됩니다.
   - `python cut_image.py ${자를 이미지명.파일타입} ${M} ${N} {crop된 sub image명}`
   - 예를들어, 'bike.png'라는 이미지를 2x2 크기로 자르고 싶고, 각 잘라진 sub image의 이름을 'crop'으로 하고 싶을 경우, `python cut_image.py bike.png 2 2 crop`을 입력하면 됩니다.
3. 이 잘린 이미지들을 합병하기 위해 다음과 같이 터미널에 입력하면 'dmeta/merge/' 경로에 원본 이미지와 유사한 합병된 이미지가 저장됩니다.
   - `python merge_image.py ${sub image명} ${M} ${N} ${merged image명}`
   - 예를들어 'crop'이란 이름으로 sub image들을 이름붙였고, 'result'라는 이름을 가진 이미지 파일을 생성하고 싶으면, `python merge_image.py crop 2 2 result`를 입력하면 됩니다. 단, M, N값은 이미지를 자를 때 입력한 값과 동일해야 합니다.
  
## 진행 방식
### cut_image.py
- crop된 sub image들의 위치 정보를 알 수 없도록 1에서 sub image의 총 개수 사이에서 무작위로 이름이 붙여지도록 하였습니다.

### merge_image.py
- 회전 및 이동에 불변하는 특징 검출기(feature detector)인 SIFT를 사용하여 원본 이미지 및 sub image들에서 keypoint와 descriptor값을 뽑아내고, 이들을 이용해 변형된 sub image들을 복구한 뒤에 merge하는 방식을 택했습니다.
