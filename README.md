# 안드로이드 개념적인 부분
## 안드로이드 4대 컴포넌트
#### 액티비티(Activity), 서비스(Service), 브로드캐스트 리시버(BroadCast Receiver), 콘텐트 프로바이더(Content Provider)
#### 각각의 컴포넌트는 인텐트를 통해 상호작용
#### <br>

## Context란?
#### 애플리케이션(객체)의 현재 상태의 맥락을 의미
#### 컨텍스트는 새로 생성된 객체가 지금 어떤 일이 일어나고 있는지 알 수 있도록 함
#### 액티비티와 애플리케이션에 대한 정보를 얻기 위해 사용
#### 애플리케이션 context와 액티비티 context가 존재
#### <br>

## 애플리케이션 컨텍스트(Application Context)란?
#### 싱글턴 인스턴스이며 액티비티에서 getApplicationContext()를 통해 접근 가능
#### 애플리케이션 라이프 사이클과 연결돼 있음
#### 현재의 컨텍스트와 분리된 라이프사이클을 가진 컨텍스트가 필요하거나 액티비티의 범위를 넘어서 컨텍스트를 전달할 때 사용
#### <br>

## 액티비티 컨텍스트(Activity Context)란?
#### 액티비티에서 사용 가능
#### 액티비티의 라이프사이클과 연결되어 있음
#### 액티비티의 범위 내에서 컨텍스트를 전달 또는 라이프사이클이 현재의 컨텍스트에 붙은 컨텍스트가 필요할 때 사용
#### <br>

## 생명주기란?
#### 상태 변화가 있을 때마다 화면에 보이는 액티비티의 생명 주기 메서드를 호출해서 상태 변화를 알려줌
#### onCreate : 만들어 졌을 때
#### onStart : 화면에 나타날 때
#### onResume : 포커스가 떠난 후 다시 돌아올 때/ 현재 화면에 나타나 있을 때
#### onPause : 화면의 일부가 가려질 때
#### onStop : 완전히 가려졌을 때
#### onDestroy : 종료됐을 때
#### <br>

## 의존성 주입이란?
#### 의존관계를 외부에서 결정하고 주입하는 것
#### <br>

## 의존성 주입을 사용하는 이유
#### Unit Test 용이
#### 코드의 재활용성을 높여줌
#### 객체간의 의존성을 줄이거나 없엘 수 있음
#### 객체 간의 결합도가 낮아지고 유연한 코드 작성 가능
#### <br>

## XML이란?
#### AndroidManifest.xml, Layout 파일, Resource 파일 등 다양한 곳에서 사용
#### XML을 이용해 데이터를 쉽게 표현
#### Android OS가 XML을 파싱하여 데이터를 구조화함
#### <br>





#### <br>
# Kotli 문법적인 부분
## 클래스란?
#### 객체를 생성하기 위한 설계도
#### <br>

## 객체(인스턴스)란?
#### 설계도(클래스)로 찍어낸 실체
#### <br>

## 추상화(abstract)란?
#### 어떤 객체를 표현함에 있어 모든 것을 다 표현하는 것이 아니라 일정 부분 특징만을 표현
#### 목적을 위해 필요한 부분만을 찾을 수 있음
#### <br>

## 불변성(Immutability)이란?
#### 무언가가 변할 수 없다는 것을 의미함
#### 불변 변수 -> 변경될 수 없는 변수
#### val : 완전한 불변성 X
#### const val : 완전한 불변성
#### <br>

## Collection이란?
#### Generic으로 구현이 되어 다양한 타입과 함께 사용될 수 있음
#### 데이터를 모아 관리와 사용을 편리하게 하기 위해 만들어진 프레임워크
#### 기본적으로 Mutable(변경 가능 - 추가, 삭제 가능)과 Immutable(변경 불가능 - 수정 불가능)을 지원
#### List, Set, Map 존재
#### <br>

## List vs Set vs Map 비교
#### **공통점**
#### 모두 Collection, 모두 Mutable과 Immutable을 지원
#### <br>
#### **차이점**
#### List : 중복 허용O, 순차적
#### Set : 중복 허용X, 순차적이지 않은 집합
#### Map : Key-Value 두 개로 구성된 페어로 나타냄, key 중복 불가능, value 중복 가능
#### <br>

## Kotlin DSL이란?
#### DSL이란 특정 분야에 최적화된 프로그래밍 언어를 뜻함
#### 상용구 코드(보일러 플레이트 코드)를 최소화 하기 위해 명령형 코드 대신 선언적 코드 형식을 따름
#### 가독성이 좋고 간략한 코드를 사용하여 Gradle 스크립팅 함
#### <br>



#### <br>
# 라이브러리 부분

## Retrofit이란?
#### 서버와 클라이언트 간 http 통신을 위한 라이브러리
#### OKhttp를 기반으로 만들어짐
#### <br>

## Okhttp란?
#### RESP API, HTTP 통신을 간편하게 구현할 수 있도록 기능을 제공
#### Retrofit의 베이스가 됨
#### <br>

## Okhttp vs Retrofit 비교
#### 공통점
#### 둘다 HTTP 클라이언트 라이브러리
#### <br>
#### 차이점
#### Retrofit : HTTP client 역할을 수행
#### Okhttp : 통신을 하는동안 데이터를 전송
#### <br>

## Dagger hilt란?
#### Dagger의 높은 러닝커브를 보안하고 초기 구축 비용을 절감하기 위해 탄생한 의존성 주입 라이브러리
#### <br>

## Koin이란?
#### Kotlin DSL로 만들어짐
#### Dagger에 비해 러닝커브가 낮음
#### 리플렉션을 이용해 런타임에 오브젝트 그래프를 그려주기 때문에 앱 성능이 저하됨
#### <br>

## Jetpack Compose란?
#### Native UI를 코드레벨로 구현할 수 있는 최신 툴킷
#### 필요한 영역의 뷰를 다시 그려주는 방식으로 작업
#### 코드 감소, 직관적, 빠른 개발 과정, 강력한 성능 등의 이점이 있음
#### <br>

## DataBinding이란?
#### xml파일에 Data를 연결해서 사용할 수 있게 도와줌
#### 글루코드(프로그램의 요구사항 구현에는 기여하지 않지만, 본래 호환성이 없는 부분끼리 결합하기 위해 작동하는 코드) 최소화
#### <br>

## ViewBinding이란?
#### View와 상호 작용하는 코드를 쉽게 작성할 수 있는 기능
#### <br>

## Glide란?
#### 이미지 로딩 라이브러리
#### 어떤 종류의 이미지라도 빠르고 부드럽게 스크롤할 수 있게 하는 것이 목적
#### 붙이기, 리사이즈, 디스플레이에 효과적
#### <br>

## Glide vs Picasso 비교
#### 공통점
#### 둘 다 이미지 로딩 라이브러리
#### <br>
#### 차이점
#### Picasso : Bitmap포맷을 ARGB_8888로 사용 (화질 좋음)
#### Picasso : Bitmap포맷을 RGB_565를 사용 (메모리 용량 적음)
#### Picasso는 1920x1080크기의 원본 이미지를 메모리로 가져와서 GPU에서 실시간으로 리사이징
#### Glide는 바로 768x432크기로 메모리에 가져와서 ImageView로 할당 시키기때문에 메모리 사용량이 적음
#### <br>



#### <br>
# 디자인 패턴, 아키텍처 부분

## 싱글톤 패턴이란?
#### 해당 클래스에 한 개의 인스턴스만을 갖게하고 전역 범위에서 이 인스턴스에 접근해 사용
#### <br>

## MVVM 디자인 패턴이란?
#### MVP에서 파생됨
#### 모델 - 뷰 - 뷰모델 각각의 기능에 따라 분리하여 코드를 작성
#### <br>
#### 개념적인 의미
#### Model : 데이터와 데이터에 관련된 행위를 모두 합쳐 Model 이라 부름
#### View : 사용자에게 화면으로 보여지는 모든 구조, 레이아웃을 의미
#### ViewModel : View 의 추상화된 형태, View 에 보여져야하는 데이터와 명령들을 가지고 있음
#### <br>
#### 안드로이드에서의 의미
#### Model : Network, DB, SharedPreferences 등 다양한 Data Source 로부터 필요한 데이터를 준비
#### View : Activity, Fragment, CustomView, Dialog, Toast, Snackbar, Menu 등의 UI 컴포넌트
#### ViewModel : View 와 Model 사이의 매개체 역할을 함
#### <br>

## MVP 디자인 패턴이란?
#### 모델 - 뷰 - 프레젠터로 구성
#### UI(View)와 로직(Model)을 분리하고 서로 간에 상호작용을 다른 객체(Presenter)에 그 역할을 줌으로써, 서로의 영향(의존성)을 최소화하는 것
#### MVC와 다르게 코드가 깔끔해짐
#### Model과 View의 결합도가 낮아 확장성이 개선됨
#### 어플리케이션이 복잡해질수록 View와 Presenter 사이의 의존성이 강해지는 문제가 있음
#### <br>
#### 개념적인 의미
#### Model : 프로그램 내부적으로 쓰이는 데이터를 저장하고, 처리하는 역할(비즈니스 로직)
#### View : UI를 담당 (Activity, Fragment 등)
#### Presenter : Model과 View사이의 매개체, 인터페이스를 통해 상호작용
#### <br>

## MVC 디자인 패턴이란?
#### 모델 - 뷰 - 컨트롤러로 구성
#### 컨트롤러와 View는 1:n 구조
#### 컨트롤러는 View를 선택할 뿐 직접 업데이트 하지는 않음 (View는 컨트롤러를 모름)
#### View와 Model 사이의 의존성이 높아 유지보수가 어려움
#### <br>
#### 개념적인 의미
#### Model : 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분입니다.
#### View : UI를 담당 (Activity, Fragment 등)
#### Controller : 사용자의 입력(Action)을 받고 처리하는 부분
#### <br>
