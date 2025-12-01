#  Tinnitus Cognitive Therapy Program 
**이명(Tinnitus) 환자를 위한 MR 기반 인지 행동 치료(CBT) 콘텐츠**

<br>


> ##  Confidentiality Notice
> 본 프로젝트는 의료기관 및 기업과의 비밀유지계약(NDA)에 의거하여, 실제 구현 화면(스크린샷), 병원명, 상세 치료 프로토콜은 공개하지 않습니다.
>
> 본 문서는 개발자가 담당한 **시스템 최적화, 구현 기술, 협업 방식**을 중심으로 기술되었습니다.  

<br>

##  Project Overview
이명 환자의 증상 완화와 심리적 안정을 돕기 위한 **Mixed Reality(MR) 디지털 치료제**입니다.
이명에 대한 교육과 이완 훈련 과정을 가상 가이드(Mascot)와 함께 진행하며, 컨트롤러 없이 맨손으로 상호작용할 수 있는 몰입형 콘텐츠입니다.

* **Development Period:** 2025.07.30 ~ 2025.11.27 (4개월)
* **Team:** 2인 (Developer 1명, Planner/Designer 1명)
* **My Role:** Unity Client 개발 전담 (시스템 구현, XR 상호작용, 리소스 최적화)
* **Target Device:** Meta Quest 3

<br>

##  Tech Stack
| Category | Technology |
| :--- | :--- |
| **Engine** | Unity 6.0 LTS (C#) , Blender (최적화)|
| **XR Framework** | Open XR, XR Interaction Toolkit, Meta XR SDK|

<br>

##  Key Implementations & Optimization

### 1. Performance Optimization for Standalone VR
Quest 3 환경에서 고품질 비주얼과 72fps 이상의 안정적인 프레임 방어를 위해 **최적화 작업**에 개발 역량을 집중했습니다.

* **Graphics & Rendering:**
    * **Texture/Polygon:** 3D 모델의 불필요한 폴리곤 최소화(블렌더 작업) 및 텍스처 사이즈/포맷 최적화를 통해 메모리 최소화.
    * **Lighting:** 실시간 연산 부하를 줄이기 위해 배경 및 정적 오브젝트에 **Lightmap Baking** 적용, 런타임 라이트 연산 최소화.
    * **XR Settings:** URP 렌더링 파이프라인 설정을 조정하여, 그림자 해상도(Shadow Resolution) 및 그림자/라이트 쿠키 크기를 XR 환경에 최적화하고 GPU 부하를 최소화.

### 2. Hand Tracking Interaction
XR HMD 경험이 적은 환자들의 특성을 고려하여, 컨트롤러 없이 **직관적인 핸드 트래킹** 인터랙션을 구현했습니다.

* **Custom Poke Interactor:** 호버링 및 시각 피드백: Poke 시 손가락 끝 위치를 추적하여 Hover 및 Select 이벤트 시각 효과(버튼 눌림, 색상 변화, 버튼 크기 조정)를 구현해 자연스러운 UIUX를 제작했습니다.
* **Realistic Hand Pose Blending:** XR 인풋 SDK의 기본 그랩 포즈 대신, 물체별 커스텀 Hand Pose를 녹화 및 적용했습니다.  치료 도구를 쥘 때, 손이 물체를 뚫고 지나가는 이질감 없이 물체 모양에 맞게 손가락이 감싸 쥐는(Grasp) 자연스러운 인터랙션을 구현했습니다.


### 3. Smooth Transition & Sequence Control
딱딱한 의료 정보 전달을 피하고 부드러운 사용자 경험을 제공하기 위해 연출에 시간을 투자했습니다.

* **DOTween 활용:** UI 팝업, 씬 전환, 오브젝트의 등장/퇴장 시 **DOTween**을 활용해 시각적 피드백 제공.
* **Flow Control:** 시퀀스 흐름을 자연스럽게 구현해 환자가 흐름에 맞게 콘텐츠를 따라갈 수 있도록 유도.

### 4. Simple Data Management
복잡한 DB 구축 없이, 치료 진행 상황을 가볍고 효율적으로 관리했습니다.

* **Progress Check:** `PlayerPrefs`를 활용하여 각 세션(챕터)의 완료 여부, O/X 퀴즈 수행 여부 등 필수적인 진행 데이터만 로컬에 저장/로드하는 구조 구현.

<br>

##  Collaboration Process
기획자 겸 디자이너 1인과 개발자 1인으로 구성된 소규모 팀으로 협업했습니다.

* **Rapid Prototyping:** 기획/디자인 리소스가 나오면 즉시 유니티에 적용하고, XR 기기에서 확인 후 피드백을 반영하는 빠른 루틴으로 협업.
* **Constraint Solving:** 디자이너가 작업한 고해상도 리소스가 VR 기기에서 성능 저하를 일으킬 때, 리토폴로지나 텍스처 베이킹 등의 기술적 가이드를 제시하며 퀄리티와 성능의 타협점을 조율.

<br>

## Contact

-  개발자: **나우진**
-  이메일: [uujin314@icloud.com](mailto:uujin314@icloud.com)
