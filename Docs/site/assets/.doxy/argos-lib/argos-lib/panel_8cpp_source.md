

# File panel.cpp

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**cpp**](dir_cf4b00708d9639a2579b4441eb30ca52.md) **>** [**led**](dir_42b5fa11a77a8b77390e65f20483b7fe.md) **>** [**panel.cpp**](panel_8cpp.md)

[Go to the documentation of this file](panel_8cpp.md)


```C++


#include "argos_lib/led/panel.h"

argos_lib::led::Strip argos_lib::led::Serialize(const argos_lib::led::Panel& panel,
                                                const argos_lib::led::PanelScanParams& params) {
  unsigned width = panel.Width();
  unsigned height = panel.Height();
  Strip serializedStrip(width * height);  // Allocate memory once

  // Each case is a little different, but if you consider the TopRight, Horizontal case, addressing
  // looks like this in a 4x3 panel
  //     ________________
  //  V |  3   2   1   0 | <
  //  > |  4   5   6   7 | V
  //    | 11  10   9   8 | <
  //     ----------------
  //
  // Notice consistent scan direction in secondary scan direction (vertical down), but alternating
  // direction in the primary scan direction (horizontal starting left) on adjacent rows.

  switch (params.firstPixel) {
    case FirstPixelPosition::TopRight:
      if (PrimaryScanDirection::Horizontal == params.scanDirection) {
        unsigned stripIndex = 0;
        for (unsigned y = height; y > 0; --y) {
          for (unsigned x = width; x > 0; --x) {
            serializedStrip[stripIndex++] = panel.at(y % 2 == 0 ? x - 1 : width - x, y - 1);
          }
        }
      } else {
        unsigned stripIndex = 0;
        for (unsigned x = width; x > 0; --x) {
          for (unsigned y = height; y > 0; --y) {
            serializedStrip[stripIndex++] = panel.at(x - 1, x % 2 == 0 ? y - 1 : height - y);
          }
        }
      }
      break;
    case FirstPixelPosition::TopLeft:
      if (PrimaryScanDirection::Horizontal == params.scanDirection) {
        unsigned stripIndex = 0;
        for (unsigned y = height; y > 0; --y) {
          for (unsigned x = 0; x < width; ++x) {
            serializedStrip[stripIndex++] = panel.at(y % 2 == 0 ? x : width - x - 1, y - 1);
          }
        }
      } else {
        unsigned stripIndex = 0;
        for (unsigned x = 0; x < width; ++x) {
          for (unsigned y = height; y > 0; --y) {
            serializedStrip[stripIndex++] = panel.at(x, x % 2 == 0 ? y - 1 : height - y);
          }
        }
      }
      break;
    case FirstPixelPosition::BottomLeft:
      if (PrimaryScanDirection::Horizontal == params.scanDirection) {
        unsigned stripIndex = 0;
        for (unsigned y = 0; y < height; ++y) {
          for (unsigned x = 0; x < width; ++x) {
            serializedStrip[stripIndex++] = panel.at(y % 2 == 0 ? x : width - x - 1, y);
          }
        }
      } else {
        unsigned stripIndex = 0;
        for (unsigned x = 0; x < width; ++x) {
          for (unsigned y = 0; y < height; ++y) {
            serializedStrip[stripIndex++] = panel.at(x, x % 2 == 0 ? y : height - y - 1);
          }
        }
      }
      break;
    case FirstPixelPosition::BottomRight:
      if (PrimaryScanDirection::Horizontal == params.scanDirection) {
        unsigned stripIndex = 0;
        for (unsigned y = 0; y < height; ++y) {
          for (unsigned x = width; x > 0; --x) {
            serializedStrip[stripIndex++] = panel.at(y % 2 == 0 ? x - 1 : width - x, y);
          }
        }
      } else {
        unsigned stripIndex = 0;
        for (unsigned x = width; x > 0; ++x) {
          for (unsigned y = 0; y < height; ++y) {
            serializedStrip[stripIndex++] = panel.at(x - 1, x % 2 == 0 ? y : height - y - 1);
          }
        }
      }
      break;
  }
  return serializedStrip;
}
```


