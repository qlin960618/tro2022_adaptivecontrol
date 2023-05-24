# Adaptive Constrained Kinematic Control using Partial or Complete Task-Space Measurements

Sample code and minimal example for [our TRO2022 paper](https://doi.org/10.1109/TRO.2022.3181047): 

```bib
@Article{marinhoandadorno2022adaptive,
  author       = {Marinho, M. M. and Adorno, B. V.},
  title        = {Adaptive Constrained Kinematic Control using Partial or Complete Task-Space Measurements},
  journal      = {IEEE Transactions on Robotics (T-RO)},
  year         = {2022},
  month        = dec,
  doi          = {10.1109/TRO.2022.3181047},
  url          = {https://arxiv.org/pdf/2109.06375.pdf},
  url_video    = {https://youtu.be/WntmyJe53gY},
  custom_type  = {1. Journal Paper},
  volume       = {38},
  number       = {6},
  pages        = {3498--3513}
}
```

# Tested on

- Ubuntu 22.04 `5.19.0-41-generic #42~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Tue Apr 18 17:40:00 UTC 2 x86_64 x86_64 x86_64 GNU/Linux`
- CoppeliaSim EDU 5.4.1 (rev4)
- DQ Robotics cpp [`commit 77acf9a42875ffb69e9f48f98f3950f9d7242c0e`](https://github.com/dqrobotics/cpp/commit/77acf9a42875ffb69e9f48f98f3950f9d7242c0e)
- DQ Robotics cpp-interface-vrep [`commit 67a5839074243e262de3a6c83439dc3a59492913`](https://github.com/dqrobotics/cpp-interface-vrep/commit/67a5839074243e262de3a6c83439dc3a59492913)
- DQ Robotics cpp-interface-qpoases [`commit cdc2d6cbc6d67074267c38227b85bb1f14df8b14`](https://github.com/dqrobotics/cpp-interface-qpoases/commit/cdc2d6cbc6d67074267c38227b85bb1f14df8b14)
- qpOASES [`commit 0b86dbf00c7fce34420bedc5914f71b176fe79d3`](https://github.com/coin-or/qpOASES/commit/0b86dbf00c7fce34420bedc5914f71b176fe79d3)
- sas_core [`commit 696b2019c30d62e322030eec8a0c2bb2f3f7b3c8`](https://github.com/SmartArmStack/sas_core/commit/696b2019c30d62e322030eec8a0c2bb2f3f7b3c8)

# Installation

## Just in case

```bash
sudo apt install g++ cmake git
```

## DQ Robotics Development 

```bash
sudo add-apt-repository ppa:dqrobotics-dev/development
sudo apt-get update
sudo apt-get install libdqrobotics*
```

## qpOASES

```bash
cd ~/Downloads
git clone https://github.com/coin-or/qpOASES.git
cd qpOASES
sed -i -e 's/option(BUILD_SHARED_LIBS "If ON, build shared library instead of static" OFF)/option(BUILD_SHARED_LIBS "If ON, build shared library instead of static" ON)/g' CMakeLists.txt
mkdir build
cd build
cmake ..
make -j16
sudo make install
sudo ldconfig
```

## Download the repo

```bash
cd ~
mkdir git
cd git
git clone https://github.com/mmmarinho/tro2022_adaptivecontrol.git --recursive
```

# Build

With all dependencies correctly configured,

```bash
cd ~/git/tro2022_adaptivecontrol
mkdir build
cd build
cmake ..
make -j16
```

