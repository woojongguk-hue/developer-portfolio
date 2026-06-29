[README.md](https://github.com/user-attachments/files/29465737/README.md)
# 우종국 | Backend Portfolio

Java/Spring 기반 백엔드 개발자로 서비스 안정성과 운영 효율을 함께 고민해온 개발자입니다.  
대용량 데이터 처리, 시스템 연계, MSA 구조 설계, CI/CD, 모니터링 환경 구성 경험을 바탕으로 기능 구현 이후의 운영 안정성과 확장성까지 고려하는 개발자로 성장하고 있습니다.

## Proficiency

- 운영 안정성과 확장성을 고려한 백엔드 API 및 배치 기능 개발
- 서비스 경계, 데이터 흐름, 시스템 연계를 고려한 구조 설계
- SQL/Stored Procedure 기반 대용량 데이터 처리 및 성능 개선
- Jenkins 기반 CI/CD와 Prometheus, Grafana 기반 모니터링 환경 구성
- 로그와 지표를 활용한 장애 원인 분석 및 운영 이슈 개선
  
## Skills

| Category | Skills |
|---|---|
| Backend | Java, Spring Boot, Spring Cloud, Spring Security, JWT, REST API, Quartz |
| Database | MS-SQL, MySQL, SQLite, SQL, Stored Procedure, Query Tuning |
| Data / Integration | SAP JCo Connector, SAP/OData, RFC, ETL, Kafka, MQTT, Modbus TCP/IP |
| DevOps / Monitoring | Jenkins, CI/CD, Prometheus, Grafana, Ubuntu, CentOS, Windows Server |
| Frontend / Client | Vue.js, WinForm |

## Projects

| Project | Focus |
|---|---|
| [데이터 연계 솔루션 구축](projects/01-data-integration-solution.md) | MSA, 서비스 이중화, CI/CD, 모니터링, SAP JCo, ETL |
| [SAP 연계 데이터 통합 플랫폼 구축](projects/02-sap-data-platform.md) | 대용량 데이터 이관, Paging/Chunk, Thread Pool, Quartz, 인증/인가 |
| [사용자 맞춤형 온수난방 시스템 개발](projects/03-iot-heating-system.md) | IoT, MQTT, Kafka, FOTA, 실시간 이벤트, 관리자 대시보드 |
| [캐스케이드 제어·모니터링 시스템 고도화](projects/04-modbus-monitoring.md) | Modbus TCP/IP, 장비 통신, 장애 분석, 원격 모니터링 |

## Project Highlights

### 데이터 연계 솔루션 구축

신규 데이터 연계 솔루션을 구축하며 MSA 기반 서비스 구조, 서비스 이중화, Jenkins 기반 CI/CD, Prometheus/Grafana 모니터링 환경을 구성했습니다. 운영 중 서비스 상태와 리소스 문제를 추적할 수 있는 기반을 마련하고, SAP ECC RFC 및 S/4HANA DB 연계 ETL 프로세스를 구현했습니다.

- 50만 건 처리 시간 4분 30초에서 1분 30초로 단축
- 서비스 이중화와 Gateway 구성을 통한 단일 장애 지점 완화
- Quartz Clustering 기반 스케줄러 중복 실행 문제 해결
- Jenkins 기반 CI/CD 구성으로 배포 관리 효율 개선

### SAP 연계 데이터 통합 플랫폼 구축

RFC/EAI 중심의 레거시 연계 구조를 API 기반 통합 플랫폼으로 전환하는 프로젝트에 참여했습니다. 대용량 SAP 데이터 이관, 데이터 검증, 모니터링, 배치 등록 기능을 제공하는 관리자 시스템을 구축했습니다.

- 300만 건 규모 데이터 추출 속도 2시간에서 1시간 20분으로 단축
- Paging/Chunk 처리로 JVM 메모리 사용량과 GC 부하 완화
- Thread Pool과 Work Queue 기반 배치 동시성 제어
- Spring Security와 JWT 기반 인증/인가 체계 구현

### 사용자 맞춤형 온수난방 시스템 개발

기존 온수난방 제어 시스템과 연동되는 Spring 기반 웹 서비스와 관리자 대시보드를 개발했습니다. IoT 기기 통신, FOTA, 실시간 이벤트 전달, 데이터 처리 파이프라인을 구현했습니다.

- MQTT 기반 기기 통신 기능 구현
- Kafka 기반 실시간 데이터 처리 파이프라인 구축
- FOTA 기반 펌웨어 배포 구조 구현
- Firebase 기반 앱 알림 기능 구현

### 캐스케이드 제어·모니터링 시스템 고도화

기기와 시스템 간 통신 불안정 문제를 개선하고, 원격 모니터링과 네트워크 제어 환경을 구축한 프로젝트입니다. 통신 구간별 예외 처리와 로그 시스템을 구성해 장애 원인 파악 시간을 줄였습니다.

- Modbus TCP/IP 기반 통신 구조 구현
- 서버/로컬 이원화 프로그램을 단일 애플리케이션으로 통합
- 통신 구간별 로그를 통한 장애 분석 기반 마련
- 원격 모니터링 및 네트워크 제어 환경 구축


