# YourTube

<div align="center">
<img src="src/yourtube_title.png" alt="YourTube Title Logo" width="80%" />
<h3>24-1 YBIGTA 컨퍼런스</h3>

<p>이용자가 원하는대로 YouTube 영상을 분류하는 크롬 확장 프로그램</p>
<!--<p>$\rm{\large{\color{#ee4e56}YOU}}\large{tube \space algo}\large{\color{#ee4e56}R}\large{ithm \space}\large{\color{#ee4e56}TU}\large{ning \space}\large{\color{#ee4e56}B}\large{rowser \space}\large{\color{#ee4e56}E}\large{xtension}$</p>-->

<!--
<h6>Compatible with</h6>
<div>
<img src=https://img.shields.io/badge/Google_chrome-4285F4?style=for-the-badge&logo=Google-chrome&logoColor=white>
<img src=https://img.shields.io/badge/Microsoft_Edge-0078D7?style=for-the-badge&logo=Microsoft-edge&logoColor=white>
<img src=https://img.shields.io/badge/Brave-FF1B2D?style=for-the-badge&logo=Brave&logoColor=white>
<img src=https://img.shields.io/badge/Vivaldi-EF3939?style=for-the-badge&logo=Vivaldi&logoColor=white>
</div>
<h6>and other Chromium based browsers</h6>
-->

</div>

## 목차
- [문제 정의](#문제-정의)
- [선행 연구](#선행-연구)
- [세부 목표](#세부-목표)
- [접근 방법](#접근-방법)
- [결과 및 주요 기능](#결과-및-주요-기능)
- [팀 구성](#팀-구성)

## 문제 정의
*<프로그램 실행 전 이미지> -> <프로그램 실행 후 이미지> 삽입*

YouTube 사용자들은 추천 알고리즘으로 인해 자신의 원래 목적과 관련이 없는 컨텐츠를 소비하는 경우가 많다. 이를 해결하기 위해 사용자들은 자신이 관심 있는 채널을 구독하고 해당 채널의 영상을 시청하지만, 구독한 채널이 많고 다양한 경우에는 자신이 원하는 컨텐츠를 찾기 어렵다.

이 문제를 해결하기 위해, 구독한 채널의 컨텐츠를 카테고리별로 분류하고, 세부 카테고리로 나누어 영상을 필터링할 수 있는 크롬 확장프로그램을 개발하고자 하였다. 이 프로그램을 통해 YouTube 사용자는 원하는 컨텐츠를 쉽게 분류하고 탐색하여 시청할 수 있다.

## 선행 연구
*(Optional 필드; 생략해도 무관)*

## 세부 목표

*(세부적인 목표 및 계획)*

1. YouTube API를 이용해 사용자의 구독 정보를 가져온다.
2. 구독된 채널별로 최신 영상을 15개씩 가져온다.
3. 가져온 영상들을 YouTube 영상 카테고리에 따라 분류한다.
4. 카테고리별로 영상들을 다시 세부 카테고리에 따라 분류한다.

   4-1. 이용자 입력에 따라 새로운 세부 카테고리 설정 가능.


## 접근 방법

1. **태스크** *(세부 목표를 달성하기 위한 구체적인 태스크)*
    - 파이프라인 팀
        - 데이터베이스 구축
        - Google Cloud Platform을 이용해 서버 구축
        - 프론트엔드 구현
        - 크롬 확장 프로그램 배포
    - 모델링 팀
        - 영상 카테고리 분류 모델 학습을 위한 데이터셋 수집
        - 영상 카테고리, 세부 카테고리 분류를 위한 모델 학습
        - 모델 배포

2. **데이터셋** *(사용한 데이터셋, API 등)*
    - YouTube API
        - 이용자의 구독 채널 목록을 가져온다.
    - YouTube Video Description Dataset
        - YouTube의 영상 7,000개에 대한 세부 정보들을 크롤링하여 직접 구축한 데이터셋.
     - OpenAI API
        - 영상 데이터셋에서 업로더가 카테고리 설정을 안했을 때 설정되는 영상의 Default 카테고리인 22번 카테고리에 대해서 OpenAI API를 이용해 GPT-4o로 카테고리 재분류를 수행했음.

3. **모델링/아키텍쳐 등**
    <img src="src/YourTube_Architecture.png" alt="YourTube Architecture" width="80%" />

   - 전체 카테고리 분류 모델
      - 구독한 채널의 영상들의 정보를 바탕으로 영상들을 YouTube 기본 제공 카테고리에 맞게 분류한다. 전체 카테고리 -> BERT Multilingual Base Model (cased) Pre-trained 및 Fine-tuned
   - 세부 카테고리 분류 모델
      - 카테고리별로 분류된 영상들에 대해 세부 카테고리를 기준으로 분류한다. 세부 카테고리 -> Sentence Transformer(paraphrase-MiniLM-L6-v2)
   - Mongo DB
        - (Description)

## 결과 및 주요 기능

*(평가 지표, 구현한 핵심 기능 등)*

우리가 학습시킨 모델의 카테고리 분류 정확도 제시

프로그램을 이용해 특정 영상들을 분류한 스크린샷 제시 (대분류 및 세부 카테고리 분류)

## 팀 구성

| 이름  | 팀  | 역할  |
|:-----:|:----:|:-----:|
| **[조윤영](https://github.com/younyoungieo)** | DE |  파이프라인  |
| **[김현호](https://github.com/smthswt)** | DE | 파이프라인 |
| **[임종혁](https://github.com/2000may24th)** | DE | 파이프라인 |
| **[김예진](https://github.com/gina261)** | DA | 모델링 |
| **[곽민규](https://github.com/DeokbaeKwak)** | DS | 모델링 |
| **[이승준](https://github.com/aiseungjun)** | DS | 모델링 |
| **[박경욱](https://github.com/danielredglasses)** | DS | 모델링 |

