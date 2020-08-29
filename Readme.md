# Vulnerable Settlements

One of the challenges in the fight against poverty is the precise localization and assessment of the  sprawl of vulnerable communities. This is traditionally accomplished using nation-wide census exercises, a burdensome process that  requires field visits by trained personnel. Unfortunately, censuses are conducted only sporadically (e.g., every ten years in Mexico), which makes it difficult or impossible to track the short-term effect of policies to fight poverty. In practice, poverty assessment is  carried out through extrapolations, sampling,  indirect indicators, and lately using satellite images. In this research, we propose to build a system that maps  images from  satellite surveys with data captured in the field by means of machine learning schemes. Given images of the area of interest, the system extracts features related to well-being of the communities considered. This strategy permits a quick assessment of the degree of vulnerability of new or changing community sprawls, providing quantitative information that can be used to evaluate the effect of governmental policies and socio-economical factors.

[Vulnerable Settlements in Mexico. You can see a live demo of this map at (requires Earth Engine permission) https://code.earthengine.google.com/9350aac99d8a6aa99c1fdce7e740d82a?hideCode=true](https://github.com/joaquinsalas/vulnerableSettlements/blob/master/figures/mexicoMap.jpg)

## Background

Historic statistics seem to indicate that poverty rate is steadily receding worldwide. Take, for instance, global extreme poverty. In 1981, 42.12% of the population had an income of less than $1.90 USD at constant 2011 purchasing power parity prices (PPP). In 2015, this value was reduced to 9.94%. Nowadays, an estimated 250,000 individuals abandon extreme poverty in the world each day. This trend extends to individual countries. In Mexico, in the same period considered above, the population living in extreme poverty decreased from 8.14% to 2.48%. If poverty rate is receding globally, though, income inequality is on the rise.  Reportedly, three individuals in the US (Gates, Bezos, and Buffett), and six individual in Mexico, own as much wealth as the bottom 50% of the population in their countries~\cite{hardoon2016economy}.  Indeed, poverty rate is  unevenly distributed worldwide, with Mexico affected at a much larger scale than the U.S. For example, in 2016, 95.5% of the U.S. population received as income  $10 USD or more daily, versus 31.3% of the Mexican population. This translates to  16.36 million individuals in the U.S.  and 88.85 million in Mexico living below the international poverty line of $10 USD daily~\cite{roser2013global}.


Poverty means families going hungry, children with little or no access to education, reduced services (electical power, drinking water), and  poor health~\cite{plag2020goal}. Communities of people living in poverty are vulnerable to physical factors and social exploitation.
Building on the principle of "leaving no one behind", the UN adopted the 2030 Agenda for Sustainable Development, which included eliminating extreme poverty as its primary goal. 

A critical step in combating poverty is to identify, assess, and track the sprawl of affected communities. This is necessary both to plan economical and social interventions, and to evaluate the efficacy of such interventions. For example, periodic national census exercises are designed to  grab an instant photo of the status of a country. Unfortunately, censuses  require considerable effort and take place only sporadically (e.g., every ten years in Mexico). Clearly, a better and more economical approach is required to allow access to timely information on the location and poverty status of affected communities. Several technological trends can reduce the cost of this process, and produce reliable up-to-date data. These technologies rely on sensory  information from space, and ground surveys~\cite{khan2019multi}. Data from these sources is becoming increasingly abundant,  precise, and cheap to obtain. 
Furthermore, recent advances in machine learning techniques make it possible to extract relevant indicators from sensory data, which can  inform and guide policymakers. 

In this project, we propose to develop a system whose purpose is to locate vulnerable community sprawls and assess poverty status between census years, using high-resolution, multispectral satellite imagery. In the process, we will develop the capabilities to track differences in gap years (between censuses), and estimate the wealth status of people living in new and modified settlements.  Crucially, we will supplement our estimates with ground truth data obtained with local surveys. This result will enable us to assess the performance of our algorithms and provide relevance feedback to the inference mechanisms. The contribution that we foresee as outcome of this project is a methodology for tracking vulnerable communities during census gap years employing a blend of daytime and nighttime-light satellite imagery using deep learning. 

## A Vulnerability Index

We start with nation-wise block-level aggregated information about the following features

+ Proportion of households without sewage
+ Proportion of households without concrete floor
+ Proportion of households without tubed drinking water
+ Average number of occupants per bedroom
+ Proportion of households without toilet. 


Roy et al. (2019) propose to use the first principal component and the data projection on it as the vulnerability value. We have found it to be too sensitivy to extreme values. Therefore, we propose to define well-being by the projection of vector p = [p_1, ..., p_5]/sqrt(5) with vector [1,1,1,1,1]/sqrt(5), as we illustrate in the following figure:

[Vulnerability Assessment. We project the vector containing the measurements with a vector describing having all the 
features to having none.](https://github.com/joaquinsalas/vulnerableSettlements/blob/master/figures/vulnerabilityProjection.jpg)




















