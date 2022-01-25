---
title: "플러터(Flutter) BLoC 기본 : Counter using Cubit"
categories:
- flutter
tags:
  - flutter
  - bloc
  - cubit

toc: true
toc_sticky: true

---

> 플러터의 상태관리(State Management)를 위한 패키지인 BLoC의 Counter 기본 예제를 통해 학습합니다. 이 예제는 Cubit을 사용하여 BLoC를 구현합니다.


![img1](https://raw.githubusercontent.com/felangel/bloc/master/docs/assets/bloc_logo_full.png)

### BLoC(Business Logic Components)

BLoC는 디자인패턴의 하나로 Flutter의 상태관리(State management)를 위한 강력한 방법입니다. 다른 상태관리 패키지로는 `Provider`, `GetX` 등이 있으며 간단히 `setState()` 함수를 호출하는 방법도 있습니다.

일반적으로 **Bloc > Provider or GetX > setState** 순으로 유지보수성이 낮아진다고 얘기할 수 있습니다. 유지보수성이 낮아진다는 말은 소스코드 간의 의존성이 강하여 변경하기 어려울 수 있다는 말입니다.

Flutter의 BLoC는 UI와 비즈니스 로직을 분리하기 위해 설계된 디자인패턴입니다. Google의 Paolo Soares와 Cong Hui가 설계했으며 DartConf 2018에서 처음 발표되었습니다.

----------


### BLoC의 원리

위젯은 `Sink`를 통해 `BLoC`로 이벤트를 보내고 `streams`를 통해 위젯으로 이벤트를 받는 컨셉입니다.

![img2](https://www.didierboelens.com/images/blog/streams_bloc.png)

위 사진은 간단히 말해서 위젯에 상태변화가 발생하면 BLoC를 통해 Streaming 한다는 말입니다.

스트림을 통해 상태를 관리하기 때문에 상태가 변화할 때마다 위젯을 빌드할 필요가 없습니다.

설명만으로는 이해하기 어려울 수 있으므로 아래서 BLoC의 기본 예제인 Counter를 통해서 자세히 알아볼 예정입니다.

----------


### BLoC의 장/단점

Flutter에서 BLoC를 활용하면 UI와 비즈니스 로직이 직관적으로 분리되게 됩니다. 

그렇기 때문에 일정규모 이상의 프로젝트를 진행할 경우에 높은 유지보수성을 기대할 수 있습니다.

다만, BLoC를 구현할 경우에 코드의 양이 많아지므로 소규모 프로젝트일 경우에는 굳이 사용할 필요는 없습니다.


#### 장점

- UI와 비즈니스 로직의 분리

- 유지보수성 향상

- TDD에 효과적


#### 단점

- 복잡한 소스코드 구조

- 학습의 어려움

----------

### Counter 예제

출처 : https://github.com/felangel/bloc/blob/master/docs/fluttercountertutorial.md
{: .notice--info}

#### 1. Flutter 프로젝트 생성

플로터 프로젝트를 생성하고 아래 프로젝트 구조와 같이 파일을 생성합니다.

- 프로젝트 구조 
```
├── lib
│   ├── app.dart
│   ├── counter
│   │   ├── counter.dart
│   │   ├── cubit
│   │   │   └── counter_cubit.dart
│   │   └── view
│   │       ├── counter_page.dart
│   │       └── counter_view.dart
│   ├── counter_observer.dart
│   └── main.dart
├── pubspec.lock
├── pubspec.yaml
```

----------


#### 2. Flutter BLoC Package 추가

```cmd
$ flutter pub add bloc
$ flutter pub add flutter_bloc
```

`pubspec.yaml` 파일에 직접 `dependencies`를 추가해주셔도 됩니다.
{: .notice--info}

----------


#### 3. 프로젝트 구조 분석

파일명 | 기능
---------- | ----------
lib/counter_observer.dart | `CounterObserver`로 감시자 구현
lib/main.dart | `CounterObserver()`를 감시할 위젯인 `RunApp`에 연결
lib/app.dart | `CounterPage()` Home으로 페이지 라우트
lib/counter/view/counter_page.dart | `BlocProvider()`로 `CounterView()`에 `CounterCubit()` State 연결
lib/counter/cubit/counter_cubit.dart | 상태 변화 정의 `increment()`, `decrement`
lib/counter/view/counter_view.dart | 상태 변화 호출 `context.read<CounterCubit>().increment()`, `context.read<CounterCubit>().decrement()`
lib/counter/counter.dart | counter 캡슐화


----------


#### 4. 소스코드 상세

##### lib/counter_observer.dart

`BlocObserver` 클래스를 상속받아 `CounterObserver` 클래스를 만들고 상태 변화를 감시하는 `onChange()`를 구현합니다.

```dart
import 'package:bloc/bloc.dart';

/// {@template counter_observer}
/// [BlocObserver] for the counter application which
/// observes all state changes.
/// {@endtemplate}
class CounterObserver extends BlocObserver {
  @override
  void onChange(BlocBase bloc, Change change) {
    super.onChange(bloc, change);
    print('${bloc.runtimeType} $change');
  }
}
```

----------


##### lib/main.dart

State를 감시할 위젯을 `BlocOverrides.runZoned()`로 감싸고 `lib/counter_observer.dart`에서 구현한 `CounterObserver()`를 감시할 위젯인 `RunApp`에 연결합니다.

`BlocOverrides.runZoned()`는 BLoC Package 8.0에 신규로 추가된 함수입니다
BLoC Package 8.0 이전과 이후의 비교는 [VERY GOOD VENTURES Blog](https://verygood.ventures/blog/bloc-v8-release)에서 확인하실 수 있습니다.
{: .notice--info}

```dart
import 'package:bloc/bloc.dart';
import 'package:flutter/widgets.dart';
import 'app.dart';
import 'counter_observer.dart';

void main() {
  BlocOverrides.runZoned(
    () => runApp(const CounterApp()),
    blocObserver: CounterObserver(),
  );
}
```

----------

##### lib/app.dart

`MaterialApp` 클래스를 `CouterApp` 클래스가 상속받아 `CounterPage()`를 Home으로 페이지 라우트합니다.

```dart
import 'package:flutter/material.dart';

import 'counter/counter.dart';

/// {@template counter_app}
/// A [MaterialApp] which sets the `home` to [CounterPage].
/// {@endtemplate}
class CounterApp extends MaterialApp {
  /// {@macro counter_app}
  const CounterApp({Key? key}) : super(key: key, home: const CounterPage());
}
```

----------


##### lib/counter/view/counter_page.dart

`BlocPrivider()`로 Business Logic인 `CounterCubit()`와 View인 `CounterView()`로 분리합니다.

```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';
import '../counter.dart';
import 'counter_view.dart';

/// {@template counter_page}
/// A [StatelessWidget] which is responsible for providing a
/// [CounterCubit] instance to the [CounterView].
/// {@endtemplate}
class CounterPage extends StatelessWidget {
  /// {@macro counter_page}
  const CounterPage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return BlocProvider(
      create: (_) => CounterCubit(),
      child: CounterView(),
    );
  }
}
```

----------


##### lib/counter/cubit/counter_cubit.dart

`CounterView()`에서 상태변화를 호출하면 `CounterCubit` 클래스의 호출된 함수가 상태를 변화시킵니다.

VSCode의 BLoC Extention을 통해 cubit을 생성하면 Cubit과 State가 함께 생성이 되는데, 이 예제에서는 state가 `int`이기 때문에 별도의 state 클래스가 없습니다.

```dart
import 'package:bloc/bloc.dart';

/// {@template counter_cubit}
/// A [Cubit] which manages an [int] as its state.
/// {@endtemplate}
class CounterCubit extends Cubit<int> {
  /// {@macro counter_cubit}
  CounterCubit() : super(0);

  /// Add 1 to the current state.
  void increment() => emit(state + 1);

  /// Subtract 1 from the current state.
  void decrement() => emit(state - 1);
}
```

----------

##### lib/counter/view/counter_view.dart

View에 UI를 그리고 state를 호출합니다. 이 예제에서는 아래와 같이 state를 호출하고 있습니다.

1. `BlocBuilder<CounterCubit, int>(... return Text($state) )`
2. `onPressed: () => context.read<CounterCubit>().increment(),`

```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';

import '../counter.dart';

/// {@template counter_view}
/// A [StatelessWidget] which reacts to the provided
/// [CounterCubit] state and notifies it in response to user input.
/// {@endtemplate}
class CounterView extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final textTheme = Theme.of(context).textTheme;
    return Scaffold(
      appBar: AppBar(title: const Text('Counter')),
      body: Center(
        child: BlocBuilder<CounterCubit, int>(
          builder: (context, state) {
            return Text('$state', style: textTheme.headline2);
          },
        ),
      ),
      floatingActionButton: Column(
        mainAxisAlignment: MainAxisAlignment.end,
        crossAxisAlignment: CrossAxisAlignment.end,
        children: <Widget>[
          FloatingActionButton(
            key: const Key('counterView_increment_floatingActionButton'),
            child: const Icon(Icons.add),
            onPressed: () => context.read<CounterCubit>().increment(),
          ),
          const SizedBox(height: 8),
          FloatingActionButton(
            key: const Key('counterView_decrement_floatingActionButton'),
            child: const Icon(Icons.remove),
            onPressed: () => context.read<CounterCubit>().decrement(),
          ),
        ],
      ),
    );
  }
}
```

----------


##### lib/counter/counter.dart

counter의 소스코드를 캡슐화합니다. `main.dart`에서는 `counter.dart`만 import하여 counter 관련 모든 소스코드를 import할 수 있습니다.

```dart
export 'cubit/counter_cubit.dart';
export 'view/counter_page.dart';
```


----------

플러터의 BLoC 디자인패턴에 관한 자세한 내용은 [BLOC Library 웹사이트](https://bloclibrary.dev/)에서 확인하실 수 있습니다.