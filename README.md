## thunder_line_follower_pmr3100 (noetic) - 0.1.1-1

The packages in the `thunder_line_follower_pmr3100` repository were released into the `noetic` distro by running `/usr/bin/bloom-release --rosdistro noetic --track noetic thunder_line_follower_pmr3100 --edit` on `Thu, 24 Jun 2021 08:26:50 -0000`

The `thunder_line_follower_pmr3100` package was released.

Version of package(s) in repository `thunder_line_follower_pmr3100`:

- upstream repository: https://github.com/ThundeRatz/thunder_line_follower_pmr3100.git
- release repository: unknown
- rosdistro version: `null`
- old version: `null`
- new version: `0.1.1-1`

Versions of tools used:

- bloom version: `0.10.7`
- catkin_pkg version: `0.4.23`
- rosdep version: `0.20.1`
- rosdistro version: `0.8.3`
- vcstools version: `0.1.42`


# 🚗 Modelo de seguidor de linha

Modelo de simulação de um seguidor de linha simples

## ⏯ Intro

Para executar a simulação, utilize:

```bash
roslaunch thunder_line_follower_pmr3100 gazebo.launch
```

## Dependências

Para instalar ROS e Gazebo (no Linux), utilize o comando

```bash
sudo apt install ros-noetic-desktop-full
```

O projeto precisa da biblioteca **velocity_controllers** dentro do [ros_controllers](https://github.com/ros-controls/ros_controllers) e da biblioteca python [pygame](https://github.com/pygame/pygame). Ambos podem ser instalados com ```apt```

```bash
sudo apt install ros-noetic-velocity-controllers python-pygame
```

Ou com ```rosdep```

```bash
rosdep install thunder_line_follower_pmr3100
```

## 🎨 Cores do Gazebo

Para uma lista completa das cores disponíveis, veja o [script OGRE](https://bitbucket.org/osrf/gazebo/src/gazebo11/media/materials/scripts/gazebo.material) do repo oficial.
