# Documenation of Deltatime
This documenation is unfinished yet.   
- Supports en-US Guide.
- 한국어 도움말을 지원합니다.

---

# [en-US] English Guide

## Introduction
- **Deltatime**(aka dtbx) is a [TurboWarp](https://turbowarp.org/) extension which provides soft, precision Delta timing blocks.
- Guidance of v2.2.x

## Basic knoledgement
- Note that FPS and ΔT are in directly-impactable relationship, so even mentioning only "FPS" or "ΔT" normally means both of them.
- ΔT means the "Delta Time".

## FPS & ΔT

```scratch
(ΔT :: #333333)
```

`FPS` and `ΔT` value of **dtbx** has following properties :
- `FPS` block returns roundary integer value of **current Framerate** using `Math.round()`.
- When Framerate goes down to < 0.5, `FPS` block starts to return real number of **current Framerate** by 2 decimal places using `.toFixed(2)`.
- If the `FPS` value is not grater than 0, `ΔT` value will be also set to 0 until `FPS` grater than 0.

## Filtering
- **Filtering** blocks are purposed to stablize FPS.   
- `Filter Strength`(aka strength) is a value that directly determines the performance and stability of FPS. Cannot be smaller than 1 and also bigger than 907.
- When filter strength has been set to higher value :
  - FPS and ΔT will be less fluctuate.
  - Updating time of FPS and ΔT will be increase. That means small variation of FPS may be ignored as strength arises.

## Stability Evaluator
Stability Evaluator provides value of "How much stable" or "How fast to update" FPS in actual working.
Not added yet.

## Autopilot
- Autopilot is a function that automatically adjusts the `Filter Strength`, refering `Stability Evaluator` to achieve user's target purpose.
- Autopilot has following modes : "Fast Updating", "Stability Focusing", "Fast & Stabilizing".
  - When Autopilot has been set to "Fast updating" mode, it focuses at only rapid renewing of FPS until shorten by target time.
  - When Autopilot has been set to "Stability Focusing" mode, it focuses at only stabilization of FPS until achieve target value.
  - When Autopilot has been set to "Fast & Stabilizing" mode, it detects the fluctuation of FPS and adjusts the strength flexible.
 
Not added yet.

---

# [ko-KR] 한국어 도움말

## 소개
- **Deltatime**(일명 dtbx)은 부드럽고 보다 정확한 델타 시간계 값을 제공하는 [TurboWarp](https://turbowarp.org/)의 확장 기능입니다.
- v2.2.x 기준

## 개념 설명
- **FPS**는 특정 환경에서 화면이 초당 새로고침되는 횟수(일명 주사율)를 숫자로 나타낸 값입니다. 예시로 60 FPS는 **화면이 1초에 60번 바뀌는 것**을 의미합니다.
- **ΔT**는 "델타 타임" 또는 "델타 시간계"를 의미합니다. 1을 FPS 값으로 나누어 얻을 수 있는 값입니다.
- FPS와 ΔT는 상호 간의 직접적인 영향을 받는 값입니다. 따라서 해당 문서에서 "FPS" 나 "ΔT" 중 한 가지만 언급하였더라도 보통은 두 가지 모두를 의미하는 것으로 간주할 수 있습니다.

## FPS 및 ΔT
**dtbx**의 `FPS`와 `ΔT` 값은 다음과 같은 속성을 가집니다.
- `FPS` 블럭은 JS의 `Math.round()` 함수를 사용하여 **현재 주사율**을 정수로 반올림한 값을 반환합니다.
- 주사율이 0.5 미만으로 떨어질 경우, `FPS` 블럭은 **현재 주사율**의 소수 이하 2번째 자릿수 까지의 실수 값을 반환하기 시작합니다. 해당 상황에서는 JS의 `.toFixed(2)` 함수를 사용합니다.
- 만약 `FPS` 값이 0보다 크지 않을 경우, `FPS` 값이 0보다 커질 때까지 `ΔT` 값 또한 0으로 설정됩니다.

## 필터링
- **Filtering** 탭에 있는 블록들은 FPS를 안정화하는 데 사용됩니다.
- `Filter Strength`(일명 필터 강도)는 FPS의 안정성 및 성능을 직접적으로 결정하는 값입니다. 1보다 작거나 907보다 클 수 없습니다.
- 필터 강도가 증가하면 `FPS` 및 `ΔT` 값에 다음과 같은 변화가 일어나게 됩니다.
  - 해당 값들이 비교적 덜 요동치게 됩니다.
  - 주사율의 실제 값이 반영되기까지 더 많은 시간이 걸리게 됩니다. 따라서 필터 강도가 증가함에 따라 실제 주사율 값의 작은 변동이 무시될 수 있습니다.
 
## 안정성 평가자
`Stability Evaluator`는 실제 상황에서 FPS가 얼마나 안정적인지에 대한 평가를 실시합니다.
아직 추가되지 않았습니다.
