# SWE_2021_41_2024_2_week_6

---
## Week 4 Assignment
- Link of my repository: [Link](https://github.com/dpl9753/SWE_2021_41_2024_2_week_4)
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

---
## Week 5 Assignment

> ```bash
> docker exec ossp-container cat /etc/os-release
> ```
> - explanation

> ```bash
> docker exec ossp-container git --version
> ```
> - explanation

> ```bash
> docker exec ossp-container python3 --version
> ```
> - explanation

> ```bash
> docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
> ```
> - explanation
