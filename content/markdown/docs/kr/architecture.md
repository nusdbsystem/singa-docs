# SINGA 아키텍처

---

## 논리적 아키텍처

<img src = "../ images / logical.png"style = "width : 550px"/>
<p> <strong> Fig.1 - 시스템 아키텍처 </strong> </p>

SINGA는 다양한 분산 [트레이닝 프레임워크](frameworks.html) (동기 또는 비동기 트레이닝)을 지원하는 유연한 구조를 가지고 있습니다.
Fig.1. 시스템의 구조를 보여줍니다.
특징으로는 여러 server 그룹과 worker 그룹을 가지고있다.

* **Server 그룹**

  Server 그룹은 모델 매개 변수의 복제본을 가지고 worker 그룹의 요청에 따라 매개 변수의 업데이트를 담당합니다. 인접한 server 그룹들은 매개 변수를 정기적으로 동기화합니다. 일반적으로 하나의 server 그룹은 여러 server로 구성된 각 server는 모델 매개 변수의 분할 된 부분을 담당합니다.

* **Worker 그룹**

  각 worker 그룹은 하나의 server 그룹과 통신합니다. 하나의 worker 그룹은 매개 변수의 기울기 계산을 담당합니다. 또한 분할 된 데이터의 일부에 대해 "완전한"모델 복제본을 트레이닝합니다. 모든 worker 그룹들은 해당 server 그룹들과 비동기 적으로 통신합니다. 그러나 같은 worker 그룹의 worker들은 동기화합니다.

동일 그룹 내에서 worker들의 분산 트레이닝은 많은 다른 방법이 있습니다.

  * **모델 병렬화** 각 worker 그룹에 배정 된 모든 데이터에 대해 매개 변수의 부분 집합을 계산합니다.
  * **데이터 병렬화** 각 worker는 배분 된 데이터의 부분 집합에 대해 모든 매개 변수를 계산합니다.
  * [**하이브리드 병렬화**](hybrid.html) 위의 방법을 조합한 하이브리드 병렬화를 지원합니다.


## 임플리멘테이션

SINGA에서 servers와 workers는 다른 스레드에서 움직이는 실행 유닛입니다.

In SINGA, servers and workers are execution units running in separate threads.
그들은 [messages](communication.html)를 이용하여 통신합니다.
각 프로세스는 로컬 messages를 수집하고 그것을 지원하는 수신기에 전송하는 stub으로 메인 스레드를 실행합니다.

각 server 그룹과 worker 그룹은 "전체"모델 복제이다 *ParamShard* 개체를 유지합니다.
만약 workers와 servers 동일한 프로세스에서 달리는한다면,
그 *ParamShard* (파티션)은 메모리 공간을 공유하도록 설정됩니다.
이 경우 다른 실행 유닛 사이를 오가는 messages는 통신 비용을 줄이기 위해 데이터의 포인터 만 포함됩니다.
프로세스 간 통신의 경우와는 달리 messsages는 매개 변수의 값을 포함합니다.
