<h1>운전연수 신청 사이트 - '교차로'</h1>


<h2>1. 기획 의도</h2>
<div dir="auto" style="display: flex;">
<img width="1180" alt="스크린샷 2022-12-27 오전 12 09 34" src="https://user-images.githubusercontent.com/122762202/233516894-6786533c-41da-4253-8c7e-9754db5cd681.png" style = "width: 45%; height : 45%">
</div>


<h2>2. 기대 효과</h2>
<img width="1161" alt="스크린샷 2022-12-27 오전 12 20 31" src="https://user-images.githubusercontent.com/122762202/233516945-286cad78-74ad-4274-85f9-66ecfabf1353.png" style = "width: 45%; height : 45%">


<h2>3. 프로젝트 사용 툴</h2>
<img width="1160" alt="스크린샷 2022-12-27 오전 12 23 33" src="https://user-images.githubusercontent.com/122762202/233516994-0efd63f6-f000-4566-b108-14dba6d0ac86.png" style = "width: 45%; height : 45%">


<h2>4. 담당 업무</h2>

4-1. 메인
- header의 목록들과 footer의 링크 설정
- thymeleaf를 사용해 메인페이지 이용후기 조회
- 기존 이용후기 내용 DB 조회
- 이용후기 내용 최신순으로 DB 업데이트
  
4-2. 이용후기 페이지 - 목록
  - 후기내용 불러오기
  - ajax를 사용하여 무한스크롤 생성
  - 후기 내용 최신순으로 업데이트
  - 자신이 작성한 후기는 바로 삭제 가능

4-3. 이용후기 페이지 - 작성하기
  - 연수가 완료된 사람만 작성가능
  - 별점기능, 파일 업로드기능

4-4. 이용후기 페이지 - 수정하기
  - memberId에 따라 작성한 내용 불러오기
  - 별점, 제목, 내용, 이미지 정보 조회
  
4-4. 이용후기 페이지 - 삭제하기
  - 자신이 작성한 내용 삭제 기능
 
  
  
  
<h2>5. 느낀점</h2>
<h3>5-1. 어려웠던 부분</h3>
📌thymeleaf를 사용하여 무한스크롤 페이징처리를 하는것이 어려웠다. <br>
✔ thymeleaf와 관련된 강사님의 강의를 다시 듣고 처음부터 재구축 하였다.<br><br>
📌프로젝트 초반에는 service와 controller를 어떻게 구분해서 사용해야 하는지 감이 잘 잡히지 않아서 헷갈렸다. <br>
✔ 프로젝트를 통해 학습과 적용을 반복하다보니 자연스레 언제 사용해야 하는지 알게됐다. 특히, service에 내가 필요한 변수를 능숙하게 선언, 사용 할 수 있게 됐다는 점이 큰 수확이었다. <br><br><br><br>


<h3>5-2. 문제를 해결했던 부분</h3>
<h4>📌C드라이브 파일 업로드가 안되던 사건</h4> <br>
🌩문제 상황🌩<br>
처음에 D드라이브로 경로를 설정했다가 C드라이브로 경로를 바꿨는데 C드라이브의 파일이 담겨지지만 불러와지지 않는 사건이 발생했다.(D드라이브는 둘다 <br><br>
🚨문제 원인🚨 <br>
초기에 config에서 경로설정을 D드라이브로 설정을 했었는데, 그것을 잊고 파일 업로드 controller에서만 코드를 수정했다. 즉, 
채팅이 전송될 때 거치는 모든 메소드와 컨트롤러에 전부 로그를 찍어봤는데, list에 담아둔 WebSocketSession이 중간이 실종된다는 것을 확인했다. 즉, 메세지를 받을 대상이 없었기 때문에 onMessage 메소드가 실행되지 않았던 것이다. <br><br>
🚀해결 방법🚀<br>
config와 yml파일의 경로를 수정했더니 파일이 잘 담기고, 잘 가져와 졌다.<br><br><br>


<h3>5-4. 총평</h3>
<h4>🌟 두려워하지 말자. 나는 내 생각보다 끈기있는 사람이다. </h4>



초반에 JAVA에 대해 공부가 부족해 남들보다 시간이 걸렸지만, 잠을 포기하고 이해가 될때까지 파고들어 결국 남들을 따라갈 수 있게 되었다.



<h4>🌟 내가 마주한 오류와 해결방안을 구체적으로 기록해두자. </h4>



정말 많은 오류를 경험하고 해결했는데, 기록을 해두지 않아서 많이 잊어버린 점이 프로젝트가 끝난 이후 아쉬웠다. 간단하게라도 기록하면서 기상천외한 오류를 겪을 동료 개발자들에게 한 줌의 도움이라도 주고싶다. 



<h4>🌟 어떻게 더 소통하는 동료, 소통하는 리더가 될 것인가. </h4>



해당 프로젝트를 진행하면서, 백엔드 작업을 진행할 때 팀장과 팀원들과의 의사소통이 부족했다. GIT을 pull,push,pr 하면서 제때 안해서 많은 오류가 일어났고 해결하는데 많은 시간이 소비되었다. 약 한달간 각자의 역할을 수행하면서 자신의 업무뿐 아니라 다른 사람과의 소통도 중요하다는 걸 뼈져리게 느꼈다. 나는 업무 태도를 지적하고, 해결하려는 자세에 앞서서 그 사람의 마음을 얻는 것이 더 먼저라는 생각이 들었다. 항상 이 경험을 되새기면서 팀원들에게 먼저 다가갈 수 있는 우호적인 사람이 돼야겠다.    


<h2>ERD</h2>
<img width="100%" alt="erd" src="https://user-images.githubusercontent.com/122762202/233519739-7989a676-8520-44ea-842f-feb20ec16a38.png">

