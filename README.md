# kakao-arena : 멜론 플레이리스트 예측  
  ### 미션: 플레이리스트 태그, 노래 채우기  
  - 제공데이터를 분석하여 valid의 일부 수록된 태그, 노래를 보고 __태그 10개, 노래 100개 채우기__  
  <p>
   <img src="https://user-images.githubusercontent.com/57060127/95476627-6358c700-09c2-11eb-88ce-798dda58d15b.JPG" width="100%"></img>  
   
  제공데이터: song_meta, genre, train, valid  
  생성데이터: All, song_artist_genre_toptags_id, tag_clustering, genre_clustering  
<br>


-------------------------------------------------------------------------------------------------------------------
- ## Data
  - __song_meta__: 노래장르, 발행일, 노래앨범이름, 가수id, 가수이름 정보 (총 707,989개 곡정보)
  <img src="https://user-images.githubusercontent.com/57060127/91639461-bb122300-ea51-11ea-9e82-7965543d5cca.JPG" width="100%"></img>
  <br>
 
  - __train__: 태그, 플레이리스트 id, 플레이리스트 이름, 노래id, 좋아요수, 발행일 정보 (총 115,071개 플레이리스트정보)  
  <img src="https://user-images.githubusercontent.com/57060127/91639534-3a075b80-ea52-11ea-9a54-75d39b2c63c5.JPG" width="100%"></img>
  <br>
  
  - __genre__: 대장르, 소장르 정보  
  <img src="https://user-images.githubusercontent.com/57060127/91639565-8783c880-ea52-11ea-8b03-ffcfb3a6e286.JPG" width="25%"></img>
  <br>
  <br>
  <br>
  <br>

- ## Generating Data :분석하기 쉬운 형태로 정리한 데이터  
  - __All: 노래별 태그 분리__  
    > 노래특성에 가장 큰 영향을 줄 것이라고 예상되는  __장르,노래이름,가수,태그__ 값을 하나의 데이터로 정리함  
  이 과정에서 노래이름이 같아도 앨범명에따라 노래 id가 다름을 발견  
  <img src="https://user-images.githubusercontent.com/57060127/91657767-814b2600-eafe-11ea-8684-6b771d9f7bea.JPG" width="90%"></img>
  <br>
  <br>
  
  - __song_artist_genre_toptags_id.: 노래별 높은 빈도순으로 태그 나열__   
    > 태그정보가 있는 csv에는 노래가 id값으로 들어가 있고, 플레이리스트별 태그정보가 있음(단일노래기준 태그정보 없음)  
  노래별 태그 빈도수를 알아보기위해 노래별 높은 빈도수로 태그를 정리함  
  <img src="https://user-images.githubusercontent.com/57060127/91657797-f585c980-eafe-11ea-94f5-448ceae9f0bf.JPG" width="100%"></img>
  <br>
  <br>
  
  - __tag_clustering__  
    > 100개의 cluster로 clustering  
  - __genre_clustering__  
    > 약 31종류의 장르가 있음.  
    > 13개의 cluster로 clustering  
  <br>
  <br>
  
  
  
 - ## valid 채우는 방법  
   - __valid__: 채워야할 플레이리스트  
   <br>
   <br>
   
   
  
  - tag가 있다면?  
    - valid에 있는 플레이리스트안에 노래id의 태그를 확인 => 가장 많이 나온 태그를 추출 => 많이 등장한 태그가 노래 태그에 상위권에 있는 노래로 플레이리스트 채우기, 태그 채우기    
    
  - tag가 없다면?  
    - 노래 id를 보고 노래에서 많이나온 태그 확인 => 같은태그를 가진 노래로 채우기, 같은 cluster로 묶인 태그로 채우기  
  
