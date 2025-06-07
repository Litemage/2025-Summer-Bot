

# File log.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**general**](dir_ce90de3a31c0930a75a0088390301e44.md) **>** [**log.h**](log_8h.md)

[Go to the documentation of this file](log_8h.md)


```C++


/*
  Contains functions / classes useful for logging runtime information
*/

#pragma once

#include <cstdarg>
#include <iostream>
#include <string>

#include "units/base.h"

namespace argos_lib {
  enum LogLevel { INFO, ERR };

  class ArgosLogger {
   public:
    ArgosLogger() = delete;
    explicit ArgosLogger(std::string tag) : m_tag{tag} {}

    void Log(LogLevel level, const char* fmt, ...) const {
      va_list lst;
      va_start(lst, fmt);
      switch (level) {
        case LogLevel::INFO:
          std::fprintf(stdout, "[%s]", m_tag.c_str());
          std::vfprintf(stdout, fmt, lst);
          break;

        case LogLevel::ERR:
          std::fprintf(stderr, "[%s_ERROR]", m_tag.c_str());
          std::vfprintf(stderr, fmt, lst);
          break;

        default:
          std::fprintf(stdout, "[%s]", m_tag.c_str());
          std::vfprintf(stdout, fmt, lst);
          break;
      }
      std::fprintf(stdout, "\n");
    }

   private:
    std::string m_tag;
  };
}  // namespace argos_lib
```


