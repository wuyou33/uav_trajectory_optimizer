# Trajectory Optimizer for UAVs #

Solvers used in the paper **Real-Time Planning with Multi-Fidelity Models for Agile Flights in Unknown Environments** (ICRA 2019) ([pdf](https://arxiv.org/abs/1810.01035), [video](https://www.youtube.com/watch?v=E4V2_B8x-UI))

```
@article{tordesillas2018real,
  title={Real-Time Planning with Multi-Fidelity Models for Agile Flights in Unknown Environments},
  author={Tordesillas, Jesus and Lopez, Brett T and Carter, John and Ware, John and How, Jonathan P},
  journal={arXiv preprint arXiv:1810.01035},
  year={2018}
}
```

Two videos of the trajectories generated by these solvers are available here:

Video 1                    |  Video 2
:-------------------------:|:-------------------------:
[![ICRA 2019: Real-Time Planning with Multi-Fidelity Models for Agile Flights in Unkonwn Environments](https://img.youtube.com/vi/E4V2_B8x-UI/0.jpg)](https://www.youtube.com/watch?v=E4V2_B8x-UI "ICRA 2019: Real-Time Planning with Multi-Fidelity Models for Agile Flights in Unkonwn Environments")  |  [![Trajectory Generation for UAVs using CVXGEN](https://img.youtube.com/vi/VX9n68GTqRQ/0.jpg)](https://www.youtube.com/watch?v=VX9n68GTqRQ "Trajectory Generation for UAVs using CVXGEN")



### Introduction:

This is a highly efficient solver to generate trajectories for UAVs. It's basically a C++ wrapper for the C code generated by CVXGEN to solve the optimization problem to generate trajectories for UAVs. 

It includes three solvers to solve for:

* **Velocity-Controlled Trajectories**: State is position.
* **Acceleration-Controlled Trajectories**: States are position and velocity.
* **Jerk-Controlled Trajectories**: States are position, velocity and acceleration,


### Instructions:
Clone this repository:
```
git clone https://github.com/jtorde/uav_trajectory_optimizer.git
```
Now compile the cvxgen code: By default, the compiler will use the option `-Os` for the CVXGEN code. If you want the maximum performance, change it to `-O3` in the Makefile inside the folders cvxgen_*
```
cd uav_trajectory_optimizer
chmod +x setup.sh 
./setup.sh
```
Then compile the c++ wrapper:

```
catkin config -DCMAKE_BUILD_TYPE=Release
catkin build
```

And finally execute the example:
```
./build/cvx/cvx_exec
```

### License
Academic license - for non-commercial use only


