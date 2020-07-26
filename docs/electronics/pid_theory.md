# PID Controllers

PID controller stands for **Proportional-Integral-Derivative** and it is one of the most commonly used controller and used in a variety of industrial applications. 
The reason for its most widely usage is because of its robust performance and its functional simplicity, which allows engineers to operate them in a simple,straightforward manner.

It consists of three coefficients;proportional, integral and derivative coefficient which are tweaked to to get the optimal response of the controller.

The signal that is input into process h(t) can be represented as:
h(t) = K_p (t)e(t) + K_i ∫_0 ^t e (φ)dφ + K_d de(t)/dt

### Let's see what does each response mean-

## Proportional Response:
The proportional component depends only on the difference between the set point and the process variable. This difference is referred as the *Error term* .
The proportional gain **(Kc)** determines the ratio of output response to the error signal. For instance, if the error term has a magnitude of 10, a proportional gain of 5 would produce a proportional response of 50.
 In general, increasing the proportional gain will increase the speed of the control system response. 
However, keeping a very large Kc might induce oscillations in the system and add to the instability of the system.

## Integral Response :
It sums up the error over time. The result is that even a small error term will cause the integral component to inccrease slowly.The integral response will continually increase overtime unless the error is zero,so the effect is to drive the Steady-State error to zero.
**Steady-State** error is the final difference between the process variable and set point.A phenomenon called integral windup results when integral action saturates a controller without the controller driving the error signal towards zero.

## Derivative Response :
The derivative response causes the output to decrease if the process variable is increasing rapidly.The derivative response is proportional to the rate of change of the process variable.Increasing the *derivative time* (Td) parameter will cause the control system to react more strongly to changes in the error term and will increase the speed of the overall control system response.
However,the most practical control systems use very small derivative time, because these are highly to noise in the porcess variable signals as a result of which it can make the control system unstable.

Let's see the block diagram of a PID controller:

![pid controller](https://ni.scene7.com/is/image/ni/12fbdcae1638?scl=1)

Refer to [this](https://www.youtube.com/watch?v=wkfEZmsQqiA&list=PLn8PRpmsu08pQBgjxYFXSsODEF3Jqmm-y) playlist by mathworks to get a more detailed insight into how the PID controller works.The first video gives a nice brief overview.Along with this,checkout [this](https://www.youtube.com/watch?v=XfAt6hNV8XM) video for a bunch of real life use cases of PID.

Now let's talk about an example where we can apply the concept of the PID that we have studied across.
Consider a situation where you want your robot to turn to a specific angle.The only control you have over your robot is a turn signal(like a throttle).We have provided with a rough **pseudo code** as an example on how a person can implement a simple PID control.

`PID_Control(bot,goal,Kp,KiKd)`

`{`

	* Initialize error_prev = goal - bot.theta

	* Initialize error_int = 0

	* Loop:

	  > Set error = goal - bot.theta

	  > Update error_int = error_int + error

	  > Set error_dvt = error-error_prev

	  > Set uKp*error + Ki*error_int + Kd*error_dvt

	  > Execute bot.turn_control(u)

	  > Set error_prev = e

`}`

You can see that the error is just the difference between our desired state and the
current state. And we don’t really sit around calculating the derivative or integral,
instead we use crude but effective approximations. The derivative is taken as the
difference between the current and previous error and the integral is just the sum of all
errors up to the current point. You could go one step further and use dt (a small
constant) in calculating derivative and integral. Once you have an approximation for the
three terms, you take their sum (weighted with their respective constants) as the signal
that you want to provide to the robot.

The values Kp,Ki and Kd can be tweaked by the designer of the controller which is us, in this case.
In general, the optimum values of Ki,Kp and Kd are found using trial and error.
A recommended way to go about doing this is to first keep Ki and Kd zero and find a near optimum value.
Then you could introduce the other two components one by one.

For a detailed tutorial on the topic, have look at [this](https://w3.cs.jmu.edu/spragunr/CS354_F17/handouts/pid.pdf) document.