# Linear-Quadratic Regulator(LQR) Controller

The theory of optimal control is concerned with operating a dynamic system at minimum cost. The case where the system dynamics are described by a set of linear differential equations and the cost is described by a quadratic function is called the LQ problem. One of the main results in the theory is that the solution is provided by the **linear–quadratic regulator** (**LQR**).

The settings of a (regulating) controller governing either a machine or process (like an airplane or chemical reactor) are found by using a mathematical algorithm that minimizes a cost function with weighting factors needed to be supplied. A **cost function** is a function that maps an event or values of one or more variables onto a real number intuitively representing some "cost" associated with the event. The cost function is often defined as a sum of the deviations of key measurements, like altitude or process temperature, from their desired values. The algorithm thus finds those controller settings that minimize undesired deviations. The magnitude of the control action itself may also be included in the cost function.

#### Finite horizon LQR

For a continuous-time linear system, defined on $t \epsilon [t_0,t_1]$ , described by:<br><br>
$\dot{x} = Ax + Bu$<br><br>


with a quadratic cost function defined as:
$J = x^T (t_1)F(t_1)x(t_1) + \int_{t_0}^{t_1} (x^TQx + u^TRu + 2x^TNu) \,dt$<br><br>
the feedback control law that minimizes the value of the cost is:<br><br>
$u = -Kx$<br><br>
where K is given by:<br><br>
$K = R^{-1}(B^TP(t) + N^t)$<br><br>
and P is found by solving the continuous time [Riccati differential equation](https://en.wikipedia.org/wiki/Riccati_differential_equation):<br><br>
$A^TP(t) + P(t)A - (P(t)B+N)R^{-1}(B^TP(t) + N^T) + Q = - \dot{P}(t)$<br><br>
with the boundary condition:<br><br>
$P(t_1)=F(t_1)$


To learn more in detail about LQR controller watch [this](https://www.youtube.com/watch?v=1_UobILf3cc&list=RDCMUCm5mt-A4w61lknZ9lCsZtBw&start_radio=1&t=7) video by Steve Brunton

#### Linear Quadratic Gaussian (LQG) control theory

Here, Given a linear model of the plant in a statespace description, and assuming that the disturbance and measurement noise are Gaussian stochastic processes with known power spectral densities, the designer translates the design specifications into a quadratic performance criterion consisting of some state variables and control signal inputs. The object of design then is to minimize the performance criterion by using appropriate state or measurement feedback controllers while guaranteeing the closed-loop stability. When LQG controller problem is solved in a deterministic setting, known as an  H<sub>2</sub> optimal control problem, in which the H<sub>2</sub> norm of a certain transfer function from an exogenous disturbance to a pertinent controlled output of a given plant is minimized by appropriate use of an internally stabilizing controller.

To learn about robust controllers and LQG control problem in detail watch [this](https://www.youtube.com/watch?v=7OZVbqPQ2Zw) video

**H∞** (i.e. "**H-infinity**") **methods** are used in control theory to synthesize controllers to achieve stabilization with guaranteed performance. To use *H*∞ methods, a control designer expresses the control problem as a mathematical optimization problem and then finds the controller that solves this optimization. *H*∞ techniques have the advantage over classical control techniques in that *H*∞ techniques are readily applicable to problems involving multivariate systems with cross-coupling between channels.

Read [this]() material from MIT Open Courseware  to know about H∞ methods in more detail.

