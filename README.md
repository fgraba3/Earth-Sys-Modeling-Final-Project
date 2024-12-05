# Earth-Sys-Modeling-Final-Project
Simulation of lake evaporation using an eddy diffusion model - Kylee Graham & Frank Graba
***
**Main Theme:**
The main theme of this paper is to accurately model evaporation and water level in lakes based on an eddy diffusion model. This can help us understand how climatic variations such as precipitation, cloud coverage, and temperature can impact water levels in lakes. This is important because lakes can serve as sources of drinking water, and a better understanding of this type of modeling can help predict when droughts would occur. Which would better prepare areas for limiting water usage for non-drinking activities. This type of modeling could also be used to predict when water levels are increasing due to low evaporation and to warn of flooding. Overall, this modeling is useful both for safety in terms of understanding periods of flooding or low levels of drinking water, as well as gaining a scientific understanding of how climatic variables affect lake evaporation.
***
**What Observations and Models are used by others that are different than what we are doing in the project:**
To simulate and interpret lake evaporation of Harney-Malheur Lake, Oregon, Hostetler & Bartlein (1990) use an eddy diffusion model. This model is used to understand the flow of fluid, in this case freshwater, due to eddy motion. The eddy diffusion model considers the thermal structure of lake water wherein seasonal temperature variability, heat storage, convection, turbulent mixing, and the surface energy balance must be accounted for (Hostetler & Bartlein 1990). Similarly, we will model evaporation of Harney-Malheur Lake using the eddy diffusion model as this model is numerically stable. While we will use the same model, we will not simulate the data from 1980 to 1986. We will use the model over a similar six year from 2018 to 2023. We have chosen to do a more recent modeling to compare evaporation rates approximately 40 years apart. We believe it is important to show this data to see if evaporation rates have increased over time as lower lake surface level could be caused by warming temperatures due to climate change. Our model is different from .....(insert diffusion paper here).
***
See Equations via this pdf 
[Governing Equations.pdf](https://github.com/user-attachments/files/18028040/Governing.Equations.pdf)
***
What simulations did you run with the model? 

Developing a base case analysis, we ran the model first using Dirichlet boundary conditions using an oscillating sine function to mimic the temperature profile of the lake. We also used a constant diffusivity value for simplicity. Once we got the model to work, we updated the diffusion value to act as a PDE changing with depth over time (D(z,t)). This method allows us to account for both molecular diffusion of water, eddy diffusion, and the area of the lake at depth z. While the paper implements Neuman boundary conditions, we use Dirichlet for simplicity in both models.  
