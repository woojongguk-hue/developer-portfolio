# SAP 연계 데이터 통합 플랫폼 구축

## Overview

RFC/EAI 중심 레거시 연계 구조를 API 기반 통합 플랫폼으로 전환한 프로젝트입니다.  
대용량 SAP 데이터 이관, 데이터 검증, 모니터링, 배치 등록 기능을 제공하는 관리자 시스템을 구축했습니다.

- **기간:** 2025.08 ~ 2026.02
- **참여 인원:** 4명
- **역할:** 백엔드 API 개발, 대용량 데이터 처리 구조 개선, 배치 기능 구현, 인증/인가 구현
- **사용기술:** Java, Spring Boot, Spring Security, JWT, Quartz, Vue.js, MS-SQL, SAP/OData, Dynamic DataSource

## Architecture
<img width="1147" height="706" alt="image" src="https://github.com/user-attachments/assets/d04e8216-be7d-419e-b0b9-d295cbe3b2ed" />

## Problem

- 3000만 건 이상의 대용량 데이터 이관 시 JVM 메모리 한계 발생
- GC 부하 증가로 인한 처리 안정성 저하
- 다수의 스케줄링 배치 작업 실행 시 동시 프로세스 증가로 인한 성능 저하 및 배치 작업 실패 발생
- 대량 데이터 처리 중 실패 위치 추적 어려움
- 배치 실패 시 데이터 이관 지연과 수작업 재처리 비용 발생

## Solution

### 1. Paging/Chunk 처리

대용량 데이터를 한 번에 로딩하지 않고 Paging/Chunk 단위로 분할 처리
이를 통해 Heap 사용량과 GC 부하를 줄이고, 처리 단위를 명확히 분리

### 2. Thread Pool + Work Queue 적용

다수 배치가 동시에 실행되며 발생하던 프로세스 증가와 실패 문제를 제어하기 위해 Thread Pool과 Work Queue를 적용
동시 실행 수를 제한하고, 초과 작업은 대기열에서 순차 처리되도록 구성해 서버 리소스 사용량이 급격히 증가하지 않도록 제어

### 3. 실패 지점 추적 가능 구조

Chunk 단위로 성공/실패 로그를 남겨 실패 위치를 추적하고, 전체 배치를 다시 실행하지 않고 실패 구간을 확인할 수 있는 기반을 마련

### 4. 처리 로직 역할 분리

서비스에서 수행하던 데이터 검증·변환 로직은 최소한으로 유지하고, 대용량 처리와 반복 계산이 필요한 로직은 SQL Server의 Stored Procedure와 Function으로 분리

## Result

- 배치 실패율을 0%로 개선해 대용량 데이터 이관 작업의 안정성을 확보
- 3000만 건 규모 데이터 추출 시간을 2시간에서 1시간 20분으로 단축
- Paging/Chunk 처리로 JVM Heap 사용량과 GC 부하를 줄여 장시간 배치 실행 안정성 개선
- Thread Pool + Work Queue 기반 동시성 제어로 다수 배치 실행 시 프로세스 증가와 실패 가능성 완화
- Chunk 단위 처리 결과 저장으로 실패 위치 추적과 재처리 가능
- 데이터 검증, 변환 로직을 SQL Server Stored Procedure와 Function으로 분리해 서비스 부하를 줄이고 DB 중심의 대용량 처리 효율 개선


