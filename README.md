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
