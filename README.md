스택오버플로우에서 실행한 `2024 개발자 설문조사` 데이터를 분석했습니다. <br>
분석 과정은 다음과 같습니다. 

- 2024년 개발자들이 사용한 개발 언어 분석을 통한 업계 트렌드 파악
- 데이터 수집
  - 설문지에서 분석에 사용될만한 질문을 가려냄
- Imports
- Functions & Variables
  - DATA_DEVS
  - COMP_KRW
  - standard_figsize
  - get_flattened_list(), get_unique_values() 함수
  - draw_median_salary_barh()
  - draw_salary_boxplot()
- 데이터 불러오기
  - 가려낸 질문만 뽑아내기
- 데이터 전처리
  - info() - null 값이 많이 보임
  - describe() - 숫자 컬럼의 통계 확인
  - describe() - 문자열 컬럼의 통계 확인
  - MainBranch
    - target branch 정의
  - Age
  - Employment
  - RemoteWork
  - EdLevel
  - YearsCodePro
  - DevType
    - NaN 값 제거
  - Country
  - Currency, CompTotal
    - 통화코드만 value로 갖도록 수정
    - 다양한 나라의 연봉 한화로 환산
      - 환율 정보 불러오기
    - 연봉 데이터 이상값 처리
  - Language
    - explode() 함수 사용 - 리스트 내의 값이 각각 row로 추가됨
    - 직군별 언어 묶기 - groupby()
    - 데이터 직군의 사용언어
  - WorkExp
  - Industry
  - 데이터 저장하기 - to_csv()
    - devs_df
    - devs_df_comp
    - devs_lang_df
    - devs_prflang_df
  - 데이터 불러오기
    - full_df
    - comp_df
    - lang_df
    - prflang_df
- 데이터 시각화
  - 인기있는 개발 언어
    - 현재 사용하는 언어
      - barh
    - 가장 많이 쓰이는 개발 언어 상위 10개
      - barh - 상위 10개 언어별 사용자 수
      - barh - 상위 10개 언어별 응답자 수 비율 정보를 그래프에 추가
    - 사용을 희망하는 언어
      - barh
    - 가장 많이 사용을 희망하는 개발 언어 상위 10개
      - barh - 상위 10개 언어별 응답자 수(응답자 수 비율)
    - 언어별 사용자 수 vs 사용 희망자 수
      - subplot - 그래프 비교  
      - 하나의 그래프에 비교할 두개의 데이터를 시각화
  - 데이터 직군 인기 언어
    - TOP 10 비교
      - subplots - 데이터 직군에서 가장 인기 있는 언어(현재 사용 vs 사용 희망)
    - 데이터 직군별 상세 비교
      - bar - 데이터 3개의 직군별 인기 있는 언어 응답자 수 비교
  - 언어별 주요 직군
    - groupby() - 언어별 주요 직군 수
    - 직군별 bar 색 선정
  - 개발 언어별 연봉
    - hist - 전체 연봉 분포
      - 로그변환 - 이상치를 제거하지 않고도 전체 경향 확인
    - barh - 언어별 연봉 중간값
    - boxplot - 언어별 연봉 분포
    - 직군별 연봉
      - 직군별 연봉 중간값
      - 직군별 연봉 분포
