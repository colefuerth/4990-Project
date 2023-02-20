# Physics-Based Visual Computing for Efficient 3D Vision and Sensing

David B. Lindell \
University of Toronto

## 3D sensing

- 3d sensing is on all kinds of vehicles now, phones, satellites, whatever
- what he is interested in is a paradigm called physics based visual computing
- you can capture these from photon interactions
- photon interactions
  - time of flight
  - polarization
  - spectrum
  - spatial statistics
- optics, sensors, algorithms
- "superhuman" visual computing
  - 3d geometry
  - lighting
  - reflectance
  - material properties
  - motion
  - behaviour

## Homage to the father of photometry

- pierre bouger wrote a book to model the behaviour of light
- he looked at how light was attenuated as it passed through a volume onto a screen
- there is a logarithmic model of how the photons would scatter through the semi transparent models
- there is now a `radiative transfer` equation on how light would scatter

## Non-line-of-sight imaging

basially sense something off of a wall, behind an object

- lidar, or time flight imaging sensing
- you send a pulse of light from a laser and the sensor will measure the time it takes for the photons to leave the sensors and come back
- you see a peak of photon returns that indicates the time delay
- you get a "3d point cloud" coming back
- almost every self driving car uses some kind of lidar on top

- these lidars are designed to capture direct lines of sight, but what about non line of sight
- fog and inclement weather really fuck with the lidar as they are now
- his test bench was a lidar array and a single pixel light detector
  - his laser would move around on in a pattern on the wall
  - using the geometry of the wall, he could sense the shape of the object behind the wall
  - it was a trillion frames per second video
  - you would see the ripples of photons hitting the wall as they bounce off the object
- A single-photon avalanche diode would pick up the photon coming back from a picosecond laser
- the picosecond laser would be fired at megahertz rates and hit the wall
- you end up with a histogram of photons returning for each pulse, in nanoseconds
- you can raster that data off of the imaging area to build a "3d" model of the gabbagoo behind the wall

### Connection to radiative transfer

- you can apply some assumptions to come up with an equation for this
- you can transform this equation into a system of linear equations, $\roh = Ap$
  - $\roh$ is the measurements
  - A is the transort matrix
  - p is the unknown volume
- this initial model ends up with trillions of elements, which is not computationally friendly
- So, we can perform a transormation on the information model to come up with 
- **picture of this on phone**

### Frequency-wavenumber migration

- If you drop the calculations for two-way propagation (there and back) and just do one way, you can get a much more efficient model
- basically, you set the time of flight to 0 and set C to half the speed of light, and let the light coming back off the rabbit work its way to the reflector
- You can iteratively reverse that wave pattern until it converges at t=0, and get a surface that is the shape of the object
- Iterative is inefficent, but someone at some point did invert the equation and get a closed form solution

### $f-k$ migration

- you can do the same thing with frequency and wavenumber
- Express wavefield as function of measurement spectrum (plane wave decomposition)
- wavefield = fourier transform of measurements
- set t=0 to get migrated solution:
- measurements = (almost) inverse fourier transform of wavefield

## imaging through scattered media

This one looks at things like fog and smoke

- the entry point where the light enters the medium is the "ballistic regime"

### Connection to radiative transfer

- in scattering media, you can work out the radiative transfer equation into a diffusion equation (with some assumptions)
- You can do something called "ballistic imaging", where you filter out all the noise down to a specific part where you *expect* the light to be

### Modelling

- say you are imaging something behind a thing paint canvas
- r0 is the point on the near side, r1 is the exit point on the far side
- you can use the difusion equation from earlier to model the photon distribution coming out at r1
- then, you can set points r2 and r3 as how the photons pass back through the medium

### Neural Networks

- you can use machine learning models on individual images to model them
- the neural networks dont work well directly applied, but if you apply them on top of a Volume Rendering model, they work really well

## 3D modelling

- you can feed a bunch of images at different angles through a neural network to get a 3d model
- they used different activations for different results
- you do some kind of 3d aliasing to prevent the models from getting fucky wucky
  - kind of looks like stretched borderlands 2 graphics
- 