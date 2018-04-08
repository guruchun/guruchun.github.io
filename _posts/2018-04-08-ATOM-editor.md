## linux에서 Atom Editor 사용하기

개발환경은 ubuntu이다.  
linux라면 vim을 쓰는게 정석이겠지만, eclipse만 쓰다가 text editor를 쓰려면 많이 불편하다. vim에 익숙해질 때까지는 다른 editor를 찾아봐야 한다. atom이 좋아 보인다.  
나중에 electron으로 개발할 것도 있기 때문에 electron의 결과물을 미리 경험해 보기에도 좋겠다.

### atom 설치
ubuntu software center에서 검색해서 설치하더니 중간에 멈춘다. 이유는 모르겠다.  
atom.io에서 deb 패키지를 다운로드 받아서 설치했다.

### atom에서 python coding하기
settings > install 에서 패키지를 몇개 찾아서 설치했다.
* 'script', 'autocomplete-python', 'terminal-plus'

구글링 해보니 이거면 충분한 것 같다.

### python 설치
python이 혹시 설치되어 있을까?  
`python --version`으로 확인해보니 2.7.12 가 설치되어 있다.  
`python3 --version`으로 확인해보니 3.5.2 가 설치되어 있다.

최신 python3 버전인 3.6.x를 사용하려면 개인 repository를 추가해야 설치할 수 있다.  
`sudo add-apt-repository ppa:jonathonf/python-3.6`  
굳이 3.6을 설치할 필요는 없을 것 같다. 기본 설치된 3.5 버전을 사용하기로 한다.
