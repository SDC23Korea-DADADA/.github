<div align = "center">
<p align="center">
  <img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/7691bbc3-d79b-4066-9e7c-c64b83cad33b" alt="app_logo" width="128">
</p>
<h3>One Closet</h3>
</div>

## 📌 목차

1. [**앱 소개**](#-앱-소개)
1. [**서비스 소개**](#-서비스-소개)
1. [**기술 스택**](#-기술-스택)
1. [**협업**](#-협업)
1. [**시스템 구조도**](#-시스템-구조도)
1. [**팀 소개**](#-팀-소개)

<div id="1"></div>

## 📱 앱 소개

One Closet은 삼성 의류 관리 가전기기 고객들에게 컴퓨터 비전 기술 기반으로 더 편리하고 새로운 서비스를 제공하고 옷장 관리를 돕는 앱 서비스입니다. <br>의류 이미지에서 분류, 재질, 색상을 추출해 **`관리 코스를 추천하고`** 옷장에 등록된 의류 이미지를 직접 피팅할 수 있는 **`가상피팅`** 기능을 제공합니다.

<div id="2"></div>

## ⏳ 서비스 소개

#### 의류 관리 코스 기능

https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/32ec9603-e51d-481d-921e-c72cc95765d6

- 의류 이미지에서 재질, 색상, 분류를 추출하고 재질에 따른 삼성 세탁, 건조, 에어드레서 코스를 추천해줍니다.
- 의류 정보에는 추가 정보를 입력할 수 있고 추가 정보를 바탕으로 한번에 옷을 찾아볼 수 있습니다.

#### 가상 피팅 기능

https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/66c3a006-1b8e-40e8-8fc3-9d164c4ba807

- 모델 이미지에 의류 이미지(상의, 하의, 한벌옷)를 넣어서 가상 피팅한 결과를 받아볼 수 있습니다.
- 생성된 가상 피팅 결과 이미지를 달력에 등록해 코디 계획으로 등록할 수 있습니다.

#### 디지털 옷장

<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/0427a4a6-f43d-40bd-b48c-418204c916c3" width="25%"/>
<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/f2f830a4-8146-494e-ba3d-a502332a83df" width="25%"/>
<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/9d50755d-0ed7-491f-9cb9-a92b61e4507b" width="25%"/>

- 사용자 필요에 따라 아이콘, 색상, 이름을 커스텀하여 옷장을 추가/삭제할 수 있습니다.
- 등록된 옷은 유저가 선택한 옷장에 등록되어 한 눈에 파악할 수 있고 가상 피팅에 사용됩니다.

#### 데일리 코디

<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/ebb8ddde-b032-4eb8-b3f6-8717534b257a" width="25%"/>
<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/fcd1656c-dc4d-4c9b-b94f-0e727368064c" width="25%"/>
<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/86fdb91d-cc0e-4971-9369-0352d13ca0e2" width="25%"/>

- 사용자의 그 날의 코디를 등록하고 날짜별로 확인할 수 있습니다.
- 가상 피팅 기능을 이용해 특정 날짜의 코디 계획을 세울 수 있습니다.

<div id="3"></div>

## 📍 기술 스택

### Android

### Backend

#### ERD
<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/102503928/fdf5fb33-f289-4047-9e75-3016174288b3"/>

#### API 명세서
https://minsung37.notion.site/OneCloset-API-b1079cc23d1243998b7d7369da41a52f?pvs=4

### AI

<div id="4"></div>

#### 데이터 수집

|    사이트    |    데이터 명     | 사이트 주소                                                                                        |
| :----------: | :--------------: | :------------------------------------------------------------------------------------------------- |
|    AI-hub    | K-fashion 이미지 | https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=51 |
| deep-fashion | DeepFashion  | https://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html                                             |

#### 의류 판단

<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/71217221/adf42a0f-79d5-47cc-8185-c977b812d8e7" width="40%"/> <img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/71217221/268ea150-a597-4458-8ebb-ef3fbfaf10bf" width="40%"/>

- `yolov5`을 사용하여 학습시켰습니다.
- label은 `clothings` 만 존재하여 의류가 감지되는지에 대한 여부만 판단해줍니다.

#### 의류 재질 탐지

<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/71217221/2b991e13-1d71-4d2a-a32c-5fe0ce189da7" width="30%"/> <img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/71217221/ee5ef2f7-2b46-4bdb-b24f-4b1eb9d738cb" width="30%"/>

| 분류 | 내용 |
| :-----------: | :---------------------: |
|     모델      | pytorch EfficientNet2_m |
|    정확도     |         89.43%          |
|     loss      |         0.3277          |
|   optimizer   |          Adam           |
| learning rate |         0.0005          |


- 분류 라벨
  - 면
  - 니트
  - 데님
  - 쉬폰
  - 패딩
  - 트위드
  - 플리스
  - 가죽
  - 코듀로이

#### 의류 종류 분류

<img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/37768793/d482ea7e-514c-4064-9327-d6d4a198aa0c" width="30%"/> <img src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/37768793/1259556e-53fc-44fb-9f4d-7ceedf2c8e6c" width="30%"/>

| 분류 | 내용 |
| --- | --- |
| 모델 | pytorch EfficientNet_v2_s |
| 정확도 | 92.45% |
| loss | 0.2802 |
| optimizer | SGD |
| learning rate | 0.001 |

- 분류 라벨 (18종)
    - 외투 - 코트, 재킷, 점퍼/짚업, 패딩, 가디건, 베스트
    - 상의 - 긴팔티, 반팔티, 셔츠/블라우스, 니트웨어, 후드티, 민소매
    - 하의 - 긴바지, 반바지, 롱스커트, 미니스커트
    - 한벌옷 - 원피스, 점프수트

#### 의류 색상 분류

- `k-means clustering` 알고리즘을 이용하여 픽셀을 군집화한 후, 가장 유사한 색상으로 매핑하였습니다.
- 유사 색상을 정확하게 판단하기 위해 `CIELAB 색 공간`을 사용하였습니다.
- 분류 라벨 (19종)
    
    블랙, 그레이, 그린, 네이비, 라벤더, 레드, 민트, 베이지, 브라운, 블루, 스카이블루, 옐로우, 오렌지, 와인, 카키, 퍼플, 핑크, 화이트, 다채색

## 📃 협업

<img width="512" alt="image" src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/68934392/17756f31-ba80-4447-9ec5-83e9d3c3bd25">

<div id="5"></div>

## 🔎 시스템 구조도

<img width="750" alt="image" src="https://github.com/SDC23Korea-DADADA/OneCloset-Introduction/assets/23161060/92bfe3a2-a306-4ac3-a5e2-f97e321a255a">

<div id="6"></div>

## 🙋🏻 팀 소개

| 김동현                                                                                                                                   | 김주용                                                                                                                                              | 김소연                                                                                                                                            | 정수정                                                                                                                                        | 지민성                                                                                                                                       | 송찬환                                                                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| <a href="https://github.com/hhkers"><img src="https://avatars.githubusercontent.com/u/74969432?v=4" alt="" width="100" height="100"></a> | <a href="https://github.com/Kim-JuYong"><img src="https://avatars.githubusercontent.com/u/68934392?v=4" alt="jyo_ong" width="100" height="100"></a> | <a href="https://github.com/soyeonnnb"><img src="https://avatars.githubusercontent.com/u/71217221?v=4" alt="ppeper" width="100" height="100"></a> | <a href="https://github.com/sujeong1201"><img src="https://avatars.githubusercontent.com/u/37768793?v=4" alt="" width="100" height="100"></a> | <a href="https://github.com/minsung37"><img src="https://avatars.githubusercontent.com/u/102503928?v=4" alt="" width="100" height="100"></a> | <a href="https://github.com/cksghks89"><img src="https://avatars.githubusercontent.com/u/23161060?v=4" alt="" width="100" height="100"></a> |
| 멘토                                                                                                                                     | 안드로이드                                                                                                                                          | 의류 판단 & 재질 분류                                                                                                                             | 종류 분류 & 색상 분류                                                                                                                                | API                                                                                                                                          | 인프라 & 가상피팅                                                                                                                             |

<br>
