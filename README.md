# business_card_recognition
구현 예정(청사진)
1. 이미지에서 명함 영역을 찾기
- contours 함수를 활용하여 제일 큰 넓이를 가진 영역을 찾는다.
- 허프 변환을 이용하여 원하는 부분을 찾는다.
- 가장 큰 영역을 가진 부분과 이미지가 가진 각도를 활용하여 사진을 회전 시킨다. 그리고 나머지 부분은 삭제한다.
2. 명함을 인식해서 텍스트 추출하기
- contours를 사용한 후 , 브루트 포스로 리스트 모임을 만든다.
3. 카테고리로 구분하기
-  @, ., .com이 있으면 e-mail
- ..로, 동, 시, 194-1 주소와 관련된 키워드가 있으면 주소 카테고리.
- 이름
- 휴대폰: 010-.... - ....
- 회사전화 : 010-....-....

실제 구현
1. 이미지에서 명함 영역을 찾기
- contours 함수를 활용하여 제일 큰 넓이를 가진 영역을 찾는다.(명함마다 디자인달라 구현 불가)
- 허프 변환을 이용하여 원하는 부분을 찾는다.(허프 변환을 통해 선과 선이 만나는 지점을 찾아 명함을 위치를 찾았다.)
- 가장 큰 영역을 가진 부분과 이미지가 가진 각도를 활용하여 사진을 회전 시킨다. 그리고 나머지 부분 삭제한다.(직선이 기울어진 정도로 회전을 하였다.)
2. 명함을 인식해서 텍스트 추출하기
- contours를 사용한 후 , 브루트 포스로 리스트 모임을 만든다.
 (명함의 규격이 다 달라,contour를 하기에는 어려워,pyteseract에서 사진 전체의 이미지를 파악하는 걸로 판단하였다.) 
3. 카테고리로 구분하기(구현 x)
-  @, ., .com이 있으면 e-mail
- ..로, 동, 시, 194-1 주소와 관련된 키워드가 있으면 주소 카테고리.
- 이름
- 휴대폰: 010-.... - ....
- 회사전화 : 010-....-....
- 자연어처리를 추가적으로 배우고 내용을 수정을 해야겠다. 인식률이 높지가 않아 글자가 불분명하여 특정 문자를 찾기가 어려웠다. 추후에 자연어처리를 배워서
  카테고리를 추가하여야겠다.

