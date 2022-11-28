# vos-kubeflow

1) Install
- **순서**: 
> - install 폴더에 shell 스크립트를 순서대로 실행한다.
> - kubeflow manifest(https://github.com/kubeflow/manifests)에 들어가서 clone 후 kubeflow 설치를 진행한다.

2) Create User
- **순서**:
> - user 폴더에 profile.yaml 파일을 자기 자신에 맞춰서 변경한다.
> - 참고 페이지: https://docs.containerplatform.hpe.com/54/reference/kubernetes/kubernetes-administrator/kubeflow/Manually_Creating_a_Profile_Namespace_for_a_User.html
> - manifests 폴더에서 config-map.yaml 파일에 계정을 추가해준다 ~/manifests/common/dex/base/config-map.yaml
> - 다시 dex를 apply.
