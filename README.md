  Шаблонный контейнер `Vector<T>` в одном заголовочном файле `advanced-vector/vector.h`.
  Управление памятью вынесено в отдельный класс `RawMemory<T>`, что отделяет
  выделение сырой памяти от конструирования и разрушения объектов.

  ## Возможности

  - Правило пяти: копирование, перемещение, копирующее и перемещающее присваивание, деструктор
  - `Size`, `Capacity`, `Reserve`, `Resize`
  - `PushBack` (lvalue/rvalue), `EmplaceBack`, `PopBack`, `Emplace`, `Insert`, `Erase`
  - Итераторы (`begin/end/cbegin/cend`), `operator[]` в const- и не-const версиях

  ## Реализованные приёмы

  - Ручная работа с неинициализированной памятью: placement-new, `std::uninitialized_*`, `std::destroy_*`
  - Выбор перемещения или копирования при реаллокации через `if constexpr` и type traits
  - Строгая гарантия безопасности исключений в `Reserve`, `EmplaceBack`, `Emplace`
  - Perfect forwarding, вычисляемые `noexcept`, идиома copy-and-swap

  ## Сборка

  Заголовочник самодостаточен, требуется C++17. Тестовый код — в `advanced-vector/main.cpp`.
