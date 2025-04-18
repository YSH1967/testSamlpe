## ✅ 클론 ST-LINK V2 DFU 모드 진입 방법

- 클론 보드에서 보통 다음 두 가지 방식

### 방법 1: 버튼/점퍼를 통한 DFU 진입

1. ST-LINK 보드에 **RESET**이나 **BOOT**이라는 버튼이 있는지 확인.
2. 버튼이 없으면 **PCB 위 점퍼**나 **점퍼 핀**을 찾기.
3. 아래 순서 시도:
    - USB 분리
    - 점퍼나 BOOT 핀을 HIGH로 설정 (혹은 BOOT0 연결) → **버튼을 누르고 5초 이상**
    - USB 다시 연결
    - `STLinkUpgrade` 실행 → "Open in update mode" 클릭

### 방법 2: 강제로 DFU 인식시키기 → 위에꺼 되면 안해도 됨 !!

1. USB를 꽂은 상태에서 `lsusb` 확인:
    
    ```bash
    **lsusb**
    ```
    
    정상이라면 **STMicroelectronics ST-LINK/V2** 같은 게 나올 거예요.
    
2. `dfu-util` 설치되어 있다면 DFU 모드로 진입했는지 확인 가능:
    
    ```bash
    **sudo apt install dfu-util
    dfu-util -l**
    ```
    
    만약 아무 장치도 안 나오면, DFU 모드가 아닌 상태임
