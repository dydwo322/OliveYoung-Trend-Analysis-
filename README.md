# Text-Mining Project(OliveYoung-Trend-Analysis)

<img width="500" alt="OliveYoung" src="https://user-images.githubusercontent.com/79880476/203081488-d2794fad-7fd3-4b0a-b3c3-0cfa46ebdf51.jpg">

### ○ 프로젝트 주제 
올리브영의 고객 리뷰 데이터와 화장품이 가진 성분들을 이용해 트렌드와 관련된 요소들을 분석해 보고 소비자 성향을 분석

### ○ 프로젝트 기간
22.08.08 ~ 22.08.19

### ○ 프로젝트 분석 목표

<div><img width="500" height="150px" alt="crawling" src="https://user-images.githubusercontent.com/79880476/203086943-b69dde05-c282-441d-aadf-669bd20959df.jpg"><p>- 크롤링을 통해 활용할 수 있는 데이터 파악</p></div>

<div><img width="500" height="150px" alt="ewa" src="https://user-images.githubusercontent.com/79880476/203086934-481ca132-a434-43dc-a464-79a3f2eece89.jpg"><p>- 제품에 들어간 성분의 등급 점수와 리뷰 점수와의 상관관계 분석</p></div>

<div><img width="500" height="150px" alt="keyword" src="https://user-images.githubusercontent.com/79880476/203089489-1cadf244-8dd0-44a5-b449-540cce9b6632.jpg"><p>- 상품 설명에서 어필 하고 있는 키워드와 리뷰에서 해당 키워드가 일치하는지 분석</p></div>

---
# 1. 데이터 수집 
### 1. 올리브영 스킨/로션 화장품 리뷰 크롤링
### 2. COOS를 이용한 성분별 등급 크롤링
### 3. 리뷰어들의 세부 선택정보 크롤링
---
# 2. 전처리
### 1. 화장품의 성분표을 전처리
### 2. 화장품 성분들을 등급 변환해주는 전처리
---
# 3. 데이터 분석방법

---
# 4. 이슈 
### 1. 리뷰의 개수가 적은 제품, 같은 제품이지만 다른 상품으로 나오는 제품들, 제품당 크롤링 가능 개수 1000개 제한
### 2. 성분표 제품별로 형식이 규격 없이 제각기로 표시됨
### 3. 화장품 도메인에서만 사용하는 단어들이 토큰화X
### 4. 리뷰의 라벨링 & 긍부정 사전의 한계
---
# 5. 해결
### 1. 리뷰 개수 부족 & 중복 상품 제거 → 83개의 제품(제품당 댓글 개수는 충분하다고 판단)
### 2. 성분표 제품별로 형식을 동일하게 정규표현식을 이용하여 정형화 작업
### 3. Customized KoNLPy 라이브러리 활용하여 화장품 도메인 단어(닦토,흡토) 토큰화
### 4. 리뷰의 라벨링을 새로운 조건 및 정교화 작업을 통해 잘못 분류 되는 비중을 낮춤
---
# 6. 분석 
### 1. 전체 리뷰의 내용을 LDA 토픽 모델링하여 '보습,진정,자극'의 3가지 카테고리로 분류 되었다.
<table>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334695-814dd302-4b38-4e94-9074-498f77e7481b.jpg"/>- LDA 토픽 모델링 전체 키워드</td><td><img  src="https://user-images.githubusercontent.com/79880476/203334717-d5722778-0356-4942-94dd-55fbbbb7f81a.jpg"/> - LDA 토픽 모델링 '진정'</td>
  </tr>
  <tr align=center>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334744-42125897-ddec-4615-8892-2474f44d7300.jpg"/>- LDA 토픽 모델링 '자극'</td><td><img  src="https://user-images.githubusercontent.com/79880476/203334761-c921fe16-655c-413e-91f0-722e6d0f200c.jpg"/>- LDA 토픽 모델링 '보습'</td>
  </tr>
</table>

### 2. 제품 설명 강조 키워드 '보습,진정,자극'의 빈도를 수치화하여, 광고 키워드와 비교하였는데 83개 제품 중 14개만 일치하였다.
<table>
  <tr>
    <td><img src="https://user-images.githubusercontent.com/79880476/203334488-52d14bed-14c8-441a-8964-8b37a5aca6f1.jpg"></td>
  </tr>
  <tr align=center><td> -광고 키워드와 제품 키워드 비교</td></tr>
</table>

### 3. 성분 등급 점수 & 댓글 평가 지수 상관 관계 분석(긍정 - 하강그래프 / 부정 - 상승그래프가 이상적), 잘 나오지 않았다.

<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203342856-5e07e51c-10c1-4fae-8453-adef65f92d9b.jpg"></td>
  </tr>
  <tr align=center><td>- 전체 제품의 성분 score값과 긍부정 리뷰 비율의 그래프</td></tr>
</table>

---
# 7. 결론
<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203334516-b5bd2da3-e1b7-4946-ba8f-080848e02ccd.jpg"></td>
  </tr>
  <tr align=center><td>- 제품 키워드 이용한 키워드 분포도</td></tr>
</table>
  
### ∴ 제품 키워드 실제 효능과 무관하지만, 소비자에게 사용자(리뷰어)들이 평가한 효능 수치화 해서 정보 제공 목적으로 활용 가능하다고 판단하였습니다.<br>
<table>
  <tr >
    <td><img src="https://user-images.githubusercontent.com/79880476/203342847-cf1713b7-a786-44e1-8e07-13bed3558287.jpg"></td>
  </tr>
  <tr align=center><td>- 제품 성분등급 & 제품의 긍정 리뷰 지수 간의 상관관계 그래프</td></tr>
</table>

### ∴ 약간의 관계성이 있어 보이지만, 표본 데이터 83개 & 긍정 리뷰 비중이 95%정도 이기 때문에 연관성을 분석하기에 한계가 있고, 좀 더 정확한 분석을 하기위해서 데이터가 더 필요하다고 판단하였습니다.<br>

---
# 8. 사용 코드 
<table>
    <thead>
        <tr>
            <th>목록</th>
            <th>파일명</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=3>올리브영 리뷰 크롤링</td>
            <td>
                <a>.ipynb</a>
            </td>
            <td> 올리브영 리뷰 크롤링 코드</td>
        </tr>
        <tr>
            <td>
                <a>.ipynb</a>                
            <td>올리브영 화장품 성분표 크롤링 코드</td>
        </tr>
        <tr>
            <td>
                <a>.ipynb</a>     
            <td> 올리브영 리뷰어의 정보 크롤링 코드</td>
        <tr>
            <td>화장품 성분표 전처리</td>
            <td>
                <a>.ipynb</a>     
            <td> 크롤링 해온 화장품 성분표 전처리 코드 </td>
        </tr>
        <tr>
            <td>화장품 등급 점수 변환</td>
            <td>
                <a>.ipynb</a>     
            <td> 화장품 마다 있는 성분들을 등급 점수로 변환 해주는 코드 </td>
        </tr>        
        <tr>
            <td>화장품 광고 키워드</td>
            <td>
                <a>.ipynb</a>
            <td>화장품 광고 키워드와 리뷰데이터의 상관관계를 파악하는 코드</td>
        </tr>        
    </tbody>
</table>


---
# 9. 피드백
- 성분의 성분별 등급을 스코어화 하는데 그것을 가지고 전체 스코어를 평균값을 구하고, 그것을 기준으로 비교 할 수 있는 지표(분산,평균치를 기준으로 4분위를 표시 etc..)을 구해서 추가해주면 좀 더 좋을 거 같다.
- 긍정리뷰의 비율과 성분등급의 minmaxscaled를 그린 그래프를 긍정비율의 상º하위 20%의 평균을 구해서 비교해봐라.
- 성분의 성분별 등급을 스코어화 하는데 과정을 좀 더  추가 해줬으면 좋겠다. 과정을 모르는 학생분들은 알기 쉽지 않다.
- 마지막 그래프에서 기존 앞에 보여준 스코어랑 달리 minmaxscaled로 수치로 바꾸는 과정 왜 선택해서 바꿔서 그래프를 그렸는지 이유랑 이런것을 보여주는게 필요할 거 같다.
- 토큰화 시, 안걸러지는 도메인 용어를 용어사전으로 만들어서 커스텀마이징을 이용한 것은 잘했다.
- 주제가 되게 괜찮았다. 또한 여러가지 성분 등급표, 광고 키워드 등 여러가지 활용할 수있는 자료들이 많았던 조였고, 나중에 이를 통해서 성분쪽으로 관련지어 진행해서 하면 괜찮을 것 같다.
---
###  ○ 역할
- 이재엽 : 데이터 크롤링(리뷰) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 김용재 : 데이터 크롤링(화장품의 성분표) & 데이터 전처리(성분표)
- 정효제 : 데이터 크롤링(광고 키워드) & 데이터 전처리(성분표) 
- 한서연 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
- 이정아 : 데이터 크롤링(화장품 성분 등급) & 데이터 등급점수와 리뷰점수간 상관관계 분석 
- 전은성 : 데이터 크롤링(리뷰어의 선택 키워드) & 데이터 키워드 간 상관관계 분석
