# D-Meta_task
디메타 과제 면접

1. 리눅스 환경에 접속하여 `cd dmeta` 커맨드를 입력하여 'dmeta' 경로로 이동합니다.
2. 이미지 cropping을 하기 위해 다음과 같이 터미널에 입력하면 잘린 이미지 조각들이 'meta/cut/' 경로에 형성됩니다.
   - `python cut_image.py ${자를 이미지명.파일타입} ${M} ${N} {crop된 이미지명}`
   - 예를들어, 'bike.png'라는 이미지를 2x2 크기로 자르고 싶고, 각 잘라진 이미지의 이름을 'crop'으로 하고 싶을 경우, `python cut_image.py bike.png 2 2 crop`을 입력하면 됩니다.
4. 이 잘린 이미지들을 합병하기 위해 다음과 같이 터미널에 입력하면 'dmeta/merge/' 경로에 원본 이미지와 유사한 합병된 이미지가 저장됩니다.
