

# File panel.h

[**File List**](files.md) **>** [**argos\_lib**](dir_f9cbf5730473812e84551a5945ef39f8.md) **>** [**include**](dir_0330651415bf66743a1cd99e3d0db0bc.md) **>** [**argos\_lib**](dir_934baf9e7d2bb4710ca41f9f25ef3ea4.md) **>** [**led**](dir_92b511606ba5c2da7e2dda655454d24f.md) **>** [**panel.h**](panel_8h.md)

[Go to the documentation of this file](panel_8h.md)


```C++


#pragma once

#include <frc/AddressableLED.h>

#include <algorithm>
#include <vector>

namespace argos_lib {
  namespace led {
    template <typename T>
    class Array2D {
     public:
      Array2D() = delete;
      Array2D(unsigned width, unsigned height, T fillValue = {}) : m_cells(width, std::vector<T>(height, fillValue)) {}

      T& at(unsigned x, unsigned y) { return m_cells.at(x).at(y); }

      const T& at(unsigned x, unsigned y) const { return m_cells.at(x).at(y); }

      unsigned Width() const noexcept { return m_cells.size(); }

      unsigned Height() const noexcept {
        try {
          return m_cells.at(0).size();
        } catch (const std::out_of_range&) {
          // Handle empty vector even though this shouldn't ever happen with deleted default constructor
          return 0;
        }
      }

     private:
      std::vector<std::vector<T>>
          m_cells;  
    };

    using Panel = Array2D<frc::AddressableLED::LEDData>;  
    using Mask = Array2D<float>;  

    using Strip = std::vector<frc::AddressableLED::LEDData>;

    enum class PrimaryScanDirection { Vertical, Horizontal };

    enum class FirstPixelPosition { TopRight, TopLeft, BottomLeft, BottomRight };

    struct PanelScanParams {
      FirstPixelPosition firstPixel;       
      PrimaryScanDirection scanDirection;  
    };

    Strip Serialize(const Panel& panel, const PanelScanParams& params);

  }  // namespace led
}  // namespace argos_lib
```


