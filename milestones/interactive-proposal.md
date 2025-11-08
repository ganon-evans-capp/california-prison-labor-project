# Ganon Evans 

## Description

About one in one hundred of all of the people in Louisiana are in prison, with over half of them in local facilities. For state facilities, imprisonment is a population shift from urban parts of the state to more rural areas where prisons are located. As a result, states across the country have performed "prison gerrymandering" in which congressional districts for both state and federal office meet their population requirements by counting prisoners who reside there, but are originate from other parts of the state.

I wanted to make an interactive model showing the consequences of the prison population shift in Louisiana and hows it affected population-dependent things like congressional districts and their results, grants and federal funding, and demographics. I have a lot of robust data on prison statistics now by region, but I think the challenge will to try and estimate the unseen counterfactuals of what districts would look like if people were instead in their home locations. 

## Technical Plan re: Option A/B/C/D

I plan on going something like Plan B. I don't want to do a geospatial map, but instead try and do something to represent the flow or change of people and factors related to population migration. I was really inspired by the "A Day in the Life of Americans" example or others that use the moving blobs. I wanted to do something like where areas are represented by bubbles and grow or shrink with population. After some research, it seems like a package that allows for packed circles ([{like this one}](https://github.com/mhtchan/packcircles)) may allow me to that.

I think it would be cool to compare regions in terms of their total incarcerated populations relative to some other statistics, like development. I've seen demographic data with population pyramid-style graphs in the past, so I'm curious if perhaps I could set something up that easily shows several parishes or cities or whatnot. [{At the bottom of this page is an example of what I'm thinking of}](https://stephanieevergreen.com/visualizing-demographic-data/). Plotly and matplotlib have built-in functions to do this, but I'll probably stylize things more with CSS.

## Mockup

![Bubble 1](../images/map_mock.png)

## Data Sources

### Data Source 1: Prison Policy Initiative, Louisiana Data

URL: [{URL}](https://www.prisonpolicy.org/data/)

Size: The Prison Policy Initative has 20 datasets varying in size. For instance, there's one with Louisiana's six congressional districts and two others for each zip code and census tract respectively. Each dataset has 5-6 columns, including the number of people from each location in prison and the total imprisonment rate per 100,000.

The datasets are somewhat inconsistent, but one thing I noticed is that, for instance, the New Orleans dataset indicates how many people are in state prisons, so it may be cool to model the flow of people back to certain neighborhoods or areas as a whole.

### Data Source 2: US Census Bureau ACS Data

URL: [{URL}](https://data.census.gov/table/ACSSDP1YCD1192023.DP05?q=congressional+district&d=ACS+1-Year+Estimates+Supplemental+Data+Profiles+for+Congressional+Redistricting)

Size: 6 Rows (one for each congressional district), Unknown number of columns (dependent on how many economic attributes I select for)

Very rough placeholder dataset for now (see questions), but I want to bring in some external economic or social measurements relative to my analysis by area (either Louisiana House or Senate District or congressional district).

## Questions

1. I have a gut feeling I'll need to merge in a lot of funding data. I'd like to look at population-based grants or funding. Do you have any idea where I could best find that? I thought of the census tracts for instance as one palce I could use to link data.

2. Can you think of any other examples of things I could link my project to? I think a longterm idea would be showing how redistributed populations could affect congressional maps...I think maybe implementing Professor Duchin's package could make some cool data.