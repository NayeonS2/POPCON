# 공통 프로젝트 D201

![로고](https://user-images.githubusercontent.com/109330614/224963582-f3191ac5-297e-4841-b834-84028e5b3920.png)

# **🔖 프로젝트 소개**

## 🤷‍♀️ 어느새 유효기간을 넘겨버린 기프티콘, 아깝지 않으신가요?

- 쉽고, 편하고, 친절한 **POPCON**과 함께 기프티콘을 관리해보세요
- 갤러리와 문자에서 이미지를 읽어와 자동으로 기프티콘을 등록해줘요
    - 기프티콘 정보를 자동으로 인식해 직접 입력할 필요가 없어요
- 원하는 시간대에 유효기간 만료 전 알림을 받을 수 있어요

## 🤳 간편하게 흔들어서 바로 사용하세요!

- 기기를 흔들면 현위치에서 바로 쓸 수 있는 기프티콘이 팦💥 등장해요
- 지도 탭에서는 내가 가진 기프티콘들을 쓸 수 있는 매장의 정보들을 볼 수 있어요

## 🎁 고마운 사람의 집 앞에 기프티콘을 선물해보세요!

- 지도에서 원하는 위치에, 원하는 기프티콘을 두고갈 수 있어요
- 다른 사람이 두고 간 기프티콘을 주워갈 수 있어요
- 기프티콘을 득템하면 감사메세지는 필수!
- 친구들과의 재밌는 놀이로, 고마운 사람에게 마음을 전할 수단으로 다양하게 활용해보세요
- 집에서 자고있던 워치를 사용할 기회가 될수도,,?✨

---

# **📚 기술스택**

![기술스택](https://user-images.githubusercontent.com/109330614/224963488-bbb02aa9-2c8a-4e0d-8a65-9e8213c196a3.png)

| 분야 | 사용기술 |
| --- | --- |
| FrontEnd | Android(Kotlin), MVVM |
| BackEnd | SpringBoot, FCM |
| Database | MariaDB |
| DevOps | AWS EC2, docker, GitLab Runner, Google Cloud Platform |
| Tool | Jira, Notion, IntelliJ, AndroidStudio, GitLab |
| Design | Figma |

---

# 🧬 **아키텍처**

![아키텍쳐](https://user-images.githubusercontent.com/109330614/224964419-321818cc-104a-4a1e-91f9-71693b5d7f1c.png)

---

# 🔑 ERD

![ERD](https://user-images.githubusercontent.com/109330614/224963352-c7088e06-d784-4c80-aaa6-c24160241683.png)

---

# 📝 **API 명세서**

- [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html) (포스트맨으로 수정할것!)
- Brand controller
    
    
    Get
    /api/v1/brands/orderby_gifticon
    기프티콘 개수 많은 순서대로 정렬된 브랜드 리스트
    
    | Get | /api/v1/brands/orderby_gifticon | 기프티콘 개수 많은 순서대로 정렬된 브랜드 리스트 |
    | --- | --- | --- |
- File controller
    
    
    | POST | /api/v1/files/add_origin | 기프티콘 등록위해 원본 이미지 리스트 업로드 |
    | --- | --- | --- |
    | POST | /api/v1/files/register_gifticon | 등록하기 버튼 누른 후 상품,바코드 이미지 저장 및 db 업데이트 |
    
- Gifticon Controller
    
    
    | PUT | /api/v1/gifticons | 기프티콘 수정 |
    | --- | --- | --- |
    | POST | /api/v1/gifticons | 기프티콘 저장 |
    | DELETE | /api/v1/gifticons | 기프티콘 삭제 |
    | GET | /api/v1/gifticons/{barcode_num} | 기프티콘 조회 |
    | GET | /api/v1/gifticons/{email}/{social} | 유저가 가지고 있는 기프티콘 조회 |
    | GET | /api/v1/gifticons/{email}/{social}/map | 지도에서 띄우는 기프티콘 리스트 |
    | POST | /api/v1/gifticons/brand | 기프티콘 브랜드별 정렬 |
    | GET | /api/v1/gifticons/brandsort/{email}/{social} | 브랜드 기프티콘 순으로 정렬 |
    | GET | /api/v1/gifticons/check | 기프티콘 유호기간 체크 후 상태 변경 / 서버용 APIPOST |
    | POST | /api/v1/gifticons/history | 기프티콘 히스토리 |
- Location Controller
    
    
    | POST | /api/v1/local/search | 현위치 기반 기프티콘 사용가능 한 모든 매장 |
    | --- | --- | --- |
    | POST | /api/v1/local/search/byBrand | 현위치 기반 기프티콘 사용가능 한 지정 브랜드 매장 |
    | POST | /api/v1/local/shake | 흔들었을때 사용가능한 주변 매장 브랜드 |
- Present Controller
    
    
    | POST | /api/v1/presents/get_present | 기부 줍기 |
    | --- | --- | --- |
    | POST | /api/v1/presents/give_present | 기부 버리기 |
    | POST | /api/v1/presents/possible_list | 가까운 선물 리스트, 줍기가능한 선물 리스트 |
- User Controller
    
    
    | GET | /api/v1/user/getlevel | 사용자레벨 |
    | --- | --- | --- |
    | POST | /api/v1/user/login | 로그인 |
    | GET | /api/v1/user/refresh | 토크재발급 |
    | POST | /api/v1/user/update | 사용자정보 변경 |
    | DELETE | /api/v1/user/withdrawal | 사용자정보 삭제 |


- Gifticon controller
  
    PUT
    /api/v1/gifticons
    기프티콘 수정

    POST
    /api/v1/gifticons
    기프티콘 저장

    DELETE
    /api/v1/gifticons
    기프티콘 삭제

    GET
    /api/v1/gifticons/{barcode_num}
    기프티콘 조회

    GET
    /api/v1/gifticons/{email}/{social}
    유저가 가지고 있는 기프티콘 조회

    GET
    /api/v1/gifticons/{email}/{social}/map
    지도에서 띄우는 기프티콘 리스트

    POST
    /api/v1/gifticons/brand
    기프티콘 브랜드별 정렬

    GET
    /api/v1/gifticons/brandsort/{email}/{social}
    브랜드 기프티콘 순으로 정렬

    GET
    /api/v1/gifticons/check
    기프티콘 유호기간 체크 후 상태 변경 / 서버용 API

    POST
    /api/v1/gifticons/history
    기프티콘 히스토리

- Location Controller


    POST
    /api/v1/local/search
    현위치 기반 기프티콘 사용가능 한 모든 매장

    POST
    /api/v1/local/search/byBrand
    현위치 기반 기프티콘 사용가능 한 지정 브랜드 매장

    POST
    /api/v1/local/shake
    흔들었을때 사용가능한 주변 매장 브랜드

- Present Controller
  
    POST
    /api/v1/presents/get_present
    기부 줍기

    POST
    /api/v1/presents/give_present
    기부 버리기

    POST
    /api/v1/presents/possible_list
    가까운 선물 리스트, 줍기가능한 선물 리스트

- User Controller

    GET
    /api/v1/user/getlevel
    사용자레벨

    POST
    /api/v1/user/login
    로그인

    GET
    /api/v1/user/refresh
    토크재발급

    POST
    /api/v1/user/update
    사용자정보 변경

    DELETE
    /api/v1/user/withdrawal
    탈퇴

- Brand controller
  
    Get
    /api/v1/brands/orderby_gifticon
    기프티콘 개수 많은 순서대로 정렬된 브랜드 리스트


- File controller
  
    POST
    /api/v1/files/add_origin
    기프티콘 등록위해 원본 이미지 리스트 업로드

    POST
    /api/v1/files/register_gifticon
    등록하기 버튼 누른 후 상품,바코드 이미지 저장 및 db 업데이트


---

# 👀 기능 엿보기 (GIF)

### 로그인

![로그인](https://user-images.githubusercontent.com/109330614/224963714-70d3d34a-401d-4023-a9f6-cc56685a2d1d.gif)

### 조회, 수정, 삭제

![조회수정삭제](https://user-images.githubusercontent.com/109330614/224964842-6691d667-0846-4fd4-8e6d-b2701b7edc33.gif)

### 사용, 히스토리

![사용히스토리](https://user-images.githubusercontent.com/109330614/224964381-d3d59df9-befa-415f-b4f5-91ac91231f03.gif)

### 기프티콘 등록

![기프티콘 등록](https://user-images.githubusercontent.com/109330614/224963501-61264257-2bf9-4f6e-92e4-623ee3c85999.gif)

### 갤러리 저장으로 등록

![갤러리저장으로등록](https://user-images.githubusercontent.com/109330614/224963456-5026ee18-5c81-413a-9659-bc5a8b78a7f4.gif)

### MMS 수신으로 등록

![MMS수신으로등록](https://user-images.githubusercontent.com/109330614/224963424-4c650f83-24ef-4c15-a4c8-ee97137b453f.gif)

### 위치기반 기프티콘 사용

![위치기반기프티콘사용](https://user-images.githubusercontent.com/109330614/224964820-27e88335-fc88-4f7f-a6f9-b98722608ea4.gif)

### 매장 시연 영상

![매장시연_Trim](https://user-images.githubusercontent.com/109330614/224973435-ef699f25-0dda-4238-b064-88905b4c81b7.gif)

### 주변 매장 정보 검색

![지도 검색_Trim](https://user-images.githubusercontent.com/109330614/224973329-b8503440-55d2-4f8b-956a-858315659735.gif)

### 선물 뿌리기

![선물뿌리기](https://user-images.githubusercontent.com/109330614/224964397-08217a20-321a-40e9-afbb-5e78d7e3c605.gif)

### 선물 줍기, 감사인사

![선물줍기 감사인사](https://user-images.githubusercontent.com/109330614/224964404-01ec601c-eb2e-4919-9e13-6d4675868d10.gif)

### 워치 연동 + 사용

![워치폰_Trim_1](https://user-images.githubusercontent.com/109330614/224973615-1268d8e3-1b14-4894-9ee6-74a208815d3a.gif)

![워치폰_Trim_2](https://user-images.githubusercontent.com/109330614/224973560-9a217c16-32ab-4ce6-bedf-3c17dda413bb.gif)

![워치폰_Trim_3](https://user-images.githubusercontent.com/109330614/224973592-231a40ac-ba5e-45a2-a06e-337c15796eed.gif)

### 워치 선물 뿌리기

![워치선물뿌리기](https://user-images.githubusercontent.com/109330614/224964424-5f0306f7-8eab-4513-8092-e28ce1ab555d.gif)

### 설정화면

![설정화면](https://user-images.githubusercontent.com/109330614/224964412-b19a87c1-f0a7-4468-ac7f-f7cbb991647c.gif)

### 푸시 알림 : 레벨업

![레벨업푸시알림](https://user-images.githubusercontent.com/109330614/224963647-05935615-d695-4ca2-bc69-c500a62be08d.gif)

### 레벨별 프로필 이미지

![레벨별프로필이미지](https://user-images.githubusercontent.com/109330614/224963518-fae8a419-9b51-4224-a149-ee1c1b0c6b4c.gif)

### 유효기간 만료전 푸시알림

### 감사메세지 알림

---

# 🎤소감 한마디

## 나연
- 스프링 부트로 백엔드를 구현한 것도, 웹이 아닌 앱을 구현한 것도 처음이어서 더 애착이 가고 열심히 참여했던 프로젝트였다. 밤새 만든 api가 모바일에서 동작하는 걸 확인할 때면 밤샘 피로가 녹아내리듯 뿌듯한 감정이 들었다. 개발 결과물과 사용자들의 피드백이 너무 좋았던 프로젝트였기 때문에 정책적으로 조금만 더 보완하여 꼭 앱스토에 출시하고 싶은 마음이다. 마지막으로 마음이 잘 맞는 팀원들을 만나 참 복받은 프로젝트 기간이었다고 생각한다.❤

## 동현
- 기프티콘 관리라는 재밌는 주제로 진행해서 좋았고, 처음해보는 모바일 프로젝트라 많이 배울 수 있었습니다!

## 유나
- 새로운 시도를 해볼 수 있었던 좋은 기회였고, 일상 생활에 불편함을 해결할 수 있는 서비스를 개발했다는 점에서 뿌듯했습니다.

## 보경
- 짧은 기간동안 다양한 기능들을 구현하면서 성장할 수 있었던 프로젝트였습니다!!

## 재완
- 서버를 구현하면서 만난 오류들을 수정해가는 경험을 통해 많은것을 배울 수있는 프로젝트였습니다 !!!!