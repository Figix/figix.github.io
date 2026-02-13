---
title: "Git을 간단하게 이해해보자 - 3편"
date: 2026-02-12T12:47:35+09:00
license: MIt
comments: true
draft: false
categories:
    - Git
build:
    list: always    # Change to "never" to hide the page from the list
---
## Git Bash[CLI] & Git Fork[GUI]
Git bash[CLI] 환경으로 사용하는 간단한 팁과 Git Fork[GUI] 환경하는 방법으로 포스팅을 다루겠습니다.  

| 내용 | 링크 |
|:---:|:---:|
| Git Bash [CLI - 키보드위주의 환경] | https://git-scm.com/install/ |
| Git Fork [GUL환경 - 마우스 사용하기 좋은 환경] | https://git-fork.com/ |
| Github | https://github.com/dashboard |

위 링크로 다운로드를 진행해주세요.  
![](깃설명1.png)![](깃설명2.png)![](깃설명3.png)
그림대로 따라오시면, 깃주소를 복사하는 것까지 따라오실 수 있습니다.  
이제 Git Bash를 열어볼까요?  

### Git Bash[CLI]
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fb6lJ31%2FdJMcajnyktj%2FAAAAAAAAAAAAAAAAAAAAAK_d5Xg7Iiy960xPDlQ_AwF0fycA8PHlC8KbKhlj8Xa2%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DbWYuj%252BpEYio8UnYS%252FsIhCyCvb1U%253D)  
Bash를 쓰기 위해서는 최소한 아래의 명령어에 익숙해지셔야합니다.

| 명령어 | 역할 |
|:---:|:---:|
| cd /c | c 드라이브로 이동 |
| cd src | 현재 위치에서 src라는 폴더로 이동 (없으면 이동X) |
| cd .. | 상위 폴더 위치로 이동하기 |
| ls | 현재 디렉토리의 파일 및 폴더 리스트업 기능 |

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FwEUcE%2FdJMcah4oAdT%2FAAAAAAAAAAAAAAAAAAAAAFaV_8G7qsJCvvkkPxr0Toh2XpMiSD4Gm4MXN8wx_okA%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DDb6uG4j8nnkdW2%252BnhIO2KFD2vNQ%253D)  
1. cd /d - d드라이브로 이동합니다.
2. cd Testdir/ - d드라이브 안 TestDir라는 폴더로 이동합니다.
3. ls - /d/Testdir 폴더 내 정보들을 표기합니다.
4. cd base/ - TestDir내 base라는 폴더로 이동합니다.
5. git clone 복사한 주소  
(https://github.com/Figix/Git-Description-Repository.git)
6. ls - /d/Testdir/base 폴더 내 정보들을 표기합니다. [clone한 폴더 확인]
7. cd Git-Description-Repository/ - base폴더 안에 폴더 이동

(main)이 뜬다면 현재 .git이 있는 폴더에 들어온 것이고,  
현재 위치는 main 브랜치이란 뜻입니다.  

그리고 깃주소를 가져올 때, Ctrl+v가 잘안될 것입니다.  
Ctrl+Insert로 붙여넣기를 해주세요. 
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fc4wPJy%2FdJMcahwzKdC%2FAAAAAAAAAAAAAAAAAAAAACIRcmy0u46v2XOvVMqdad7opchSmJhjLXC4XA3cfwyw%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DMLNMNnDg%252BKePm%252FPwnjiHuNsZvkk%253D)
야무지게 clone한 모습입니다.

아래에서 변경사항을 추가하겠습니다.
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FnAWgp%2FdJMcagYH5cd%2FAAAAAAAAAAAAAAAAAAAAAN2Nxi1K2Lr61Vt89jjKIDAzx4wRqRVTXKoAHEUO3tmN%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DP0W%252BjvRfbI1G5G3rHMBRe8BWsis%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fbcn4a8%2FdJMcad1WmXE%2FAAAAAAAAAAAAAAAAAAAAAMZkcdPrdCrkeKMtVbjI6llvg43KoeKbp7pIf6cduZaw%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DJj8hIatTuaQojbD5uN8hMGA2bfY%253D)
git status - 현재 수정된 사항들 리스트업  
git add 파일명 - 해당 파일을 Stage에 올리기  
git commit - Stage에 올릴 것들을 확정하고, 무엇을 올리는지 설명하는 구간  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FuXnkO%2FdJMcagEra3I%2FAAAAAAAAAAAAAAAAAAAAAPE7EWCHIV_ZTrlqxYXwgseuLE-mWqe57yh1b86D3mdw%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DGLBd71K48u3W6CqVo%252F19m29uti8%253D)
#### 📝 Git 커밋 시 나오는 창 설명 (vim 기준)
Git에서 커밋을 하면 vim 편집기 창이 열립니다.  
i 키를 누르면  
→ Insert 모드로 전환되어  
→ 커밋 메시지를 입력할 수 있습니다.  
(이때 입력하는 글씨가 보통 노란색으로 보입니다)  
커밋 메시지를 모두 작성했다면  
→ Esc 키를 눌러  
→ 입력 모드(Insert)를 종료합니다.  
:wq 명령어를 입력합니다.  
→ Write(저장) Quit(종료) 커밋이 완료됩니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FeIaTXN%2FdJMcahwzKCV%2FAAAAAAAAAAAAAAAAAAAAACr_ZtD47SwemEcBzZAXGTC5Vkk-Z-LhtnI4vtofyEDo%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3D8UpKWRrxW1B7sfZju%252BhwhzQHaWU%253D)  
git status - 커밋이 정상적으로 잘 들어온 것을 확인  
git push - 해당 내용을 원격 저장소에 올리기  

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FnxPcS%2FdJMcacvgYml%2FAAAAAAAAAAAAAAAAAAAAANwqYYYRpX3uUGsQemoPsVkjuHN2QItIwMfXsjzUVa5z%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DQO2G67Dl0SkNuTZb%252FU01U3UjF%252B8%253D)
Png와 README 수정된 내용들이 잘 올라왔습니다.  
  
## Git Fork[GUI]

그러면 이제 의도적으로 Conflict(충돌)가 나오게 한번 수정해볼까요?  
하지만, git bash로 일일히 타이핑해가며 작업하는건 너무 불편합니다.  
CLI로 Git을 다루는건 어느정도 익히셨을테니, GUI인 Fork로 작업을 시작하겠습니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FdXZM5A%2FdJMcadnlLpB%2FAAAAAAAAAAAAAAAAAAAAAEoUOkvDVPG__-Ojc56ETsen4FKLol0MY6np5-xOOzxq%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DShrA2ROw8HCPxyMPY7KB2FZZbH4%253D)
먼저 Fork를 열어주세요.  
File - Open Repository[Ctrl+O]  
.git이 나오는 폴더 구간이 나오는 폴더에서 폴더 선택을 눌러주시면 됩니다.  

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fb9VyAX%2FdJMcabJTLxt%2FAAAAAAAAAAAAAAAAAAAAACyEj6Vy_lmW-qk0iy-4WDosnKar7JFchbZwqRNPnPoC%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DObBfh5vwO%252FqzPSLlRTKEEwWjYzk%253D)
### Git Fork만의 중요 개념들
| 심볼 | 역할 |
|:---:|:---:|
| Git 고양이 마크 | 해당 브랜치가 원격 레파지토리에서의 최신화된 영역 |
| ✅ | 현재 내 시점 |
| 상단의 밑줄 | 현재 브랜치의 헤드명(위치) |

### Git Fork에서 브랜치 나누기
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FoEvoC%2FdJMcai91wQG%2FAAAAAAAAAAAAAAAAAAAAAGwiEe4JD-fEPUR8XqULuSHkwTSvSMKUlW6vYsGrptgp%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DjGWkuQZ0vXfDW8ZNLj6%252BA%252FBq%252FVs%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FVmfOV%2FdJMcadVbe9Y%2FAAAAAAAAAAAAAAAAAAAAAK3_REhKONJqDGF9OgbhXQqJROVAndg8eaOsv1REhibM%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DEmeBE1nEGSr8gpNkXg0nISZEE7w%253D)
| 체크박스 ☐ | 브랜치만 생성하기 |
|:---:|:---:|
| 체크박스 ☑ | 브랜치를 생성한 후, 브랜치 헤드를 해당 위치로 이동하기 |

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FSTQyg%2FdJMcaivqtw2%2FAAAAAAAAAAAAAAAAAAAAALZWyr4ZJfzXSfks1CzOLYuOOode1mUuevNJBkFZrUL8%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3D6eWjrDtDdy4sQRTuYCuHiW4PEI0%253D)
위 방식으로 현재 브랜치를 2개 개설한 상황입니다.  
Readme 수정이라는 로그에서 2개를 개설했습니다.  
해당 로그를 기준으로 userA, userB, Main이라는 브랜치가 생성되었고,  
userB에 ✅가 있으므로 현재 브랜치 명은 userB이며, Readme 수정이 현 위치입니다.

### Git Fork CheckOut
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FVAa1q%2FdJMcafZM7bQ%2FAAAAAAAAAAAAAAAAAAAAADg8oCgvPf8oYcERRcK3oAowcgSzLtyQALTyrgltUK6T%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DrYtPOOn2sdR2qhON845oiKgvWPE%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fwzb8P%2FdJMcafZM7bR%2FAAAAAAAAAAAAAAAAAAAAAE9QYvVIRmXfBflKemMgqZTOLgfmx73ipxKF8LUBsb5f%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3Dxv3Q9ooS110af26YGkypJqobBOs%253D)  
일단 userA로 헤드를 바꾸고[Checkout], 수정작업을 먼저 진행해보겠습니다.  
깃의 헤드를 바꿀려면 여러방법이 존재하는데, 위 두 그림의 방식으로 추천드립니다.  
왼쪽 탭을 활용해 헤드를 바꾸는 방식은 최신 헤드로 이동하는 방식입니다.  

### Git Fork Add, Commit, Push
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FpJ5mA%2FdJMcaa5gIJC%2FAAAAAAAAAAAAAAAAAAAAAOk7fa8faWZgOyZmM12OG1RmEkoIMzOuLfyjEEwGakbf%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DK0%252BlSfPZ0EELj57M7b2gvNwo2x4%253D)  
현재 기존과 다른 피카츄 이미지를 2장을 넣고,  
하나는 기존과 이름을 같게해서 파일의 수정사항을 만든 상황입니다.  

왼쪽탭에 Local Chage에 변경사항이 생겼으니 클릭해서,  
들어가면 위와 같이 창이 변경됩니다.  
Stage 버튼을 통해서 Unstatged에서 Stage로 옮깁니다.  
Stage로 올리고싶지 않은 파일은 날리면 됩니다.  

Delete 키를 통해서 해당 파일을 날릴 수도 있습니다.  
폴더에서 아예 지우는 것이니 조심히 사용하길 바랍니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FCtNXQ%2FdJMcahceZ5N%2FAAAAAAAAAAAAAAAAAAAAAPpF_VLbsYRBdIercL8mOF7OEKodYVVRB8SF95rJXlAd%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3Dy5cNeNVGTub4zRNWRuYwiK63zhY%253D)
Commit의 로그를 작성해 로그명을 정해주세요.  
Commit버튼을 통해 Commit을 해주세요.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FchcENJ%2FdJMcadARftd%2FAAAAAAAAAAAAAAAAAAAAAKf4kcaXUcbm6_oBajGFLqruhW0SMj4EAMejop6keWAk%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DYsw%252F8ADhjXyBEKa098Dwn5642pg%253D)  
userA라는 커밋 로그가 생겼지만, 고양이 마크가 없습니다.  
즉 아직 원격에는 올라간상태가아닙니다.  
이제 Push를 때려볼까요?  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FNGlCj%2FdJMcaaqFvyH%2FAAAAAAAAAAAAAAAAAAAAAFkIjDxcSs-Wv7p5n_Wj7cL3yTdxyBKraqSDvTVk3H7u%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3D4kqnn8qd0BhyCYcRz%252BUc2EpvJZw%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FcsGtTU%2FdJMcaiIXNji%2FAAAAAAAAAAAAAAAAAAAAAApYYr_iE5bhLzxUgr6ncHvUJTxmIcYNrycTbAgtBnmz%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DVAuTpNYU%252BGbHhjLJKxYWPmjK1fk%253D)
깃 고양이 마크가 생겼네요. 이제 해당 로그 영역이 제일 최신화된 영역입니다.  
자 이제 userB 브랜치로 checkout해서 작업을 진행해볼까요?  

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fl1xFB%2FdJMcaaKXLVR%2FAAAAAAAAAAAAAAAAAAAAAIkfqPghyymGKosXH8fEhlaF72lNrzG1_EL9ddicT2Mx%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3Dl5yTWy91CNCO1ClDH4qBMU6k3B8%253D)  
userA에서 피카츄 이미지2개가 있지만, userB는 1개이며,  
Pokémon_Pikachu_art.png라는 파일이 서로 다르게 나오고 있습니다.  

userA의 작업내역이 userB하고는 완전히 분리된 것을 확인했습니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2F2GZum%2FdJMcac23uvz%2FAAAAAAAAAAAAAAAAAAAAAOm_b3MeUIHqaVMbG8HgSw-QZ4fCquAiTKlKrrjPdfVD%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DgIiY8rnIcWjte7JPsXjSg411%252B1A%253D)  
Pokémon_Pikachu_art.png 파일을 변경하고, Commit하고 Push하겠습니다.  

그럼 지금까지의 작업내역을 한번 정리하겠습니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fcm7ulo%2FdJMcaajUmOb%2FAAAAAAAAAAAAAAAAAAAAAIQuCsxkVODjXeRKHSqu6J2cYltlbWROTMIipOIGy2BZ%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DUjIXjWG1oUBrTsnanvynXUKgtyo%253D)  
현재 각 브랜치별로 서로 다른 피카츄 PNG파일들이 있는 모습입니다.  

### Git Fork Merge
이제 작업한 내역들을 main에 올리는 작업을 진행하겠습니다. 먼저 userA부터 넣겠습니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbodSmI%2FdJMcaac8F9Q%2FAAAAAAAAAAAAAAAAAAAAAIGxnTrD5iFwUSTWvMTa7z95bwgcpfR_Z8XnbbDMWY0c%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DzLI%252BZGd0ZwHgx0HxTsUi5rdGzhg%253D)  
Merge는 현재 HEAD에 다른 브랜치의 작업내역을 끌어오는 행위를 말합니다.  
즉 Main 브랜치에서 userA의 작업 내역을 Merge를 해야합니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbcFXy1%2FdJMb99L2l0z%2FAAAAAAAAAAAAAAAAAAAAAGn2wvZz7TGXMVddZilCfwLhbl5oa05g5izvQ0bBxTwl%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DF51l9maG1aLU2J5S3qUE2Fdr%252B%252B8%253D)  
이대로 Merge를 진행해주시면됩니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fd142pB%2FdJMcaa5gJLv%2FAAAAAAAAAAAAAAAAAAAAACQQ--WrY8ePpX4JU4BSoieQbP7wKUGo0zxWho9oaPTP%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DHZFQbkwbXjBiy4rl%252Bn4nmik5KTc%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FEZj8Q%2FdJMcacotpcT%2FAAAAAAAAAAAAAAAAAAAAAHgtI8ftYTmJRgEdodhGdoSmkw9ckhR_ThcDOn7KpM9M%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DIeekxfui3wpnrOrAzTHCEu2NLuw%253D)  
Merge를 하면 꼭 Push를 진행해야합니다.  
그림을 보면 main의 commit된 것같은 내역이 남아있습니다.  
push한 후 모습으로 깃 고양이가 main 브랜치의 최신을 잘보여주네요.  

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FLFLFy%2FdJMcahQRiLX%2FAAAAAAAAAAAAAAAAAAAAAPL3E5N1fZVZiCw2WKkOwdA2W6_sqN8SYbwujU0Dogso%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DJx50tsBlRhychPnOQOAQ2uf%252BvOg%253D)
main 브랜치가 userA와 파일구조가 같게 된 것을 확인했습니다.  
자 이제 userB도 Main쪽으로 Merge해볼까요?  

### Conflict?
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2F16tFV%2FdJMcagLcnoT%2FAAAAAAAAAAAAAAAAAAAAAJ6qeo1UkNRoqQFv5BbLhokjnIefMb12RZH1Qh9taCHI%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DWufzrPq0fDqKre2W5yEj%252F%252Fa4Q%252Fw%253D)
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbFSvgm%2FdJMcad1WoIi%2FAAAAAAAAAAAAAAAAAAAAAORPkQB7tO4yvrq05tuhBCW3qjIQw7mgxD5Ahl4WYioS%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DBpUKnKVM5lYrxJ09ooC4BfvCpn8%253D)
Conflict(충돌)가 생겼습니다. 왜 생겼을까요?  

현재 Pokémon_Pikachu_art.png파일이 작업내역이 겹쳐서 생긴 이슈가 발생된것으로 파악됩니다.  
저는 userB를 선택해서 main브랜치 안에 userB의 거대 피카츄 이미지를 넣겠습니다.  
commit하고 push까지 진행하겠습니다.  
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FVp1xb%2FdJMcadARfOa%2FAAAAAAAAAAAAAAAAAAAAAJ-Kkp3yTu6hTmPrbXIubZhTVqX7Pq6gj2NAWjUHBw8j%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3DXKKswbUoXHFjmU0sKz0jdfMsflg%253D)
정상적으로 main브랜치가 최신화가 되었습니다.

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FyFz17%2FdJMcaflcJaO%2FAAAAAAAAAAAAAAAAAAAAAIWIf7MZznUtBUttBxjB4RQlHQaMIGxuXIWup4Mk1EbT%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1772290799%26allow_ip%3D%26allow_referer%3D%26signature%3Dk%252BplCgsumDH%252Fq5H8B7UatjXMW7M%253D)
자 그럼 지금까지 상황을 그림 정리하면 위와 같습니다.  
이정도만 이해하고 있으면, 여러분도 깃으로 협업할 수 있습니다.  

다음 포스트에는 추가적인 깃 활용 꿀팁들에 대해 다룰 예정입니다.  
Reset과 Stash를 쓸 예정이옵니다.