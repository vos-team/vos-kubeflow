# vos-kubeflow

1) Install
- **순서**: 
> - install 폴더에 shell 스크립트를 순서대로 실행한다.
> - kubeflow manifest(https://github.com/kubeflow/manifests)에 들어가서 clone 후 kubeflow 설치를 진행한다.
> - https 접근을 위해 gateway와 certificate을 적용해준다.
> - 크롬이 안되는경우 chrome://flags/로 접속해서 Black insecure private network requets를 enabled해준다.

2) Create User
- **순서**:
> - user 폴더에 profile.yaml 파일을 자기 자신에 맞춰서 변경한다.
> - 참고 페이지: https://docs.containerplatform.hpe.com/54/reference/kubernetes/kubernetes-administrator/kubeflow/Manually_Creating_a_Profile_Namespace_for_a_User.html
> - manifests 폴더에서 config-map.yaml 파일에 계정을 추가해준다 ~/manifests/common/dex/base/config-map.yaml
> - dex deployment를 삭제하고 다시 dex를 적용해준다.

3) Jupyter Notebook
> - kubeflow에서 jupyter notebook은 jovyan 계정으로 설정되어있어서 sudo 명령어가 불가능하다.
> - 그렇기때문에 custom 이미지를 활용해서 작업을 진행한다.

4) Kfp (kubeflow pipeline)
> - 기존에는 인증이 진행되지않아서 인증을 우회하는 방법을 적용해줘야한다.
> - AuthorizationPolicy를 적용 후 EnvoyFilter를 적용해준다.
