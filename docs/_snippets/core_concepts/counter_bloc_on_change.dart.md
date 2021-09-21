```dart
abstract class CounterEvent {}

class CounterIncremented extends CounterEvent {}

class CounterBloc extends Bloc<CounterEvent, int> {
  CounterBloc() : super(0) {
    on<CounterIncremented>((event, emit) => emit(state + 1));
  }

  @override
  void onChange(Change<int> change) {
    super.onChange(change);
    print(change);
  }
}
```