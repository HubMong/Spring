# 📘 SpringBasic Java 학습 노트

Java OOP의 기본 개념과 객체 설계, 의존성 주입, 다형성 등을 연습하는 실습 프로젝트입니다.  
날짜별 디렉토리에 따라 단계적으로 학습이 구성되어 있으며, 추후 Spring Framework 진입 전 기초 개념을 다지는 데 유용합니다.


## 📂 프로젝트 구조

springbasic/
├── pom.xml
└── src/
└── main/
└── java/
├── d0616_01/
├── d0616_02/
└── d0616_03/

## 📑 목차

[d0616_01 - 클래스 합성과 기본 객체 설계]
[d0616_02 - 인터페이스와 전략 패턴 연습]
[d0616_03 - 전략 패턴과 성적 시스템 통합]

## 📌 d0616_01

**주제:** 클래스 간 관계 (합성), 기본 객체 설계

### 📁 주요 파일

- `Student.java` - 이름, 나이, 성적(Sungjuk)을 포함
- `Sungjuk.java` - 국어, 영어, 수학 점수 및 평균 계산
- `Main1.java`, `Main2.java` - 객체 생성 및 출력 테스트
- `setting.xml` - 객체 설정용 (Spring Bean 설정 연습용)

### 💡 학습 포인트

- 클래스 간 `has-a` 관계 구성
- XML을 통한 객체 초기화 구조 실습
- 객체 간 의존성 표현


## 📌 d0616_02

**주제:** 인터페이스 기반 전략 패턴 구현

### 📁 주요 파일

- `Print.java` - 출력 인터페이스
- `ConsolePrint.java`, `GridPrint.java` - 출력 방식 구현
- `PersonInfo.java` - 사용자 정보 보관
- `Main.java` - 전략 주입 후 실행

### 💡 학습 포인트

- 출력 전략을 `Print` 인터페이스로 추상화
- `PersonInfo`는 `Print`에 의존하지만 구체 구현은 외부에서 주입
- 전략 교체의 유연성 확보


## 📌 d0616_03

**주제:** 성적 시스템 + 출력 전략 결합

### 📁 주요 파일

- `Student.java`, `Sungjuk.java` - 재사용
- `Print.java` + 구현체 - 동일
- `PrintInfo.java` - 학생 정보를 출력하는 통합 클래스
- `Main.java` - 전체 로직 실행

### 💡 학습 포인트

- 기존 도메인 모델에 전략 패턴 결합
- OCP (Open-Closed Principle) 설계
- 의존성 주입 및 추상화 활용 강화


## 🧠 설계 핵심 요약

| 개념 | 설명 | 적용 클래스 |
|------|------|--------------|
| 클래스 합성 | 객체 간 관계를 `has-a`로 표현 | `Student` → `Sungjuk` |
| 인터페이스 다형성 | 공통 동작 추상화 | `Print` 인터페이스 |
| 전략 패턴 | 기능을 외부에서 주입 | `ConsolePrint`, `GridPrint` |
| 의존성 주입 | 구체 구현을 외부에서 설정 | `Print` → `PersonInfo`, `PrintInfo` |
| 단일 책임 원칙 (SRP) | 클래스마다 하나의 책임만 수행 | `Print`, `PersonInfo`, `Sungjuk` 등 |
