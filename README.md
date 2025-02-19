# JoystickMotor

## 📌 프로젝트 개요
STM32F103RBT6 마이크로컨트롤러를 사용하여 조이스틱 입력을 기반으로 DC 모터를 제어하는 임베디드 시스템입니다. ADC(조이스틱 입력), PWM(모터 속도 조절), GPIO(장애물 감지) 및 UART(디버깅용)를 활용하여 정밀한 모터 제어가 가능합니다.

---

## 🛠 사용된 하드웨어
- **MCU:** STM32F103RBT6
- **입력 장치:** 조이스틱 (ADC 사용)
- **모터 드라이버:** (사용된 모터 드라이버 명시 필요)
- **센서:** 장애물 감지용 GPIO 입력 핀 (PB10, PB4)
- **통신:** UART (USART3, 115200 baud rate)

---

## 🏗 프로젝트 구조
```plaintext
JoystickMotor/
├── Core/                # 핵심 소스 코드
├── Drivers/             # 하드웨어 드라이버
├── .cproject            # 개발 환경 설정 파일
├── .project             # 프로젝트 설정 파일
├── main.c               # 메인 코드 (모터 제어, ADC 읽기, 장애물 감지 등)
├── STM32F103RBTX_FLASH.ld  # 링커 스크립트
├── TryMotorJoystick.ioc  # STM32CubeMX 설정 파일
└── README.md            # 프로젝트 설명 파일
```

---

## ⚙️ 주요 기능
1. **조이스틱 입력을 기반으로 모터 제어**
   - ADC를 사용하여 조이스틱의 X, Y 축 값을 읽음
   - X축(전진/후진), Y축(좌회전/우회전) 제어
   - PWM을 활용하여 부드러운 속도 조절 가능 (추후 개선 가능)

2. **장애물 감지 및 자동 정지**
   - YOLO를 이용한 장애물 감지 여부 송신
   - 장애물 감지 시 모터 동작 차단

3. **버튼을 이용한 조이스틱 활성화/비활성화**
   - GPIO 입력 핀(A0)을 사용하여 버튼 클릭 시 조이스틱 활성화/비활성화 토글

4. **UART 디버깅 (USART3)**
   - `printf`를 통해 실시간으로 센서 값 및 상태 확인 가능 


## 작품 사진
![Wheelchir Image](./wheelchair.jpg)
---

