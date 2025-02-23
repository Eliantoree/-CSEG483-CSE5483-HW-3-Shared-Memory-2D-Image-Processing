# -CSEG483-CSE5483-HW-3-Shared-Memory-2D-Image-Processing
[CSEG483/CSE5483] HW 3: Shared Memory를사용한 2D Image Processing


**Download Link:https://programming.engineering/product/cseg483-cse5483-hw-3-shared-memory%eb%a5%bc%ec%82%ac%ec%9a%a9%ed%95%9c-2d-image-processing/**

Description
5/5 – (2 votes)
제출 마감: 6월 16일(일) 오후 8시 정각 이전에 조교가 사이버 캠퍼스에 공지한 방식으로 제출

참고: LATE 없음

다음문제는 shared memory를사용한 Gaussian filtering커널의최적화에 관한것이다.

먼저 수업 시간에 설명한 Guassian filtering방법을 구현한 GPU 커널([GF-GLOBAL])에 대한 CPU

버전([GF-CPU])을 구현하라. [10점]

다음이코드를 shared memory를사용하여 속도를향상시키는 GPU 커널([GF-SHARED-1])을구현 하라. 이구현에서는 thread block의 thread 1개가 1개의 pixel을처리하여야 한다. [50점]

[GF-GLOBAL] 방법과 [GF-SHARED-1] 방법의 결과영상 간에 픽셀 별 차이 영상, 즉 각결과의 각 pixel의 RGB channel 값의 차이에 대한 절대값을 저장해주는 영상을 구한 후 적절한이름의 파일로 저장하여 그 결과를 시각적으로확인하라. A channel 값은 255로 할 것.[10점]

[GF-SHARED-1] 방법과는 달리 1개의 thread가 두 개 이상(예를 들어, 4개)의 pixel을 처리하는 shared memory 방법([GF-SHARED-N]) 방법을 구현하라. 이때 thread 당 몇개의 pixel을 처리할 지는자신이 결정하라. [30점]

[GF-GLOBAL] 방법과 [GF-SHARED-N] 방법의 결과영상 간에 픽셀 별 차이 영상, 즉 각결과의 각 pixel의 RGB channel 값의 차이에 대한 절대값을 저장해주는 영상을 구한 후 적절한이름의 파일로 저장하여 그 결과를 시각적으로확인하라. A channel 값은 255로 할 것. [10점]

비교 영상을 통하여계산의 정확도를 확인한 후, 위의 네가지 방법의 계산 성능을 비교 분석하라.

과연 자신이 예상한 대로결과가산출되었는지 설명할 것. [30점]

• 이번 숙제에서는 [GF-GLOBAL] 예제 코드에서와는달리편의상 GF를 연달아 10번 적용한다고가 정한다(즉 입출력데이터를 번갈아 가면서 커널을 10번호출함.)

• 실험은 제공한 영상 데이터들을 크기가 작은 것부터 큰것까지적절한 개수를 선택하여 수행한 후 그 결과를 비교 분석할 것.

지금 N장으로 구성한 영상 집합이있다고가정하자. (편의상 Image 0 7360 4832.jpg 영상 N장으로 구성 되어 있다고가정하며, N 값은자신의 실험 CPU 메모리에 한 번에 올릴 수 있는 선에서 가급적 크게 설정하자.)

먼저 Null stream, 즉 default stream 1개만사용하여 각영상 집합의 각영상을 H2D → Kernel → D2H

방식으로처리하는 방법([IMAGESET-DEFAULT])을 구현한 후, host에서의 수행 시간을측정하라. (이 방법을하나의함수를 호출하는 방식으로 구현할 것.) [30점]

다음자신이실험적으로 선택한 M에 대하여 M개의 Nondefault stream을사용하여 영상집합의 각영상에 대한 처리를 과정을 효과적으로겹치게해주는 방법([IMAGESET-NONDEFAULT-M])을

구현한 후, host에서의 수행 시간을측정하라. (이 방법도 하나의함수를 호출하는 방식으로 구현할 것.) [40점]

서강대학교 공과대학컴퓨터공학과

(2/1)

[IMAGESET-DEFAULT] 방법과 [IMAGESET-NONDEFAULT-M] 방법의 수행 시간을 비교 분석하라. [20점]

(자유형) [IMAGESET-NONDEFAULT-M] 방법의 속도를 더 향상시킬 수 있는 방법([IMAGESET-EXTRA])이있다면 그 방법을 제안하여 구현한 후기존 방법과의 성능을 비교하라. [최대 30점]

제출물: 자신이 구현한 코드를이름이 HW 3 학번인 디렉터리 아래에 위의 두 문제에 대한 Problem 1

과 Problem 2 이름의 directory를 각각만들어 Visual Studio 2022 프로젝트를생성한 후, zip으로 압축하여제출할 것.

자신이작성한코드: Visual Studio 2022를 통하여 확인할 수 있도록 위의 directory를 제출하되

.vs 파일 등 코드 수행에 불필요한 파일들은 반드시 제거한 후 제출할 것.

프로그램 실행결과: 자신의 코드를 실행한 결과를 증빙할 수 있는자료(예를 들어, 콘솔 윈도 우의 내용을캡춰한 영상)를 보고서에포함할 것.

보고서: 자신의 실험 결과를 바탕으로분석한 내용을 기술할 것.

참고:

보고서에는 각문항의 구현여부를 명확히 밝혀라.

각방법의 실험 결과에 대하여 자신만의 방식으로의견을 제시하라.
