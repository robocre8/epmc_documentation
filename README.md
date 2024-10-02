## Easy PID Motor Controller (EPMC) User Documentation
Imagine sending actual angular speed commands (not PWM commands) to your DC motor and seeing it running at that commanded speed. This is exactly what the **`Easy PID Motor Controller`** (**`EPMC`**) helps you to accomplish.
</br></br>
It is an **easy-to-use** digital **PID** motor controller system for controlling the **angular speed** of **geared DC motors** with **quadrature encoders** via **angular speed commands** in **rad/sec** rather than the traditional PWM commands. It consists of a motor driver (i.e. `L298N Driver IC` or any other motor driver that can be controlled using the Arduino PWM), an `ATmega328 microcontroller`, and a `GUI Application` that enables one to control motors easily and set up motor PID parameters.
</br></br>
It also provides a `USB serial and I2C communication interface` with `ROS2`, `Arduino`, `Python`, and `Cpp` libraries for easy interfacing with one's preferred project.

> Short test video

> [!NOTE]
> **`L298N EPMC Module`** is the main EPMC product. It consists of the L298N Driver IC and an ATmega328 microcontroller.
> 
> **`Custom EPMC Interface Board`** can also be made for other motor drivers (as long as they can control motor speed using the Arduino PWM). This may be due to the higher current requirement of the motor you intend to use for your project which the L298N (i.e. `L298N EPMC Module`) cannot provide. If you need a solution like that you can contact me from my [website]() or via [LinkedIn]()
> 
> It can easily be used by robotics or ROS hobbyists, students, learners, researchers, engineers, etc.

> Picture explaining the L298N EPMC Module
> 
> Picture explaining the concept of the custom EPMC Interface board.
#

#### THE COMMON MOTOR SPEED CONTROL PROBLEM (The Traditional PWM Approach)
Whether you are a hobbyist, maker, engineer, student, or researcher, you usually would opt to control the speed of a DC Motor using PWM Commands from a microcontroller (e.g. Arduino UNO, etc.) using a motor driver like the L298N Driver Module (or any other motor driver module).
</br></br>
While this control method is simple and easy, the only drawback of this control style is that it is an open-loop control and does not allow you to command a desired angular speed easily. This generally poses a lot of limitations in their uses, especially in more advanced robotics (e.g. wheeled mobile robotics) projects requiring precise speed controls.
</br></br>
To achieve precise angular speed control with this traditional PWM control style, one would need to understand quite a bit of control theory and signal processing calculations, write more control and signal processing code, and possibly add an extra layer of circuitry, all of which can become cumbersome and might not be easy to integrate into one’s desired project. All these require a good level of control expertise.

#

The **`Easy PID Motor Controller (EPMC)`** easily solves and abstracts all these problems so you can focus more on building your projects with good controls being made readily available.
> [!IMPORTANT]
> In summary, the **`Easy PID Motor Controller (EPMC)`** provides the following:
> * Easy interfacing with a **geared DC motor** with a **quadrature encoder**.
> * Easy setting up of PID control parameter gain for the interfaced motor via its GUI application - [epmc_setup_application]().
> * Easy motor angular speed commands in rad/sec (not PWM) and getting feedback on the motor’s actual angular position and angular speed.
> * Easy integration with `ROS2` (microcomputer or PC) projects with its ROS2 control package - [epmc_ros2_control]().
> * Easy integration with `Arduino` projects with its I2C library - [epmc_arduino]().
> * Easy integration with a microcomputer-based (`Python` or `Cpp`) project with its [epmc_python]() and [epmc_cpp]() library.

#

#### The Easy PID Motor Controller (L298N EPMC MODULE) SPECIFICATION
> Picture showing part labels

* Recommended Supply Voltage – 7v to 12v
* Motor Output Supply Current (Max) – 2A (i.e. should be used with geared DC motors whose stall current is not greater than 2A or 2.5A)
* Communication Interface - `USB Serial` and `I2C`
* Easily integrates with `ROS2` and `Arduino` (as well as `Python` and `Cpp`) projects.
* `Angular speed commands` are in **rad/sec**.
* `Angular speed feedback` in **rad/sec**.
* `Angular position feedback` in **radians**.

#

#### Easy PID Motor Controller APPLICATIONS
* Robotics (Arduino, ROS2, Python, and C++)
* Precise Motor Speed Control

#

#### Easy PID Motor Controller USAGE GUIDE SUMMARY
* Get/Purchase the **L298N EPMC MODULE** (or a **Custom EPMC Interface Board**)
> [!NOTE]
> The **L298N EPMC MODULE** (or a **Custom EPMC Interface Board**) is available on **`Pre-order`**.
> Please reach out to me via [LinkedIn]() or through my [Contact]() page.
* Interface the geared DC motors with quadrature encoder to the **L298N EPMC MODULE** (or the **Custom EPMC Interface Board**).
* Download and run the **EPMC Setup Application** to set up the encoder parameter and PID gains for the interfaced geared DC motor with quadrature encoder. You will be able to visualize the result - [tutorial]()
* Use it in your **ROS2** project - [tutorial]()
* Use it in your **Arduino** project - [tutorial]()
* Use it in your **Python** project - [tutorial]()
* Use it in your **Cpp** project - [tutorial]()

#

#### LIBRARIES THAT MADE THE Easy PID Motor Controller PROJECT POSSIBLE
Check out these Github repos of libraries that went a long way in developing the `Easy PID Motor Controller ATmega328 microcontroller computational system`. You can use them in your projects also (Ensure to star them).
* [simple_pid_control]() - PID Arduino library based on the [PID control series]() by Prof. Kelvin Lynch of Northwestern Robotics, developed by samuko-things.
* [adaptive_lowpass_filter]() - Arduino code for implementing one and two-order lowpass filter in your Arduino signal processing project/code by [Curio Res](). Also, check out how I made use of it to create an Arduino library - [samuko filter code]().
* [quadrature_encoder_velocity_and_position_calculation]() - sample Arduino code on how to compute rotational velocity and position with a quadrature encoder, developed by samuko-things.
* [Serial_comm_pyserial_and_arduino]() - a backend-API-style serial communication code between Pyserial and Arduino that can be adapted to any project, developed by samuko-things.
