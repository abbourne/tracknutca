+++
author = "bill-bourne"
comments = true
date = "2016-03-05T17:28:15-05:00"
draft = true
image = ""
menu = ""
share = true
tags = ["physics"]
title = "The Physics of Riding on Track Bankings"
mathjax = true
+++

Three questions frequently crop up around the physics of riding around track bankings:

1. What kind of G-forces do riders experience when riding though bankings at speed?
2. A low speeds a rider "leans out" in the banking as gravity pushes them down the track. A high speeds a rider leans in as the centrifugal force tends to push them up the track. There is a speed when a rider transitions between these two states, a speed when the bike is exactly orthogonal to (i.e. perpendicular to, or at 90 degrees to) the surface of the track. What is this speed?
3. What is the minimum speed you need to ride to avoid "falling off" in a banking?

The material that follows is based on two excellent posts on the subject:

* [G Force](http://alex-cycle.blogspot.ca/2015/01/g-force.html) from [Alex's Cycle Blog](http://alex-cycle.blogspot.ca/). This is a great blog with lots of emperical data on training, aerodynamics, and other cycling topics. Highly recommended!
* [The Physics Of Cycling: Why Does A Velodrome's Sides Need To Be Banked?](http://theaftermatter.blogspot.ca/2012/05/physics-of-cycling-why-does-velodromes.html)

### Traveling Around a Curve ###

#### To Turn is to Accelerate ####

Acceleration is any change in speed and/or direction. When traveling around a curve, even through a cyclist's forward speed remains constant, the cyclist is changing direction, accelerating towards the center of the curve. This acceleration is generated from a [centripetal force](https://en.wikipedia.org/wiki/Centripetal_force) generated by the bike's tires on the track surface. Take a look at the following simplified view of a track from above.

{{< figure src="/figures/track-model.png" title="Track Model From Above">}}

#### How "Tight" is the Rider Turning? - Turning Radius ####

To start with, we will just consider a path around the black, datum line of the track. We model the track as consisting of approximately two semi-circles, joined by two straights. [G Force - Alex's Cycle Blog](http://alex-cycle.blogspot.ca/2015/01/g-force.html) does a great job of demonstrating how to estimate the radius of the turn on a velodrome. However, the answer Alex came up with was based on the straights of a 250 meter velodrome being 44 meters long. A 44 meter straight seems way too short -  it implies the circumference of each turn is $$ (250 - 44xx2)/2 = 81 $$ meters long, making the turns twice as long as the straights.

So we pulled up Google Earth, and got an image of the [Bromont Velodrome](http://centrenationalbromont.com/caracteristiques-du-velodrome/) This was the velodrome used for the 1996 Atlanta Olympics, which was moved to Bromont, Quebec in 2000. Its a 250 meter track with 42 degree bankings. Here's what we found:

{{< figure src="/figures/bromont-velodrome-measurement.png" title="Bromont Velodrome Sizing">}}

The straights look to be about 59 meters long. This makes each banking $$ (250 - 59xx2)/2 = 66 $$ meters long, which seems more reasonable. The radius of a turn is:

{{< asciiMath math="r_t = l_t - (2 xx l_s)/(2pi)" >}}

Where:

* $$ r_t $$ - is the track's radius of the turn
* $$ l_t $$ - is the total length of the track
* $$ l_s $$ - is the length of one straight

So the track turn radius for a 250 meter, UCI Class 1 velodrome will be around: $$ 250 - (2 xx 59)/(2pi) = 21 $$ meters.

But what we _really_ need is the rider's turn radius, not the track's turn radius. The rider's turn radius is based on the position of their Centre Of Mass (COM). Since a rider leans over when riding around the banked turn of a velodrome, then their COM turn radius is less than the turn radius at the track where the tire is rolling along. Stealing a diagram from [G Force - Alex's Cycle Blog](http://alex-cycle.blogspot.ca/2015/01/g-force.html) :

{{< figure src="/figures/track-turn-radius-diagram.png" title="Center of Mass (COM) Turn Radius">}}

The rider turn radius is calculated as:
{{< asciiMath math="r_c = r_t - (sin(theta_l) xx h_c)" >}}
Where:

* $$ r_c $$ - is the rider turn radius (the radius at the COM)
* $$ theta_l $$ - is the lean angle of the rider, taken from the vertical
* $$ h_c $$ - is the distance from the bottom of the wheel to the Center of Mass (COM) of the bike and rider.

Let's assume a rider's COM is 1 metre up from the bottom of the wheels. (COM height will be about the same as floor to saddle height for a rider in an aggressive race position). If they  are riding at speed,  perpendicular to the track surface of 42 degrees, then their lean angle is also 42 degrees. So the rider's turn radius $$ r_c = 21 - (sin(42) xx 1) = 20.33 $$ meters (.67 meters difference)
That's a difference of about 3%. 

__OK so for the Milton velodrome, a 250 meter, UCI Class 1 track, our rider turn radius is 20.33  meters__

#### Riding at the Top of the Track ####

The top of the track has a wider turning radius than the bottom. How much wider?
We can use the following diagram to calculate the turning radius at the top of the track:
{{< figure src="/figures/track-height+radius.png" title="Top of Track Height and Turning Radius">}}
For UCI Class 1 velodromes, the width is between 7 and 7.5 meters. At Milton its 7.2 meters. So:

* Additional turning radius $$ = 7.2xxcos(42) = 5.35 $$ meters
* Track vertical height $$ = 7.2xxsin(42) = 4.98 $$ meters (about 16 ft)

To get the turning radius at the top of the track, we just add the additional turning radius to rider turn radius we found in the previous section.

__For the Milton velodrome, the top of track turning radius is $$ 20+5.35 = 25.35 $$ meters__

#### What About Forest City Velodrome? ####

Forest City Velodrome is 138 meters long. But we don't happen to have any other track dimensions. As an approximation, we can take our 250 meter track calculations and scale them proportionally. Our scaling factor is 138/250 = .552 So the length of one straight would be $$ 59xx.552 = 32.5 $$ meters.

Using the formula above, we get a track turn radius of $$ 138 - (2 xx 32.5)/(2pi) = 11.6 $$ meters. Then we subtract the rider COM part of .67 meters. As a rough check, the Forest City Velodrome fits inside a hockey arena, and a hockey rink is 85ft wide. This would work out to a radius of 13 meters, if the base of the track went around edges of the rink. Since its actually inside the edges of the rink, a track turn radius of 11.6 meters "feels" about right.

__For the Forest City Velodrome, the rider turn radius is 10.95 meters__

#### Velodrome Summary ####

Let's put it all together:

Velodrome | Length | Straight Length | Bank Angle | Turn Width | Track Turn Radius Black | Rider Turn Radius Black | Rider Turn Radius Rail 
----------|--------|-----------------|------------|------------|-------------------------|-------------------------|-----------------------
Milton    |  250   |  59             |    42      | 7.2        |      21                 |     20.3                |     25.35
FCV       |  138   |  32.5           |    51      | 4.5        |     11.6                |     10.95               |



### What G-Force Does a Rider Experience? ###

The material in this section is taken from [G Force - Alex's Cycle Blog](http://alex-cycle.blogspot.ca/2015/01/g-force.html). Alex does a great job of explaining how to calculate the G-Force experienced in a turn. There's also a [G-Force Wikipedia page
](https://en.wikipedia.org/wiki/G-force) with lots of background material on the subject.

Whenever a rider makes a turn, they are constantly accelerating towards the center of the track, assuming the bike's forward speed remains constant. As a result, they experience some lateral g forces when turning, as well as the regular downward 1g due to gravity.  So the total g force they experience will be more than 1g. How much higher depends on their speed and the turn radius. This lateral force is called [centrifugal force](https://en.wikipedia.org/wiki/Centrifugal_force).

Notice we did not mention the bank angle of the track. That's because the bank angle really has nothing to do with the f-Force! A criterium rider taking a tight corner at a given turn radius and speed on a flat road will feel the same G-Force as a track rider on a velodrome banking at the same turn radius and speed. What the bank angle does is allow the track rider to navigate a given turn radius at a much higher speed than on a flat road. The banking removes the issues of hitting the inside pedal on the road surface, or of losing friction contact with the road, skidding to the outside of the turn and crashing.

The lateral force required to turn a curve is calculated based on a variation of Newton's laws of motion:
{{< asciiMath math="f = mxxa" >}}
{{< asciiMath math="f_l = m_cxxv_c^2/r_c" >}}
{{< asciiMath math="g_l = v_c^2/(9.81r_c" >}}

That's the lateral G-Force. But of course the rider also has 1G of gravity pushing them downwards. To get the total G-Force on the rider we need to combine the lateral and downward G-Forces. This is shown in the following diagram:

{{< figure src="/figures/rider-g-forces.png" title="g Forces on Rider in Turn">}}

We've deliberately not shown the track banking to highlight that the bank angle is irrelevant. So the total g-force on the rider is given as:

{{< asciiMath math="g_t = sqrt(g_l^2 + g_g^2" >}}
{{< asciiMath math="g_t = sqrt(g_l^2 + 1" comment="Since the g-force due to gravity is 1g">}}

Using the rider turn radii given in the table above, and the equations above, we can calculate and graph the total g-force on a rider at various speeds. 

{{< figure src="/figures/rider-g-forces-graph.png" title="Total g=Force on Rider by Speed and Track">}}

The graph compares riding:

* on the black line at Milton - middle blue line
* at the rail at Milton - the lower orange line
* on the black line at Forest City Velodrome - the grey line

Of course, we've made a lot of estimations... so treat the numbers a approximate. 

### Orthogonal Riding Speed ###

Next we tackle calculating at what speed a rider is exactly orthogonal to (perpendicular to) the track in the banking. A rider will notice a change in bike handling when they go above this speed - at low speeds a rider "leans out" in the banking as gravity pushes them down the track. A high speeds a rider leans in as the centrifugal force tends to push them up the track. 

### Minimum Speed to Avoid "Falling Off" in the Banking ###

Finally we take a crack at calculating the minimum speed a rider needs to ride through the banking to avoid falling off and sliding down the track.



#### Junk ####

{{< asciiMath math="x = (-b +- sqrt(b^2-4ac))/(2a)" >}}
Theta:   &theta; θ  $$ theta $$


