# java-racingcar-precourse

# 1. 자동차 경주 진행 방식 정리

* n개의 자동차는 지정한 횟수만큼 숫자 뽑기를 진행하는 동안 전진하거나 멈출 수 있다.
* 각 자동차마다 이름, 현재까지 전진한 거리의 정보를 저장한다.
* 각 자동차는 숫자를 뽑을 때마다 0~9 사이의 값을 무작위로 부여받고, 그 값이 4 이상일 때만 전진한 횟수가 늘어난다.

* 사용자는 먼저 자동차의 이름을 입력한다. 이때 자동차의 이름은 쉼표로 구분되며, 각각의 이름은 5글자 이하로만 입력할 수 있다.
* 참가할 자동차의 이름을 입력했다면, 그 다음에는 각 자동차마다 숫자를 뽑는 횟수를 입력한다.
* 숫자를 뽑는 횟수까지 입력했다면, 각각의 자동차들은 입력한 횟수만큼 전진하거나 멈춘다.
* 각 자동차마다 숫자 뽑기를 진행할 때 현재까지의 전진 횟수는 증가하거나 유지된다.

* 각 자동차마다 입력한 횟수만큼 숫자 뽑기를 반복했다면 자동차 경주 게임이 끝난다.
* 자동차 경주 게임이 종료되면 최종 우승자를 출력한다.
* 최종 우승자가 여러 명이면 입력된 순서대로 출력하고 쉼표(`,`: 띄어쓰기 없음) 로 구분한다.
* 사용자가 잘못된 값을 입력하면 `IllegalArgumentException`이 발생한다.

---

# 2. 입력

* `경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)` 메시지를 출력한다.
* 첫번째 메시지가 출력되면 그 다음 줄에 경주에 참가할 자동차의 명단을 작성한다. 자동차 이름은 입력한 순서대로 저장된다.
  - 입력한 문자열이 쉼표로 시작하거나 끝나는 경우 `IllegalArgumentException`이 발생한다.
  - 자동차 명단에 포함된 이름들 중 하나라도 빈 문자열이거나 5글자를 초과하면 `IllegalArgumentException`이 발생한다.
  - 출전하는 자동차가 오직 한 대뿐이면 경주를 진행할 수 없으므로 `IllegalArgumentException`이 발생한다.

* 자동차 이름을 입력했다면 `시도할 횟수는 몇 회인가요?`라는 메시지를 출력한다.
* 두번째 메시지가 출력되면 그 다음 줄에 각 자동차마다 숫자를 뽑는 횟수를 입력한다.
  - 숫자를 뽑는 횟수를 정수형으로 변환할 수 없으면 `IllegalArgumentException`이 발생한다.

* 자동차의 명단과 숫자 뽑기 횟수가 모두 유효하다면 입력을 종료하고 그 다음의 한 줄을 비운다.

---

# 3. 자동차

* 각 자동차는 숫자를 뽑을 때마다 0~9 사이의 무작위 값을 부여받으며, 그 값이 4 이상일 때 현재 전진한 횟수가 1 증가한다.
* 각 자동차마다 숫자를 뽑은 시점에서의 전진 횟수를 리스트에 저장한다.

---

# 4. 자동차 경주

* 자동차 경주는 입력했던 횟수만큼 각 자동차마다 숫자를 뽑는 식으로 진행된다. 즉, 각 자동차마다 숫자를 뽑는 횟수는 모두 동일하다.
* 각 자동차마다 숫자 뽑기를 통해 현재까지의 전진 횟수를 유지하거나 증가시킬 수 있다.

* 숫자 뽑기 횟수만큼의 반복이 종료된 이후에는 최종 우승자를 결정한다.
* 최종 우승자는 마지막 숫자 뽑기를 진행했을 때의 전진 횟수가 최대인 자동차가 된다.
* 최종 우승자가 여러 명일 경우, 입력한 순서대로 최종 우승자 명단을 작성한다.

---

# 5. 출력

## 실행 결과 출력

* 실행 결과를 출력하기에 앞서 `실행 결과` 문구를 출력한다.
* 그 다음줄부터는 각 자동차마다 현재까지 전진한 양상을 출력한다. 이때 자동차별 출력 순서는 입력된 순서를 따른다.
* 각 자동차마다 현재까지 전진한 양상은 `이름 : ----`과 같은 형태로 출력한다. 이때 `-`는 자동차가 전진한 횟수만큼 반복된다.
* 각 자동차별 전진 양상를 출력했다면 한 줄을 비운다.
* 위의 과정을 이전에 입력한 숫자 뽑기 횟수만큼 반복한다.

## 최종 우승자 출력

* 입력한 숫자 뽑기 횟수만큼의 반복이 종료되면 최종 우승자를 출력한다. 
  - 최종 우승자가 한 명인 경우 `최종 우승자 : 이름`과 같은 방식으로 출력한다.
  - 최종 우승자가 여러 명일 경우 `최종 우승자 : 이름1, 이름2 ...`과 같은 방식으로 출력한다.
* 최종 우승자가 여러 명인 경우 입력된 순서대로 출력하고 `, `로 구분한다.