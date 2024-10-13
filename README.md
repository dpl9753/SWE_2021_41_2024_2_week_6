# SWE_2021_41_2024_2_week_6

---
## Week 4 Assignment
- Link of my repository: [Link](https://github.com/dpl9753/SWE_2021_41_2024_2_week_4)
- Happy Number

  - A happy number is a number defined by the following process:

    - Starting with any positive integer, replace the number by the sum of the squares of its digits.
    - Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
    - Those numbers for which this process ends in 1 are happy.
  - Return true if n is a happy number, and false if not.
```python
def isHappy(n):
  decomposition = list(map(int, list(str(n))))
  square = list(map(lambda x: x**2, decomposition))
  if sum(square) == 1:
    return True
  if sum(square) < 7: #7은 True, 6 이하는 모두 False
    return False
  return isHappy(sum(square))

#Testcase 1
print(isHappy(19))
#Testcase 2
print(isHappy(2))
```
- Description
  - isHappy() 함수는 입력된 숫자 n이 Happy Number인지 아닌지 확인
  - 주어진 숫자 n에 대해 각 자릿수의 제곱값을 sum하여 happy number인지 아닌지 재귀적으로 확인
  - 7보다 작은 경우, 1 이외에는 모두 Happy Number가 아니므로 False를 반환
  - 최종적으로 1이 되면 Happy Number이므로 True를 반환
  - 마지막에는 Testcase를 확인하여 값이 올바르게 출력되는지 확인  
- Result
  ```
  True
  False
  ```
---
## Week 5 Assignment

> ```bash
> docker exec ossp-container cat /etc/os-release
> ```
> - explanation
>   - 실행 중인 Docker container에서 cat 명령어를 실행
>   - `docker exec`: 실행 중인 container 안에서 명령어를 실행
>   - `ossp-container`: 실행 중인 container의 이름으로, 이 container에서 명령어를 실행
>   - `cat /etc/os-release`: `/ect/os-release` 파일의 내용을 출력
> - Result
>   - Ubuntu에 대한 정보
>   ```
>   PRETTY_NAME="Ubuntu 24.04.1 LTS"
>   NAME="Ubuntu"
>   VERSION_ID="24.04"
>   VERSION_CODENAME=noble
>   ID=ubuntu
>   ID_LIKE=debian
>   HOME_URL="https://www.ubuntu.com/"
>   SUPPORT_URL="https://help.ubuntu.com/"
>   BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu"
>   PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
>   UBUNTU_CODENAME=noble
>   LOGO=ubuntu-logo
>   ```

> ```bash
> docker exec ossp-container git --version
> ```
> - explanation
>   - 실행 중인 Docker container에서 git의 version을 확인하기 위한 명령어를 실행
>   - `docker exec`: 실행 중인 container 안에서 명령어를 실행
>   - `ossp-container`: 실행 중인 container의 이름으로, 이 container에서 명령어를 실행
>   - `git --version`: git이 설치되어 있다면 해당 version을 출력
> - Result
>   - 설치된 git의 version은 2.43.0
>   ```
>   git version 2.43.0
>   ```

> ```bash
> docker exec ossp-container python3 --version
> ```
> - explanation
>   - 실행 중인 Docker container에서 python의 version을 확인하기 위한 명령어를 실행
>   - `docker exec`: 실행 중인 container 안에서 명령어를 실행
>   - `ossp-container`: 실행 중인 container의 이름으로, 이 container에서 명령어를 실행
>   - `python3 --version`: Python이 설치되어 있다면 해당 version을 출력
> - Result
>   - 설치된 Python의 version은 3.12.3
>   ```
>   Python 3.12.3
>   ```

> ```bash
> docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
> ```
> - explanation
>   - 실행 중인 container에 대해 host system과 container간 directory 연결 정보를 출력 
>   - `docker inspect`: container의 상세 정보를 출력하는 데 사용
>   - `--format="{{ .HostConfig.Binds }}"`: 원하는 정보만 필터링하여 출력, 여기서는 bind mounts 정보를 의미
>   - `ossp-container`: `inspect` 명령을 실행할 container의 이름 
> - Result
>   - host의 ./ossp_host_dir directory가 container의 /mnt/ossp_container_dir로 mount
>   ```
>   [./ossp_host_dir:/mnt/ossp_container_dir]
>   ```
