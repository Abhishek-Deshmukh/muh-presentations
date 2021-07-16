# slide 1 (cover slide + TOC)

Hi, I am Abhishek Anil Deshmukh and this the presentation for my 6th semester project evaluation. My project's title is Background simulation at MINER.

*click* *click*

I will briefly discuss CENNS, the interaction that MINER is dedicated to looking for. Then will be going over what MINER is and how it plans on detecting CENNS.

After I establish why it is important to study backgrounds, I'll go over my study of cosmological background and radiogenic background. Then I'll cover a simulation I did which tests the effectiveness of different thickness of shieldings for a particular geometry. Then towards the end of my 20 mins I will go over my work with the MINER simulation team and then conclude by summarising what I achieved.

*click*

# slide 2 (CENNS)

When a neutrino interacts with a nucleus

*click*

It can cause a CENNS interaction. CENNS stands for Coherent Elastic Neutrino Nucleus Scattering. This neutrino-nucleus interaction has to follow 2 condition to be a CENNS interaction. First, coherence, meaning the neutrino has to interact with the nucleus as a whole, this requires the debrogle wavelength to be of the order of the nuclear radi, in terms of energy this translates to 10s of MeVs. Secondly, the interaction has to be elastic, meaning conserving energy and momentum before and after the interaction.

Such an interaction causes 2 main things. One, The neutrino Scatters as the interaction is elastic. Two, the nucleus with which the neutrino interacted faces a recoil. This recoil is necessary for us, as it will as the signal for detecting the CENNS at MINER.

*click* *click*

CENNS Interactions are really rare, Theoretical crosssection is 7.4 times 10 power -42 cm square
*click*

# slide 3 (MINER)

Now lets talk about MINER, MINER stands for

*click*

Mitchell Institute Neutrino Experiment at Reactor. They have their setup at Nuclear Science Center at Texas A&M University. Main goal of the experiment is to detect a CENNS interaction and as we have established that neutrino have a really low probability of interacting, they increase the number of neutrinos which are being shot at the detector.

To accomplish this they are using a 1MW TRIGA reactor, which uses Uranium 237 as its Fuel and then keeping it in meter range of the detector. To speak in number this means that if we keep a 100g silicon detector at 2 meters it receives a flux of 3.73 times 10 power 11 neutrino per cm square per second which translates to roughly 0.448 event per day.

*click*

Now we might have increased the number of events happening to about 1 every couple of days

*click*

Neutrinos aren't the only particles depositing energy on the detector we have muons, gamma, alpha, beta, neutrons etc interacting with the detector at a rates far higher than what we have for neutrino which causes our signal to be buryed under a pile of background.

Now that I have established backgrounds need to studied, we can get to what I did.

These backgrounds need to be understood, reduced and rejected. Lets first classify them to make dealing with them easier. Backgrounds can be classified into 2 categories based on where they came from, cosmological background and Radiogenic Background.

*click* *click*

# slide 4 (Cosmological Background)

Lets take a look at the cosmological background

*click*

Cosmological background consists of cosmic ray showers. Fortunately, we can simulate the output from cosmic ray showers using the Cosmic-ray shower Library, CRY for short. The output from CRY is based on simulations of atmosphere with cosmic-ray example high-energy proton primaries.

This is a plot of flux of different particles. This plot shows the angular distribution of muons, as they are main background from cosmological background

This is plot showing the coincidence in the results from the simulation from a framework called MCNPX in blue and experimental measurements in red.

*click*

CRY considers changes due to solar cycle, plot here shows fluctuations in proton flux at extreme ends of the cycle.

*click*

Also changes due to latitude

*click*

and altitude, although limited freedom is available.

*click*

It simulated the specified surface area of the sky like I can ask it to simulate a 10 meter by 10 meter patch of sky. But how does one decide on a surface area? *click* Simulating too much of it will be accurate by computationally expensive, while simulating too less won't be accurate enough. So, we need to find an optimised input surface are such that, it is accurate enough but not too computationally expensive.

*click*

# slide 5 (Computational Approach)

I started out a computational approach

*click*

Simulation set up includes a silicon detector kept at 35 inches from the input layer . Basic idea is to run this simulation for incremental values of surface area while the detector input is not saturated.  Once the detector input saturates we can take that surface area.

*click*

When I ran the simulation and plotted the result I realised high energy particles are rare, so it is statistically unreliable for prediction. One way around this was to shoot more particles to get more high energy events, but that becomes computationally expensive very quickly, so I went for a more analytical approach to the problem.

# slide 6 (Analytical Approach)

*click*

This is a euclidian space with the detector as a square centered at the origin along the x-y plane. The input surface is at height h from the x-y plane, parallel to the x-y plane. Let's choose a random point on the input surface O.  O is at (x, y, h). Now, lets find out the value of solid angle subtended by the detector point O. It would be something like this.

*click*

This is the expression for the  solid angle subtended by the detector A1 A2 A3 A4 on a point on the input surface. omega is the angle, h is the distance between the input layer and the detector, and D is the length and width of the detector.

Now we can integrate it over an surface area of the input layer to get the detector input value in some arbitrary. I wasn't able to integrate the analytically, so this is the

*click*

plot for the numerical integration values at incremental values of input surface.  The blue curve. It is saturating at about 450 so for an accuracy of 98 percent, we can just multiply 0.98 to 450 and see for what dimension of the input surface the curve and the line intersect.

*click*

I did this procedure with the current MINER setup and.

For the MINER setup with input layer at 35 inches from the detector will need about 37 meters by 37 meters input surface to simulate the cosmic-ray shower with 98% accuracy.

That is about all I have studied on the Cosmological background. Moving on to Radiogenic Background

*click*

# slide 7 (Radiogenic background)

We are primarily dealing with gamma, it is sometimes also referred to as ambient gamma.

People over at SNOLab recorded gamma background for Uranium, Thorium and K40.  This plot shows the 3 backgrounds normalised to 10 power 6 seconds. The red curve is the total background. Another thing to keep in mind when simulating radiogenic background is that it's isotropic. Meaning random in direction.

Now lets move on to testing some shielding geometry.

*click*

# slide 8 (Testing shielding)

Let me just set up some context before going to the aim. This is a veto detector it. As we know neutrino's rarely interact. The chances of a neutrino interacting 2 detectors is highly unlikely and we go on a limb and assume that if some particle deposits energy 2 detector during it's event, then it's not a neutrino. This detector is based on that, an event is only counted if during the event it deposited energy only on the green coin and no where else.
Formally it's called a single scatter cut.

...describe detector...

This geometry is rather complex and was only available in .stp format which is a CAD thing. I found a way to import the .stp file into Geant4, by converting it to obj first. Okay, so now we have the detector, we put in *click* a Geant4 simulation. And we also have shielding with the detector at the center, the shielding is a hollow cube with one face open. That is all for the context, The aim of the following exercise is as follows.

*click*

Experimental measurement show a particle rate of 303 DRU, what thicknes of shielding would decrease the particle rate to under 50 DRU. With that out of the way lets start.

*click*

Step one would be calibration, ran the simulation for 10 power 9 particles added a normal noise. Applied single scatter cut. and calculated number of particles I need to shoot to simulate a day's worth of particles. It comes out to be 2.4 times 10 power 6.

This plot is the energy to event rate histogram, after single scatter cut, adding in the noise. The way DRU is defined here is within the energy range of 100 to 300 keV. With a model simulation in place the only thing left is *click* to let it simulate with different wall thicknesses and them comparing results *click*

This first plot shows the events rate per energy range for different shielding thickness. The bottom half is a ratio plot with no shielding as the denominator.

This plot shows the wall thickness to DRU relation. As you can see 2cm thickness of lead shielding will decrease the particle rate from 303 DRU to 46 DRU.

That concludes this exercise.

*click*

# slide 9 (Contribution)

I integrate .stp format geometries of a few detector and housing into the simulation geometry and we plot on starting to run simulation from it this week.

...describe the image it time permits...

*click*

# slide 10 (Conclusions)

Now I'm basically shamelessly gonna brag about what it accomplished during my 6th semester project.

