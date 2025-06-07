

# File assertions.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**testing**](dir_4b5bf1f302d4aefee80cb53d26fbb3eb.md) **>** [**assertions.h**](assertions_8h.md)

[Go to the documentation of this file](assertions_8h.md)


```C++


#pragma once

#include <fmt/format.h>
#include <gtest/gtest.h>
#include <units/math.h>

namespace argos_lib {
  namespace testing {

    template <class UnitTypeLhs, class UnitTypeRhs, class UnitTypeTol>
    ::testing::AssertionResult UnitEqual(UnitTypeLhs actual, UnitTypeRhs expected, UnitTypeTol tolerance) {
      if (units::math::abs(actual - expected) < tolerance) {
        return ::testing::AssertionSuccess();
      }
      return ::testing::AssertionFailure()
             << fmt::format("{:.4f} not within {:.4f} of expected {:.4f}", actual, tolerance, expected);
    }

    template <class UnitTypeLhs, class UnitTypeRhs>
    ::testing::AssertionResult UnitEqual(UnitTypeLhs actual, UnitTypeRhs expected) {
      return UnitEqual(actual, expected, decltype(actual)(0.001));
    }

  }  // namespace testing
}  // namespace argos_lib
```


