# Model Based Controllers

 Model-based control uses information about the dynamics of the system's structure and its behavior in time to obtain a better control result regarding stability and performance of the controlled system. Take the following simple example:

Let $\frac{d^2x}{dt^2}= f(x)+u$

be the system to be controlled, where x - state vector, f(x) - nonlinear vector function, u - control vector. Suppose we have some estimation est(x) than we use a control law like <br><br>
$u = -est(x)+u_{st}$<br><br>
where u<sub>st</sub> be some maybe linear PID control law<br><br>
$u_{st} = K_px + K_d\frac{dx}{dt} + K_i\int xdt$<br><br>
So we get<br><br>
$\frac{d^2x}{dt^2} = \Delta f + K_px + K_d\frac{dx}{dt} + K_i\int xdt$<br><br>
where <br><br>
$\Delta f =f(x) - est(x)$<br><br>
If the model uncertainties are small enough we get a linear system with a disturbance Delta f which can be stabilized using appropriate control gains K<sub>p</sub>, K<sub>d</sub>, K<sub>I</sub>. Above given is just an example of model based controller in real life model based controller are way more complex than this.

**Model Predictive Control(MPC)** is the most widely known model based controller. Model Predictive Controllers rely on the dynamic models of the process, most often linear empirical models obtained by system identification.

Model predictive control offers several important advantages: 

(1) the process model captures the dynamic and static interactions between input, output, and disturbance variables, 

(2) constraints on inputs and outputs are considered in a systematic manner, 

(3) the control calculations can be coordinated with the calculation of optimum set points, and 

(4) accurate model predictions can provide early warnings of potential problems.

The mathematics and concepts involved in MPC are a bit complex and require a decent understanding of mathematics of control theory. 

To study more about MPC controller read [this](http://folk.ntnu.no/skoge/vgprosessregulering/papers-pensum/seborg-c20ModelPredictiveControl.pdf) material by NTNU 

You can also check [this](https://www.youtube.com/watch?v=YwodGM2eoy4) video by Steve Brunton to get a more detailed idea

Some of the other resources you should check to understand control theory and various controllers in more detail are:

1. Control Bootcamp [playlist](https://www.youtube.com/playlist?list=PLMrJAkhIeNNR20Mz-VpzgfQs5zrYi085m) by Steve Brunton
2. Control Systems [Lectures](https://www.youtube.com/user/ControlLectures) by Brian Douglas
3. Control of Mobile Robots [course](https://www.my-mooc.com/en/mooc/control-of-mobile-robots/) by Georgia Tech University on Coursera
4. Modern Robotics - Mechanical, Planning and Control by Kevin.M.Lynch and Frank.C.Park
5. MIT Courseware Control Theory [Notes](https://ocw.mit.edu/courses/mechanical-engineering/2-017j-design-of-electromechanical-robotic-systems-fall-2009/lecture-notes/MIT2_017JF09_control.pdf)

