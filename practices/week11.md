#Week 11 실습
## 오늘 한 것
- PyInstaller 설치 및 빌드
- resource_path() 함수 추가
- --add-data 옵션으로 에셋 포함
- .exe 실행 확인

## 빌드 명령어
resource_path
import sys, os
def resource_path(relative_path):
    """개발 중과 빌드 후 모두 동작하는 경로 반환"""
    if hasattr(sys, '_MEIPASS'):
        base = sys._MEIPASS
    else:
        base = os.path.dirname(__file__)
    return os.path.join(base, relative_path)

  ## AI 활용 내역
  경로 지정이 잘못되어있어서 그 부분을 수정해줌

  ## resource_path() 를 써야 하는 이유
resource_path()를 사용하는 이유는 파일 경로를 안정적으로 불러오기 위해서이다.
프로그램을 실행하는 위치가 바뀌거나, exe 파일로 변환했을 때도 이미지나 사운드 파일의 경로가 깨지지 않도록 도와준다.
특히 상대경로를 사용할 때 발생할 수 있는 오류를 줄여주기 때문에, 다양한 환경에서 동일하게 프로그램이 실행되도록 하기 위해 사용한다.
