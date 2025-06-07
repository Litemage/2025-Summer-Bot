

# File compile\_time\_member\_check.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**config**](dir_297090c629331b6211a5a9bae4ee7118.md) **>** [**compile\_time\_member\_check.h**](compile__time__member__check_8h.md)

[Go to the documentation of this file](compile__time__member__check_8h.md)


```C++


#pragma once

#include <type_traits>

#define HAS_MEMBER(X)                    \
  template <typename T, typename = void> \
  struct has_##X : std::false_type {};   \
  template <typename T>                  \
  struct has_##X<T, decltype((void)T::X, void())> : std::true_type {};
```


