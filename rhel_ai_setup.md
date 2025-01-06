# RHEL AI Setup Guide

**RHEL AI** (Red Hat Enterprise Linux AI)는 Red Hat에서 제공하는 AI/ML 기반 지식 관리 및 서비스 플랫폼입니다. 이 가이드는 RHEL AI 1.3 버전의 설치와 구성 방법을 설명합니다.

## 시스템 요구사항

RHEL AI를 설치하기 위해서는 다음과 같은 요구사항이 필요합니다:

- Git 저장소 접근 권한
- Python 3.10 이상 버전
- 마크다운 문서 변환 도구

## Knowledge 구성 방법

RHEL AI의 Knowledge 구성은 다음과 같은 단계로 이루어집니다:

1. **문서 준비**
   - 모든 문서는 마크다운(.md) 형식으로 변환
   - 이미지나 차트 제외 (텍스트만 지원)
   - 각주 제거
   - 표는 마크다운 형식으로 변환

2. **Git 저장소 설정**
   - 문서를 호스팅할 Git 저장소 생성
   - 저장소 접근 권한 설정
   - 문서 업로드 및 버전 관리

3. **qna.yaml 파일 구성**
   - version: 현재 지원 버전은 3
   - created_by: 작성자 정보
   - domain: knowledge 카테고리
   - context: 최대 500 토큰, 5개 블록 필요
   - questions_and_answers: 각 context당 최소 3쌍의 QA 필요

## Knowledge 업데이트 프로세스

1. **문서 변환**
   - Pandoc 사용
   - Visual Studio Code + Markdown All in One 확장 사용
   - IBM Deepsearch/Docling 사용

2. **품질 관리**
   - 문서 형식 검증
   - 토큰 제한 확인 (context: 500, QA: 250)
   - Git 커밋 해시 기록

3. **배포 및 관리**
   - Git 저장소에 업로드
   - 버전 관리
   - 문서 추적성 유지
