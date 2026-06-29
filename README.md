[README.md](https://github.com/user-attachments/files/29465737/README.md)
# 우종국 | Backend Portfolio

Java/Spring 기반 백엔드 개발자로 서비스 안정성과 운영 효율을 함께 고민해온 개발자입니다.  
대용량 데이터 처리, 시스템 연계, MSA 구조 설계, CI/CD, 모니터링 환경 구성 경험을 바탕으로 기능 구현 이후의 운영 안정성과 확장성까지 고려하는 개발자로 성장하고 있습니다.

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

## Architecture

각 프로젝트 문서 안에 기술 아이콘 기반 아키텍처와 처리 흐름을 함께 정리했습니다.  
핵심 프로젝트는 Java/Spring 기반 서비스 구조, 배치 처리, SAP 연계, CI/CD, 모니터링 흐름을 중심으로 설명하고, 이전 C#/.NET 프로젝트는 장비 통신과 운영 안정화 경험을 보조적으로 정리했습니다.

## Proficiency

- 운영 안정성과 확장성을 고려한 백엔드 API 및 배치 기능 개발
- 서비스 경계, 데이터 흐름, 시스템 연계를 고려한 구조 설계
- SQL/Stored Procedure 기반 대용량 데이터 처리 및 성능 개선
- Jenkins 기반 CI/CD와 Prometheus, Grafana 기반 모니터링 환경 구성
- 로그와 지표를 활용한 장애 원인 분석 및 운영 이슈 개선

## About Me

저는 단순히 기능을 구현하는 것보다, 이후 변경과 확장 과정에서 문제가 생기지 않는 구조인지 고민하며 개발해왔습니다.

신규 서비스 개발 과정에서 MSA 구조 설계, 서비스 이중화, Jenkins 기반 CI/CD, Prometheus/Grafana 모니터링 환경을 구성하며 운영 안정성을 높이는 경험을 했습니다. 또한 SAP 연계, 대용량 데이터 처리, 배치 성능 개선, IoT 데이터 처리 등 여러 시스템이 연결되는 환경에서 데이터 흐름과 장애 지점을 함께 고려하며 개발했습니다.

요구사항을 구현할 때도 전체 서비스 흐름과 운영 환경을 함께 살피고, 안정성과 유연성을 높일 수 있는 개선 지점을 찾는 데 집중합니다.

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

## Trouble Shooting

### 대용량 데이터 처리 중 JVM 메모리 한계 개선

**Problem**  
SAP 데이터 대량 추출 과정에서 데이터를 한 번에 처리하며 JVM 메모리 사용량이 증가했고, GC 부하와 장시간 배치 실패 문제가 발생했습니다.

**Solution**  
전체 데이터를 한 번에 적재하지 않고 Paging/Chunk 단위로 분리해 처리했습니다. 또한 Thread Pool과 Work Queue를 적용해 동시에 실행되는 작업 수를 제어하고, 실패 지점을 추적할 수 있도록 처리 단위별 로그 구조를 개선했습니다.

**Result**  
배치 실패율을 0%로 개선했고, 300만 건 데이터 추출 시간을 2시간에서 1시간 20분으로 단축했습니다.

### 서비스 이중화 환경에서 스케줄러 중복 실행 문제 해결

**Problem**  
서비스 이중화 이후 동일한 스케줄러가 여러 인스턴스에서 중복 실행될 수 있는 문제가 있었습니다.

**Solution**  
Quartz Clustering을 적용해 스케줄러 실행 상태를 공유하고, 중복 실행을 방지할 수 있는 구조로 개선했습니다.

**Result**  
이중화 환경에서도 안정적으로 배치 작업을 실행할 수 있었고, 운영 중 중복 처리로 인한 데이터 정합성 문제를 예방했습니다.

### 운영 상태 추적을 위한 모니터링 환경 구성

**Problem**  
서비스 사용 중 현재 서버 상태, 메모리 사용량, 과거 리소스 이력을 확인하기 어려워 장애 징후를 빠르게 파악하기 힘들었습니다.

**Solution**  
Prometheus와 Grafana를 활용해 주요 리소스 지표와 서비스 상태를 확인할 수 있는 모니터링 환경을 구성했습니다.

**Result**  
메모리 누수와 서버 리소스 이상 징후를 추적할 수 있는 기반을 마련했고, 운영 중 문제 원인 분석 속도를 높였습니다.

## Portfolio Direction

이 포트폴리오는 회사 내부 코드나 민감한 정보를 공개하지 않고, 프로젝트에서 마주한 기술적 문제와 해결 과정을 중심으로 정리했습니다.  
프로젝트명과 일부 도메인 정보는 보안상 일반화했으며, 공개 가능한 범위에서 구조, 의사결정, 결과를 설명합니다.

## Links

- PDF Portfolio: `우종국_백엔드_포트폴리오_개정.pdf`
- Resume: 별도 제출
