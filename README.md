# YourTube

<div align="center">
<img src="src/yourtube_title.png" alt="YourTube Title Logo" width="80%" />
<h3>YourTube</h3>

<em>YOUtube algoRithm TUning Browser Extension</em>

</div>

## 목차
- [문제 정의](#문제-정의)
- [선행 연구](#선행-연구)
- [세부 목표](#세부-목표)
- [접근 방법](#접근-방법)
- [결과 및 주요 기능](#결과-및-주요-기능)
- [팀 구성](#팀-구성)

## 문제 정의
*(프로젝트를 진행하게된 배경 및 motivation 간략하게 서술)*

*<프로그램 실행 전 이미지> -> <프로그램 실행 후 이미지> 삽입*

YouTube 사용자들은 추천 알고리즘으로 인해 자신의 원래 목적과 관련이 없는 컨텐츠를 소비하는 경우가 많다. 이를 해결하기 위해 사용자들은 자신이 관심 있는 채널을 구독하고 해당 채널의 영상을 시청하지만, 구독한 채널이 많고 다양한 경우에는 자신이 원하는 컨텐츠를 찾기 어렵다.

이 문제를 해결하기 위해, 구독한 채널의 컨텐츠를 카테고리별로 분류하고, 세부 카테고리로 나누어 영상을 필터링할 수 있는 크롬 확장프로그램을 개발하고자 하였다. 이 프로그램을 통해 YouTube 사용자는 원하는 컨텐츠를 쉽게 분류하고 탐색하여 시청할 수 있다.

## 선행 연구
*(Optional 필드; 생략해도 무관)*

## 세부 목표

*(세부적인 목표 및 계획)*

프로그램 사용자의 YouTube 구독 정보를 가져온다. > 구독된 채널별로 최신 영상 10개를 가져온다. > 영상들을 카테고리별로 분류한다. > 각 카테고리별로 세부 카테고리 분류를 수행하고, 분류 결과에 따라 영상들을 웹페이지에 표시한다. (이용자 입력에 따라 세부 카테고리 설정 가능)

## 접근 방법

1. **태스크** *(세부 목표를 달성하기 위한 구체적인 태스크)*
    - 모델링 팀
        - (Description)
    - 파이프라인 팀
        - (Description)

2. **데이터셋** *(사용한 데이터셋, API 등)*
    - YouTube API
        - (Description)
    - YouTube Video Description Dataset
        - YouTube의 영상 7,000개에 대한 세부 정보들을 크롤링하여 직접 구축한 데이터셋.
        - 1차 크롤링 후, 업로더가 카테고리 설정을 안했을 때 설정되는 영상의 Default 카테고리인 22번 카테고리에 대해서 OpenAI API를 이용해 GPT-4o로 카테고리 재분류를 수행했음.

3. **모델링/아키텍쳐 등** *(프로젝트 특성 및 목표에 따라)*
    ![image](https://github.com/DeokbaeKwak/24-1_YourTube/assets/121343417/53a62634-8d5a-4343-a409-ec48c57e44d5)
    ![image](https://github.com/DeokbaeKwak/24-1_YourTube/assets/121343417/2209d8ae-8961-4829-ae33-c56509eb5813)

   
    - (Models)
        - (Description)
    - (Service Architecture)
        - (Description)

## 결과 및 주요 기능

*(평가 지표, 구현한 핵심 기능 등)*

## 팀 구성

| 이름  | 팀  | 역할  |
|-----|----|-----|
| **[조윤영](https://github.com/younyoungieo)** | DE |  팀장  |
| **[김현호](https://github.com/smthswt)** | DE | (역할) |
| **[임종혁](https://github.com/2000may24th)** | DE | (역할) |
| **[김예진](https://github.com/gina261)** | DA | (역할) |
| **[곽민규](https://github.com/DeokbaeKwak)** | DS | (역할) |
| **[이승준](https://github.com/aiseungjun)** | DS | (역할) |
| **[박경욱](https://github.com/danielredglasses)** | DS | (역할) |

