# Earth-Sys-Modeling-Final-Project
Simulation of lake evaporation using an eddy diffusion model - Kylee Graham & Frank Graba
***
**Main Theme:**
The main theme of this paper is to accurately model evaporation and water level in lakes based on an eddy diffusion model. This can help us understand how climatic variations such as precipitation, cloud coverage, and temperature can impact water levels in lakes. This is important because lakes can serve as sources of drinking water, and a better understanding of this type of modeling can help predict when droughts would occur. Which would better prepare areas for limiting water usage for non-drinking activities. This type of modeling could also be used to predict when water levels are increasing due to low evaporation and to warn of flooding. Overall, this modeling is useful both for safety in terms of understanding periods of flooding or low levels of drinking water, as well as gaining a scientific understanding of how climatic variables affect lake evaporation.
***
**What Observations and Models are used by others that are different than what we are doing in the project:**
To simulate and interpret lake evaporation of Harney-Malheur Lake, Oregon, Hostetler & Bartlein (1990) an eddy diffusion model was implemented. This model is used to understand the flow of fluid, in this case freshwater, due to eddy motion. The eddy diffusion model considers the thermal structure of lake water wherein seasonal temperature variability, heat storage, convection, turbulent mixing, and the surface energy balance must be accounted for (Hostetler & Bartlein 1990). Similarly, we will model evaporation of Harney-Malheur Lake using the eddy diffusion model as this model is numerically stable. Our model is different from Henderson-Sellers and Davies (1989) and McCormick and Meadows (1988) models for example are their models more centralize on mixed-layer modeling to simulate thermal stratification of lakes and shallow inland seas. While Hostetler & Bartlein (1990) focuses more on simulating lake temperatures and evaporation of different lakes, the other models consider atmosphere-ocean circulation climate models more generally (Henderson-Sellers and Davies (1989)).
***
**Equations:** see equations via this pdf 
[Governing Equations & Assumptions.pdf](https://github.com/user-attachments/files/18029470/Governing.Equations.Assumptions.pdf)
***
**Numerical Methods:** see code via the .ipynb file (go to file from tab)
***
**Results**

**What simulations did you run with the model?**

Developing a base case analysis, we ran the model first using Dirichlet boundary conditions using an oscillating sine function to mimic the temperature profile of the lake. We also used a constant diffusivity value for simplicity. Once we got the model to work, we updated the diffusion value to act as a PDE changing with depth over time (D(z,t)). This method allows us to account for both molecular diffusion of water, eddy diffusion, and the area of the lake at depth z.  

**Describe the results.**

Figure 1 “Pyramid Lake: Temperature Profiles During the Sixth Year” shows a simulated temperature-depth profile in Pyramid Lake in Nevada. The resulting profile shows surface temperatures varying with seasonality at the surface. With increasing depth, the temperature decreases no matter the season showing that less and less heat is able to diffuse towards the depths of the lake.  

Figure 2 “Pyramid Lake: Seasonal Variation of Temperature over Time” displays the temperature gradient of the lake from surface level to its maximum depth. Seasonal variation in temperature is visible at the surface as warmer summers and cooler winters appear at the surface of the lake. At depth there is less variation in the temperature as the gradient is more constant. This shows the lake’s ability to store heat at depth during warmer months via the diffusion of heat attained during warmer periods.  

Figure 3, “Pyramid Lake Diffusivity Profile vs. Depth”, exhibits the change in diffusivity with respect to depth at a single point in time. The Diffusivity profile is based upon the molecular diffusion of water (Km), the area of the lake when assuming a rectangular shape, and the change in eddy diffusivity. For the diffusivity profile, we considered a surface temperature of 20 °C and a bottom surface temperature of 4 °C exemplifies a lake temperature profile. Our model shows that thermal energy diffusion increases with depth within the lake and then decreases after achieving the midpoint depth of 50 meters.  

Figure 4, a color mesh grid plot for the “Change in Diffusivity over Time ((D(z,t) vs. z), exhibits the change in diffusivity over time with respect to depth for Pyramid Lake. The figure shows diffusion at its highest around 50 meters deep and during the first one hundred days of the year (from January to Mid-April). This exemplifies the lack of thermal stratification that occurs within lakes during the winter as there is less stratification as the lake cools. Diffusion begins to decrease over time as D(z,t) goes towards the warmer months showing that thermal stratification could be taking place where the surface of the lake is warmed from solar radiation and the cooler, more dense waters sink to the bottom of the lake.  

**How do the results compare with any known solutions, or data?** 

The results of our model that determines temperature-depth profiles are consistent with that found in literature. The highest temperature is found at the air-surface interface and the temperature steadily decreases with increased depth until a minimum at the bottom of the lake. The resulting profile is a result of the diffusion of heat throughout the lake with the maximum heat flux occurring at the surface and decreasing quantities of heat being diffused down to the floor.  

**How do the results change with different methods, time steps, grid spacing, or model parameters?**

Surface lake temperatures varied widely with input parameters and change of the sinusoidal temperature variation. The Crank-Nicolson method allows us to use larger time steps so that we are able to look at day by day changes or chunks of even larger time. Smaller time steps are better for looking at minute variation whereas larger ones reveal results for longer periods of time. Different sizes of grid spacing increase or decrease the detail shown by the figures.  

**What did the model tell you about the process you were studying?**

The model showed us the complexities and difficulties of trying to accurately model characteristics of a lake such as temperature-depth relationships as well as evaporation. The figures created have shown us that diffusion of heat through a lake is a slow process that does not bring much heat to the depths of lakes as the amplitude of diffusion decreases with depth as shown in the temperature gradient profile. This model also shows us that water has strong heat retention and insulating properties that allow it to store heat during warmer periods and release it during cooler periods.  

**How could the model be improved in terms of methods used or processes included?**

Improvements to the model could be made by accounting for more of the natural processes that we assumed to no longer be in effect. This would include accounting for the shortwave and longwave radiation that warm the lake surface, understanding that the lake surface area changes with depth and is not constant, accounting for other parameters like albedo that may impact the heat received at the surface of the lake. To further improve the methods of the model the given Neumann boundaries would need to be implemented for a more accurate depiction of surface and bottom temperatures of the lake such as a no-flux lower boundary. Another improvement that could be made is to account for the eddy diffusivity value (K(z,t)) more accurately. While we chose a simple sinodial function to model variances, this was not used within Hostetler & Bartlein (1990)’s paper. We believe this is one reason our diffusivity function may not have best represented thermal heat diffusivity within a lake. With more careful consideration of the appropraie as outlined in our equations section, we could have developed more accurate temperature gradient and diffusivity profiles. Another way to improve our model is to incorporate real time data of water surface temperature of Lake Pyramid. By including real data, this makes the model more applicable to understand not only seasonal variation of temperature but determining if there are climate related interpretations as well.  

**References:**

Henderson-Sellers, B., & Davies, A. M. (1989). Thermal stratification modeling for oceans and Lakes. Annual Review of Heat Transfer, 2(2), 86–156. https://doi.org/10.1615/annualrevheattransfer.v2.50 

Hostetler, S. W., & Bartlein, P. J. (1990). Simulation of lake evaporation with application to modeling lake level variations of Harney-Malheur Lake, Oregon. Water Resources Research, 26(10), 2603–2612. https://doi.org/10.1029/wr026i010p02603

McCormick, M. J., & Meadows, G. A. (1988). An intercomparison of four mixed layer models in a shallow Inland Sea. Journal of Geophysical Research: Oceans, 93(C6), 6774–6788. https://doi.org/10.1029/jc093ic06p06774 

Šarović, K., Burić, M., & Klaić, Z. B. (2022). SIMO v1.0: simplified model of the vertical temperature profile in a small, warm, monomictic lake. Geoscientific Model Development, 15(22), 8349–8375. https://doi.org/10.5194/gmd-15-8349-2022

World Lake Database - ILEC. (n.d.). Wldb.ilec.or.jp. https://wldb.ilec.or.jp/


