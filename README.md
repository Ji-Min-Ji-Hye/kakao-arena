# kakao-arena : 멜론 플레이리스트 예측  
  __플레이리스트 태그, 노래 채우기__  
<br>

- ## Data
  - song_meta: 노래정보
  <img src="https://user-images.githubusercontent.com/57060127/91639461-bb122300-ea51-11ea-9e82-7965543d5cca.JPG" width="100%"></img>
  <br>
 
  - train: 플레이리스트정보  
  <img src="https://user-images.githubusercontent.com/57060127/91639534-3a075b80-ea52-11ea-9a54-75d39b2c63c5.JPG" width="100%"></img>
  <br>
  
  - genre: 장르정보  
  <img src="https://user-images.githubusercontent.com/57060127/91639565-8783c880-ea52-11ea-8b03-ffcfb3a6e286.JPG" width="25%"></img>
  <br>
  <br>
  <br>
  <br>
  
  - valid: 채워야할 플레이리스트  
  __목표__: 플레이리스트당 노래 100곡, 태그 10개 채우기  
  <img src="https://user-images.githubusercontent.com/57060127/91639671-31635500-ea53-11ea-81a5-646353e789ed.JPG" width="100%"></img>
  <br>
  <br>
  
  
  
- ## Generating Data :분석하기 쉬운 형태로 정리한 데이터  
  - __All: 노래별 태그 분리__  
  p.s) 노래이름이 같아도 앨범명에따라 노래 id가 다른것을 알게됨.  
  <img src="https://user-images.githubusercontent.com/57060127/91657767-814b2600-eafe-11ea-8684-6b771d9f7bea.JPG" width="90%"></img>
  <br>
  <br>
  
  - __song_artist_genre_toptags_id.: 노래당 태그 높은 빈도수순으로 태그 나열__   
  <img src="https://user-images.githubusercontent.com/57060127/91657797-f585c980-eafe-11ea-94f5-448ceae9f0bf.JPG" width="100%"></img>
  <br>
  <br>
  
  
  - __tag_clustering__  
  100개의 cluster로 clustering  
  - __genre_clustering__  
  약 31종류의 장르가 있음.  
  - 13개의 cluster로 clustering  
  
 - ## valid채우는 방법  
  
