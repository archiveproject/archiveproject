# archiveproject

## Queue Service

  * PGMQ - Postgres 기반의 SQS 대체제 (https://github.com/tembo-io/pgmq)
    * AWS SQS 및 RSMQ와 비슷한 경량 메시지 큐를 Postgres 기반으로 구현한 오픈소스
    * 백그라운드 워커 및 외부 의존성 없이, Postgres 확장으로만 구성
    * 제한시간 내에 컨슈머에게 '정확히 한번' 메시지 전달 보장
    * 메시지는 명시적으로 제거될 때 까지 대기열에 남아 있음
    * 메시지는 삭제 대신 아카이빙 하여 장기 보관 및 리플레이 가능
    * AWS SQS 및 RSMQ와 API 호환


## Reverse Proxy

  * Piko - Ngrok의 오픈소스 대체제 (https://github.com/andydunstall/piko)
    * 외부 네트워크로 터널링하는 리버스 프록시
    * 프로덕션 수준의 트래픽을 처리하며, 호스팅(특히 Kubernetes에서)이 간단하도록 설계됨
    * 고객 네트워크, BYOC(Bring Your Own Cloud) 서비스의 서비스를 노출하거나 IoT 디바이스에 연결할 수 있음
    * 내결함성, 확장성, 무중단 배포를 위해 노드 클러스터로 호스팅될 수 있음
    * ![pico](./images/overview_piko.png)
    * [Docker-compose.yaml](./example/docker-compose-pico.yaml)

## Infrastructure as Code:

  * OpenTofu - Terraform의 오픈소스 대체제 ( https://github.com/opentofu/opentofu )
    * 2023년에 Hashicorp는 Terraform과 다른 제품들에 대해 이전에 사용하던 MPL 2.0 대신 더 제한적인 BSL 1.1 라이선스를 채택하기로 결정함
    * 이로 인해 Linux Foundation에서 신속하게 OpenTofu라는 포크가 만들어짐
    * 2024년 3월에 출시된 OpenTofu 1.7 버전은 엔터프라이즈 수준에서 사용 가능한 첫 번째 버전으로 널리 여겨짐
    * Oracle E-Business Suite (EBS) Cloud Manager의 최신 업데이트인 24.1.1.1 버전에서 Terraform 대신 오픈소스 포크인 OpenTofu를 사용하게 됨 ( https://www.thestack.technology/oracle-dumps-terraform-for-opentofu/ )
    * OpenTofu는 기본적으로 Terraform의 친숙한 대체제임
    * 복잡한 EBS 환경을 클라우드로 이전하려는 사람들에게는 사소한 구현 세부 사항이지만, 포크 버전이 이미 주요 기업에서 사용할 만큼 견고하다는 신호를 보내고 있음






