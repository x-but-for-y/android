## x-but-for-y - turn signals but for humans

Real-time, turn signals for human safety and accident prevention

[**Read the DevPost for more info!**](https://devpost.com/software/x-but-for-y)

Made in under 24 hours for Uncommon Hacks at the University of Chicago.

## Installation

1. Clone the repo `git clone https://github.com/x-but-for-y/android.git`

2. Clone the server repo

[Video demo of turn signals](link_here)

## Inspiration

We have noticed a recent increase in person-to-person walking collisions.
To combat this problem, we wanted to create a way for individuals to communicate
their intentions to other walkers to increase knowledge-sharing.

Our solution: turn-signals but for humans!

Thinking about turning left? turn-signals but for humans automatically registers
 the direction you are looking to alert other walkers of your left turn without your hands!
 So keep on walking with both hands filled, we've got signaling covered!

 We found a project which used Computer Vision to help us get started
 [Screenshot](http://romanhosek.cz/wp-content/uploads/2013/01/device-2013-01-20-185851.png)

## Challenges

We faced MANY challenged building out the Android interface. When we initially approached the app, we attempted to use
the Android Camera API. After some time of messing around with it we learned this API is deprecated in favor of Android's Camera2 [API](https://developer.android.com/reference/android/hardware/camera2/package-summary.html). Unlike the deprecated Camera API, Camera2 API has very little documentation on how to get started. This forced us to look for existing open-source projects we could model off of. Google has a few examples of the Camera2 API. We tried the basic example and realized it would not fit our project requirements. Simply using the Camera2 API would only give us the ability to analyze images once they were capture. We require active analyzation of the camera preview to identify head turns and gestures. We finally found a decent starter template which used the OpenCVLibrary300 (Computer Vision) to outline eye locations and built the project from this template. The final challenge we had was a good one: our readings were too sensitive/noisy. I reduced the noise with a filter which filtered any change below a minimum threshold to a range sufficient for app functioning. 
