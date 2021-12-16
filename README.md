# <초기 작업>
 github에 블로그 제작을 위한 Repository 생성 (Repo 이름: .github.io) 
 생성 이후 Romote Repository 주소를 복사하고 명령 프로프트에서 git clone을 통해 Local-Remote Repository 연동
 (git clone <repo_name> → git clone https://github.com/zia2054/zia2054.github.io.git blog)

# <파일 생성 후 commit & push, github page 연동> 
블로그 제작을 위한 BLOG 폴더 생성 테스트로 index.html생성 후 git add로 파일 추가 (git add index.html) 
html 파일을 github에 commit (git commit -m "add: index.html") branch의 이름을 main으로 변경 (git branch -M main) 이후 명령 프롬프트를 통해 git push로 원격 저장소에 반영 (git push origin main) =>이때 PAT을 사용하라고 오류가 뜬다. 
따라서 github의 설정에 들어가 PAT를 생성하여 git push를 사용할 수 있게 해준다.

# <Jekyll 설치> 
https://jekyllrb-ko.github.io/docs/installation/ 위 사이트에서 Ruby+Devkit 선택 후 설치 rubyinstaller를 통해 설치 후 Ruby 프롬프트를 사용하여 jekyll 설치 (gem install jekyll bundler) 
생성해둔 BLOG폴더에 jekyll을 설치 (jekyll new . --force) jekyll serve 실행 하여 잘 표시되는지 확인(bundle exec jekyll serve) → 출력된 사이트 접속 시 사이트 확인 가능 ★_config.yml을 통해 속성 변경 가능!

# <블로그 생성>
BLOG파일에 생성된 jekyll을 깃허브에 추가 (git add *) 추가할 파일들을 commit (git commit -m "add: jekyll on repository") 
로컬 저장소의 commit정보를 원격 저장소에 반영 (git push origin main) → github에서 생성한 readme.md파일 때문에 충돌이 일어나 오류 발생, 꼭 지우고 git push 실행! (해당 오류가 발생했을 시 readme.md파일 삭제 후 git pull origin main --allow-unrelated-histories 코드 작성 후 push 진행)
zia2054.github.io 사이트에 접속하면 블로그 확인 가능

# <블로그 사용 방법> 
BLOG의 _post 폴더에 Markdown형식을 통해 내용 작성 작성 이후 추가된 파일을 꼭 add, commit, push 해야함!!! 
테마는 원하는 테마 선택 후 jekyll파일이 담겨있는 폴더에 저장 후 적용
파일 add후 warning: LF will be replaced by CRLF 이런 문구가 뜬다면 got config --global core.autocrlf true 코드를 사용하여 해결