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
# 가. 데이터 수집 

---

# 나. 전처리

---

# 다. 데이터 분석방법

---

# 라. 이슈 및 해결
   
---
# 마. 분석 


---
# 바. 사용 코드 
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
# 사. 피드백
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
