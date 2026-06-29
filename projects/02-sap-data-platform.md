# SAP 연계 데이터 통합 플랫폼 구축

## Overview

RFC/EAI 중심 레거시 연계 구조를 API 기반 통합 플랫폼으로 전환한 프로젝트입니다.  
대용량 SAP 데이터 이관, 데이터 검증, 모니터링, 배치 등록 기능을 제공하는 관리자 시스템을 구축했습니다.

- **기간:** 2025.08 ~ 2026.02
- **참여 인원:** 4명
- **역할:** 백엔드 API 개발, 대용량 데이터 처리 구조 개선, 배치 기능 구현, 인증/인가 구현
- **사용기술:** Java, Spring Boot, Spring Security, JWT, Quartz, Vue.js, MS-SQL, SAP/OData, Dynamic DataSource, Windows Server

## My Role

- Spring Boot 기반 API 서버 개발
- OData 기반 SAP 데이터 이관 프로세스 구현
- Paging/Chunk 기반 대용량 데이터 처리 구조 개선
- Thread Pool + Work Queue 기반 배치 동시성 제어
- Dynamic DataSource 기반 다중 DB 연동 구현
- Spring Security + JWT 기반 인증/인가 구현
- Quartz 기반 데이터 추출 배치 기능 구현

## Problem

SAP 데이터 이관 과정에서 대용량 데이터 처리와 배치 안정성이 핵심 문제였습니다.  
데이터를 한 번에 로딩할 경우 JVM 메모리 한계와 GC 부하가 발생했고, 다수 배치가 동시에 실행되면서 프로세스 증가와 실패가 발생했습니다. 또한 실패 지점을 추적하기 어려워 운영 재처리 비용이 커졌습니다.

주요 문제는 다음과 같았습니다.

- 대용량 데이터 추출 시 JVM 메모리 한계 발생
- GC 부하 증가로 인한 처리 안정성 저하
- 다수 배치 실행 시 프로세스 증가와 실패 발생
- 대량 데이터 처리 중 실패 위치 추적 어려움
- 여러 DB와 SAP 데이터를 함께 다루어야 하는 확장성 문제

## Solution

### 1. Paging/Chunk 처리

대용량 데이터를 한 번에 로딩하지 않고 Paging/Chunk 단위로 분할 처리했습니다.  
이를 통해 Heap 사용량과 GC 부하를 줄이고, 처리 단위를 명확히 나누었습니다.

### 2. Thread Pool + Work Queue 적용

다수 배치가 동시에 실행되며 발생하던 프로세스 증가와 실패 문제를 제어하기 위해 Thread Pool과 Work Queue를 적용했습니다.  
동시 실행 수를 제한하고 초과 작업은 대기열에서 관리하도록 구성했습니다.

### 3. 실패 지점 추적 가능 구조

Chunk 단위로 처리 결과를 남길 수 있도록 구성해 실패 위치를 추적하고 재처리할 수 있는 기반을 마련했습니다.

### 4. Dynamic DataSource와 인증/인가

Dynamic DataSource 기반으로 다중 DB 연동 구조를 구현했고, Spring Security + JWT 기반 인증/인가 체계를 구축했습니다.

## Result

- 배치 실패율 0%로 개선
- 3000만 건 규모 데이터 추출 속도 2시간 -> 1시간 20분으로 단축
- Paging/Chunk 처리로 JVM 메모리 사용량과 GC 부하 완화
- Thread Pool + Work Queue로 배치 동시 실행 안정화
- Dynamic DataSource 기반 다중 DB 연동 구조 구축
- Spring Security + JWT 기반 서비스별 회원 및 권한 관리 체계 구축

## What I Learned

대용량 데이터 처리는 단순히 빠르게 처리하는 것보다 실패 가능성을 줄이고, 실패했을 때 어디서 문제가 발생했는지 추적할 수 있어야 운영 가능한 구조가 된다는 점을 배웠습니다.

## Interview Questions

- Paging과 Chunk 처리 기준은 어떻게 잡았나요?
- Thread Pool 크기와 Queue 정책은 어떻게 결정했나요?
- Work Queue가 가득 차는 상황은 어떻게 처리했나요?
- 배치 실패율 0%는 어떤 기준으로 측정했나요?
- Dynamic DataSource를 적용한 이유는 무엇인가요?

