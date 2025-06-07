

# File interpolation.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**interpolation.h**](interpolation_8h.md)

[Go to the documentation of this file](interpolation_8h.md)


```C++


#pragma once

#include <algorithm>
#include <array>

namespace argos_lib {

  template <class T, class V>
  struct InterpMapPoint {
    T inVal;
    V outVal;

    constexpr InterpMapPoint(T in, V out) : inVal(in), outVal(out) {}

    constexpr bool operator<(const InterpMapPoint<T, V>& other) { return inVal < other.inVal; }
    constexpr bool operator==(const InterpMapPoint<T, V>& other) { return inVal == other.inVal; }
  };

  template <class T, class V>
  constexpr bool operator<(const InterpMapPoint<T, V>& a, const T& b) {
    return a.inVal < b;
  }

  template <class T, class V>
  constexpr bool operator<(const T& a, const InterpMapPoint<T, V>& b) {
    return a < b.inVal;
  }

  template <class T, int size, class V = T>
  class InterpolationMap {
   public:
    InterpolationMap() = delete;
    constexpr InterpolationMap(std::array<InterpMapPoint<T, V>, size> initArray) : m_mapArray(initArray) {
      // assert(("Map must contain at least one value.", !initArray.empty()));
      // assert(("Map values must be sorted.", std::is_sorted(initArray.cbegin(), initArray.cend())));
    }

    constexpr V Map(const T inVal) const {
      if (inVal >= m_mapArray.back().inVal) {
        return m_mapArray.back().outVal;
      } else if (inVal <= m_mapArray.front().inVal) {
        return m_mapArray.front().outVal;
      } else {
        auto afterPoint{std::lower_bound(m_mapArray.cbegin(), m_mapArray.cend(), inVal)};
        auto beforePoint{std::prev(afterPoint)};
        const auto lerpPct = (inVal - beforePoint->inVal) / (afterPoint->inVal - beforePoint->inVal);
        return beforePoint->outVal + lerpPct * (afterPoint->outVal - beforePoint->outVal);
      }
    }

    constexpr V operator()(const T inVal) const { return Map(inVal); }

   private:
    std::array<InterpMapPoint<T, V>, size> m_mapArray;
  };

}  // namespace argos_lib
```


