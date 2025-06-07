

# File trigger\_composition.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**controller**](dir_449ae403f63c24360f06e13a33b5f84a.md) **>** [**trigger\_composition.cpp**](trigger__composition_8cpp.md)

[Go to the documentation of this file](trigger__composition_8cpp.md)


```C++


#include "argos_lib/controller/trigger_composition.h"

#include <algorithm>
#include <numeric>

namespace {
  frc2::Trigger Or(frc2::Trigger lhs, frc2::Trigger rhs) {
    return lhs || rhs;
  }
  frc2::Trigger And(frc2::Trigger lhs, frc2::Trigger rhs) {
    return lhs && rhs;
  }

  template <class InputIt>
  frc2::Trigger NoneOfIt(InputIt begin, InputIt end) {
    return !std::reduce(std::next(begin), end, *begin, Or);
  }

  template <class InputIt>
  frc2::Trigger AnyOfIt(InputIt begin, InputIt end) {
    return std::reduce(std::next(begin), end, *begin, Or);
  }

  template <class InputIt>
  frc2::Trigger AllOfIt(InputIt begin, InputIt end) {
    return std::reduce(std::next(begin), end, *begin, And);
  }

}  // namespace

frc2::Trigger argos_lib::triggers::OneOf(std::vector<frc2::Trigger> triggers) {
  if (triggers.size() == 1) {
    return triggers.front();
  }
  std::vector<frc2::Trigger> allExclusiveChecks;
  allExclusiveChecks.reserve(triggers.size());

  for (size_t exclusiveTrueIdx = 0; exclusiveTrueIdx < triggers.size(); ++exclusiveTrueIdx) {
    allExclusiveChecks.emplace_back(triggers.at(exclusiveTrueIdx));
    for (size_t otherIdx = 0; otherIdx < triggers.size(); ++otherIdx) {
      if (exclusiveTrueIdx != otherIdx) {
        auto tempTrigger = allExclusiveChecks.back() && !triggers.at(otherIdx);
        std::swap(allExclusiveChecks.back(), tempTrigger);
      }
    }
  }

  return std::reduce(std::next(allExclusiveChecks.begin()), allExclusiveChecks.end(), *allExclusiveChecks.begin(), Or);
}

frc2::Trigger argos_lib::triggers::NoneOf(std::vector<frc2::Trigger> triggers) {
  return NoneOfIt(triggers.begin(), triggers.end());
}

frc2::Trigger argos_lib::triggers::AnyOf(std::vector<frc2::Trigger> triggers) {
  return AnyOfIt(triggers.begin(), triggers.end());
}

frc2::Trigger argos_lib::triggers::AllOf(std::vector<frc2::Trigger> triggers) {
  return AllOfIt(triggers.begin(), triggers.end());
}
```


