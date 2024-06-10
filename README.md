# archiveproject

## Queue Service

  * **PGMQ - Postgres 기반의 SQS 대체제** (https://github.com/tembo-io/pgmq)
    * AWS SQS 및 RSMQ와 비슷한 경량 메시지 큐를 Postgres 기반으로 구현한 오픈소스
    * 백그라운드 워커 및 외부 의존성 없이, Postgres 확장으로만 구성
    * 제한시간 내에 컨슈머에게 '정확히 한번' 메시지 전달 보장
    * 메시지는 명시적으로 제거될 때 까지 대기열에 남아 있음
    * 메시지는 삭제 대신 아카이빙 하여 장기 보관 및 리플레이 가능
    * AWS SQS 및 RSMQ와 API 호환


## Reverse Proxy

  * **Piko - Ngrok의 오픈소스 대체제** (https://github.com/andydunstall/piko)
    * 외부 네트워크로 터널링하는 리버스 프록시
    * 프로덕션 수준의 트래픽을 처리하며, 호스팅(특히 Kubernetes에서)이 간단하도록 설계됨
    * 고객 네트워크, BYOC(Bring Your Own Cloud) 서비스의 서비스를 노출하거나 IoT 디바이스에 연결할 수 있음
    * 내결함성, 확장성, 무중단 배포를 위해 노드 클러스터로 호스팅될 수 있음
    * ![pico](./images/overview_piko.png)
    * [Docker-compose.yaml](./example/docker-compose-pico.yaml)

## Infrastructure as Code:

  * **OpenTofu - Terraform의 오픈소스 대체제** ( https://github.com/opentofu/opentofu )
    * 2023년에 Hashicorp는 Terraform과 다른 제품들에 대해 이전에 사용하던 MPL 2.0 대신 더 제한적인 BSL 1.1 라이선스를 채택하기로 결정함
    * 이로 인해 Linux Foundation에서 신속하게 OpenTofu라는 포크가 만들어짐
    * 2024년 3월에 출시된 OpenTofu 1.7 버전은 엔터프라이즈 수준에서 사용 가능한 첫 번째 버전으로 널리 여겨짐
    * Oracle E-Business Suite (EBS) Cloud Manager의 최신 업데이트인 24.1.1.1 버전에서 Terraform 대신 오픈소스 포크인 OpenTofu를 사용하게 됨 ( https://www.thestack.technology/oracle-dumps-terraform-for-opentofu/ )
    * OpenTofu는 기본적으로 Terraform의 친숙한 대체제임
    * 복잡한 EBS 환경을 클라우드로 이전하려는 사람들에게는 사소한 구현 세부 사항이지만, 포크 버전이 이미 주요 기업에서 사용할 만큼 견고하다는 신호를 보내고 있음

## BI


  * **Quary - 엔지니어를 위한 오픈소스 BI** (https://github.com/quarylabs/quary)
    * "Engineer-oriented BI and analytics"
      * 엔지니어들에게 기존 셀프-서브 BI 도구들은 로컬 개발도구를 포기하게 만듦(Copilot, Git등)
      * Quary는 표준 소프트웨어 관행(버전 관리, 테스트, 리팩토링, CI/CD, 오픈 소스 등)을 BI 및 분석 워크플로우에 도입하여 이러한 문제점을 해결
    * 다양한 DB에 접속 지원 : Supabase, Redshift, Bigquery, PostgreSQL, Snowflake, DUckDB, SQLite
    * 테이블을 변환, 구성 및 문서화하기 위한 SQL 쿼리 작성
    * 차트, 대시보드 및 보고서 만들기(개발 중)
    * 버전 관리를 통해 반복적으로 테스트, 협업 및 리팩터링하기
    * 정리되고 문서화된 모델을 데이터베이스에 다시 배포
    * 지원하는 애셋 타입  
    * Source: 데이터베이스 테이블, 플랫 파일 또는 API(DuckDB 사용)와 같이 Quary에 공급되는 외부 데이터 소스를 정의
      * Model: SQL을 사용해 소스의 원시 데이터를 분석 가능한 데이터 세트로 변환하여 엔지니어가 복잡한 쿼리를 원자적 구성 요소로 분할 가능
      * Chart: SQL을 사용하여 데이터의 시각적 표현 생성
      * Dashboard(WIP): 여러 차트를 단일 보기로 결합하여 엔지니어가 한 곳에서 데이터를 모니터링하고 분석
      * Report(WIP): 자세한 보고서를 만들어 인사이트와 결과를 팀 또는 이해관계자와 공유
    * ![img](https://github.com/quarylabs/quary/raw/main/assets/readme_demo.gif)
   
## Data Pipelines

  * **Koheesio - Nike의 데이터 파이프라인 구축용 프레임워크 오픈소스** ([github.com/Nike-Inc](https://github.com/Nike-Inc/koheesio))
    * 효율적인 데이터 파이프라인을 구축하기 위한 Python 프레임워크
    * 모듈화와 협업을 촉진하여 간단하고 재사용 가능한 구성 요소로 복잡한 파이프라인을 만들 수 있게 함
    * 여러 데이터 처리 라이브러리나 프레임워크와 원활하게 작동하도록 설계됨
    * Pydantic을 사용하여 강력한 타입 검사, 데이터 유효성 검사 및 설정 관리를 제공함
    * 잘 테스트된 코드와 풍부한 기능 세트를 통해 예측 가능한 파이프라인 실행을 보장
    * **Koheesio와 다른 라이브러리의 차별점**
      * 데이터 파이프라인, PySpark 통합, 데이터 변환, ETL 작업, 데이터 유효성 검사 및 대규모 데이터 처리에 특화된 설계
      * 모든 종류의 데이터 처리 작업을 위한 Reader, Writer 및 Transformation 기능 제공
      * 데이터 엔지니어링 커뮤니티 내에서 협업과 혁신을 장려함
    * **Koheesio 핵심 구성 요소**
      * Step: Koheesio의 기본 작업 단위로, 데이터 파이프라인에서 단일 작업을 나타냄. 입력을 받아 출력을 생성함
      * Context: 작업의 환경을 설정하는 구성 클래스. 작업 간 변수를 공유하고 환경에 따라 작업의 동작을 조정할 수 있음
      * Logger: 다양한 수준에서 메시지를 기록하는 클래스
    * ![Koheesio](./images/overview_koheesio.png)

        




