## 프로잭트 개요

- 프로젝트는 콘솔 기반의 햄버거 가게 주문 시스템을 구현
- 사용자가 다양한 햄버거, 사이드 메뉴, 음료를 선택하고 주문할 수 있는 기능을 제공
- 사용자는 주문을 완료하고 결제까지 진행할 수 있으며, 최종적으로 결제 금액과 거스름돈을 확인할 수 있음.

## 프로젝트 목표

1. **다양한 메뉴 제공**: 일반 햄버거, 스페셜 햄버거, 사이드 메뉴, 음료 등 다양한 메뉴를 제공하여 사용자의 선택의 폭을 넓힘.
2. **객체 지향 프로그래밍 적용**: 햄버거, 사이드, 음료 등의 메뉴를 객체로 관리하고, 이를 주문 객체에 추가하여 주문의 복잡성을 낮추는 것을 야기.
3. **결제 시스템 구현**: 사용자가 주문한 내역을 바탕으로 총 금액을 계산하고, 사용자가 입력한 금액과 비교하여 거스름돈을 계산.
4. **확장성 및 유지보수성**: 추후 메뉴를 추가하거나 기능을 확장할 때 용이하도록 코드를 구조화.

## 프로그램 구조
<p align="center"> <img src="https://github.com/Namgyu11/4_kks_Java_Study/assets/103015031/bc9ff4e1-57c2-4cb1-8076-7b2ff9e1813b"></p>


### 프로그램 설계도

<p align="center"> <img src="https://github.com/Namgyu11/4_kks_Java_Study/assets/103015031/06a7eff6-2163-42bc-ac15-7865dec34ded"></p>

<p align="center"> <img src="https://github.com/Namgyu11/4_kks_Java_Study/assets/103015031/caae0fe2-1199-40af-8d89-38102eb700ce"></p>



## 주요 클래스 및 메서드 설명

## **주요 클래스 및 메서드 설명**

### **Main 클래스**

- 프로젝트의 진입점이며, 전체적인 주문 흐름을 제어.
- 주요 기능:
    - **`OrderManager`**를 호출하여 전체 주문 과정을 시작.
    - 사용자 수와 이름을 입력받고, 각 사용자의 주문을 처리.

### **OrderManager 클래스 (추가)**

- 사용자 수와 이름을 입력받고, 각 사용자의 주문을 처리.
- 주요 기능:
    - 사용자 수를 입력받고, 각 사용자의 이름을 입력받는다.
    - 각 사용자에 대해 **`OrderProcessor`**를 생성하여 주문을 처리.
    - 모든 주문이 완료된 후 최종 메시지를 출력.

### **OrderProcessor 클래스 (추가)**

- 각 사용자의 주문을 처리하는 클래스.
- 주요 기능:
    - 사용자가 메인 메뉴에서 일반 햄버거와 스페셜 햄버거 중 하나를 선택하도록 한다.
    - 선택된 메뉴에 따라 해당 카테고리의 메뉴 리스트를 출력하고, 사용자가 선택한 메뉴를 주문 객체에 추가한다.
    - 사용자가 세트 메뉴를 선택하면, 사이드 메뉴와 음료를 추가로 선택할 수 있다.
    - 사용자가 메뉴 선택을 완료하면 주문 내역을 출력하고, 수량을 입력 받는다.
    - 총 금액을 계산하고, 사용자가 입력한 금액과 비교하여 거스름돈을 계산한다.

### **OrderList 클래스 (수정)**

- 주문 내역을 관리하고, 각 메뉴를 추가하는 기능을 제공.
- 주요 기능:
    - 메뉴 항목을 추가하고, 주문 내역을 관리.
    - 총 금액을 계산하고 주문 내역을 출력하는 메서드를 포함.

### **MenuUtils 클래스**

- 메뉴와 관련된 유틸리티 메서드를 제공.
- 주요 기능:
    - 메뉴 리스트를 출력하고, 사용자가 선택한 메뉴를 주문 객체에 추가하는 메서드를 포함.
    - 세트 메뉴 선택 시, 사이드 메뉴와 음료를 추가하는 메서드를 포함.
    - 주문 수량을 입력받고, 결제 금액을 처리하는 메서드를 포함.

### **Burger, SpecialBurger, Side, Drink 클래스**

- 각각 햄버거, 스페셜 햄버거, 사이드 메뉴, 음료를 나타내는 클래스.
- 공통적으로 이름과 가격을 속성으로 가지며, 스페셜 햄버거는 추가로 특별 재료를 속성으로 가진다.

### **MenuType enum**

- 메뉴의 타입을 정의하는 열거형(enum).
- **`BURGER`**, **`SPECIAL_BURGER`**, **`SIDE`**, **`DRINK`** 네 가지 타입을 포함.

### **구현 세부 사항**

1. **사용자 추가 (추가)**
    - 프로그램이 시작되면 사용자 수를 입력받는다.
    - 각 사용자의 이름을 입력받는다.
    - 각 사용자에 대해 **`OrderProcessor`** 객체를 생성하여 주문을 처리하도록 한다.
2. **메인 메뉴**
    - 사용자에게 일반 햄버거와 스페셜 햄버거 중 하나를 선택하도록 한다.
    - 선택된 메뉴에 따라 해당 카테고리의 메뉴 리스트를 출력하고, 사용자가 선택한 메뉴를 주문 객체에 추가한다.
3. **세트 메뉴**
    - 사용자가 세트 메뉴를 선택하면, 사이드 메뉴와 음료를 추가로 선택할 수 있다.
    - 사이드 메뉴와 음료는 각각 별도의 메서드를 통해 사용자로부터 선택을 받을 수 있다.
4. **주문 내역 및 결제**
    - 사용자가 메뉴 선택을 완료하면 주문 내역을 출력하고, 수량을 입력 받는다.
    - 총 금액을 계산하고, 사용자가 입력한 금액과 비교하여 거스름돈을 계산한다.

<p align="center"> <img src="https://github.com/Namgyu11/4_kks_Java_Study/assets/103015031/7964ed6e-20f3-4164-b7dd-f63b9259f315
"></p>
