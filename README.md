# 로보독 라디오(Robodog Radio)

이 패키지는 **라디오 통신 전용 MakeCode 확장**입니다.
로보독 기본 동작 블록과 함께 AI 블록을 사용할 수 있습니다.

This package is the **radio-only MakeCode extension** for Robodog.
It includes the base control blocks together with the AI blocks.

* 시작할 때 `rfBand` 블록으로 라디오 밴드를 먼저 설정해야 합니다.
* 이 패키지는 `radio` 의존성을 사용하므로 **micro:bit Bluetooth 블록과 함께 사용할 수 없습니다**.
* Call `rfBand` first at startup to initialize the radio band.
* This package depends on `radio`, so it **cannot be used together with the micro:bit Bluetooth blocks**.

## 기본 사용법(Basic usage)

```typescript
robodog.rfBand(7)
robodog.gesture(deflib.Posture.Ready)
robodog.move(deflib.MoveDirection.Forward, 50)
```

```typescript
robodog.rfBand(7)
robodog.aiDetection(deflib.AiMode.FaceDetect)
robodog.faceTracking(deflib.AiClass.Class1)

basic.forever(function () {
    serial.writeLine("camera: " + (robodog.getCameraAlive() ? "true" : "false"))
    serial.writeValue("face", robodog.getFaceClass())
    basic.pause(1000)
})
```

## 확장으로 사용

* [https://makecode.microbit.org/](https://makecode.microbit.org/) 열기
* **새로운 프로젝트**에서 클릭
* 톱니바퀴 모양 메뉴에서 **확장**을 클릭합니다
* **https://github.com/kocoafab/robodog-radio**으로 검색하고 가져오기

## 지원제품(Supported targets)

* for PXT/microbit
