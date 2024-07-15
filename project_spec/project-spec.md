# Project Specification: Digital-Physical Anlaysis of Fusion Cryomechanical Components

## Background and Motivation
Super-conducting magnets form the basis of the plasma containment system in a tokamak type fusion reactor. The magnet system for a conventional tokamak is split into several sub-systems including toroidal field coils, poloidal field coils and the central solenoid. Throughout operation the super-conducting magnets and supporting structures must sustain cryogenic temperatures, significant mega-newton scale electromagnetic body forces and neutron irradiation damage. To design and qualify super-conducting magnets and their supporting structures for structural loads simulations will be required. These simulations will require experimental validation data under cryogenic environmental conditions.

In support of the effort to design de-mountable magnet joints a new cryogenic experimental facility called ‘Elsa’ is being commissioned at the Fusion Technology Facility (FTF) Yorkshire as well as a cryo-mechanical material test rig which will be located at Culham. Elsa will provide the unique capability to test full-scale super-conducting magnet joints under realistic operating conditions while the cryo-mechanical rig at Culham will provide material data that is currently sparse for cryogenic temperatures. There is currently limited experience within UKAEA in performing mechanical experiments at cryogenic temperatures; this capability will be required to gain the validation data required for magnet structural simulation.

## Aims and Objectives
In this project we aim to develop the capability to use image-based diagnostics to measure maps of component deformation at cryogenic temperatures and in strong magnetic fields. The focus of this project will be enabling optical imaging and digital image correlation in a widebore cryogenic magnet test rig. This system is characterised by imaging into a long narrow cyclindrical tube with a window diameter of X mm and a length of Y mm.

- Develop and/or integrate a set of open-source software tools for simulating digital image correlation and performing uncertainty quantification on displacement and strain in 2D/stereo.
- Apply these open-source simulation tools to predict uncertainties for the constrained optical conditions of imaging down the narrow cylindrical tube to the test sample.
- Develop an experimental method
- Experimentally analyse the digital image correlation uncertainties in the constrained optical conditions of the
- Perform a detailed comparitive analysis of the predicted uncertianties with the digital image correlation simulator and the experimental uncertainties.

## Deliverables
The computational deliverables for this project are as follows:
- A module in `pyvale` that uses the blender python api to simulate digital image correlation cameras imaging a speckle target starting with 2D DIC.
- A module allowing deformation of a speckle texture applied to a geometry being viewed by the simulated cameras.
- A benchmark comparison of the simulated deformed images with the simplified 2D image deformation code already in `pyvale` for the following cases using a 1 Mpx camera:
    - Rigid body motion of: 0 to 1 pixels in 0.1 pixel increments
    - Hydrostatic strain of up to 1 millistrain in 0.1 millistrain increments
    - Pure shear strain up to 1 milli strain in 0.1 millistrain increments.
- A module that simulates the stereo DIC calibration procedure and that can produce simulated deformed images for stereo DIC.
- A full simulation of a set of stereo DIC cameras imaging down the cryogenic magnet probe. Including:
    - A simulation of the calibration procedure.
    - A simulation of imaging a copper disc target undergoing thermal contraction to liquid nitrogen and liquid helium temperatures.
    - Predicted uncertainties (systematic and random) for the x,y and z components of measured displacement and the xx, yy and xy strains.

The experimental deliverables for this project are as follows:
- Construct a mock-up rig using PVC pipe and 3D printed components that replicates the optical geometry of the magnet probe.
    - The length of the tube should be variable so that different imaging distances can be tested.
- Use the mock-up to develop a procedure for stereo calibration down the tube.
    - Note that this might require an independent calibration procedure or a purpose built rig to reach down the tube with the calibration target.
- Experimentally determine the uncertainties of the measured displacements with DIC using the mock-up.
    - Include noise floors for each component of displacement and an analysis of systematic error using the translation stage to analyse rigid body motions in each direction
- A hand calculation or simulation for thermal contraction to estimate the amount the probe supports will contract during operation at different temperatures and use this to determine the required depth-of-field for the setup.

Reporting requirements:
- A short concise report detailing your findings and recommendations focusing on a comparison between the simulated DIC uncertainties and the experimentally measured ones.


## Resources
- `pyvale`: this is the python toolbox developed by our team for simulating sensors.
    - https://github.com/Applied-Materials-Technology/pyvale
    - Clone this repo and create a `dic-sim` branch to develop your module!
- [Techanical drawings](https://ukaeauk-my.sharepoint.com/:b:/g/personal/lloyd_fletcher_ukaea_uk/ES4kxQRqqD9CmKl9F_Qq-_0B_P3GhBFXTGRV7E4-p1wYcg?e=CMhsjd) for the cryogenic magnet probe showing dimensions of the setup.
- [Paper](https://ukaeauk-my.sharepoint.com/:b:/g/personal/lloyd_fletcher_ukaea_uk/ESZ40OvaOotCn4nJXZ7ynawBv_Z5kmeBOXInPtI6CxyS4w?e=HzVXOo) from Sandia on using Blender to simulate digital image correlation
    - https://link.springer.com/article/10.1007/s40799-021-00491-z
- **Blender**: an open source tool for ray-tracing and rendering. Useful for simulating cameras and lighting.
    - https://www.blender.org/
    - https://docs.blender.org/api/current/info_quickstart.html
    - https://github.com/blender
    - https://federicoarenasl.github.io/Data-Generation-with-Blender/
- **DICe** (Digital Image Correlation Engine): an open source tool for processing digital image correlation data.
    - https://www.sandia.gov/ccr/software/digital-image-correlation-engine-dice/
    - https://www.youtube.com/@dice3207
    - https://github.com/dicengine/dice