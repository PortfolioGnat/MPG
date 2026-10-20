# MPG
___
# Miles Per Gallon Dataset
Below you will find different examples of visualizations that pull from a dataset called MPG.\
The different categories within MPG are as follows:\
Fuel economy data from 1999 to 2008 for 38 popular models of cars

# Description:
This dataset contains a subset of the fuel economy data that the EPA makes available on [Fuel Econonmy Gov](https://fueleconomy.gov/). It contains only models that had a new release every year between 1999 and 2008; this was used as a proxy for the popularity of the car.

# Usage: MPG
1. manufacturer = manufacturer name
2. model = model name
3. displ = engine displacement, in litres
4. year = year of manufacture
5. cyl = number of cylinders
6. trans = type of transmission
7. drv = the type of drive train; where f = front-wheel drive, r = rear wheel drive, 4 = 4wd
8. cty = city miles per gallon
9. hwy = highway miles per gallon
10. fl = fuel type
11. class = "type" of car

# **Visualization 1: MPG Example**
![Visualization 1](/mpg_example.png)

## The image shows how many miles per gallon a vehicle gets on the highway in relation to its engine displacement. Here it has also been divided into different facets, categorized by class.

This visualization shows how to display information in a digestible, self-explanatory image. The aforementioned image was also used as practice for loading, posting, and captioning images to README via GitHub repositories.

## Notes/Commentary:
1. The image does a great job of showing the correlation between the hwy (highway miles per gallon) and the displ (engine displacement in liters).
2. The issue with this image is that it has not been properly defined for potential viewers who may not know the abbreviations for the values on both the x and y axes. It could have used the full definitions of the abbreviations where the axes are labeled, so it would be less confusing/irradicate the need for a guide or reference to the help(mpg) data.
4. The data has also not been properly labeled, and I had to execute code in GitHub in order for the visualization to receive a header.

### Great for a starter visualization, but there are many elements that could ultimately be improved upon.
___
## RStudio Code for MPG Example:

data(mpg, package='ggplot2')
> This loads the dataset as a package

help(mpg)
> Displays the definitions of the abbreviations used in the columns of the dataset so that I could copy and paste said information.

mplot(mpg)
> Runs through the dataset and asks how you would like the information to be displayed, as shown:

1: 1-variable (histogram, density plot, etc.)\
2: 2-variable (scatter, boxplot, etc.)
> Select one by entering a value for the visualization you would like to create.

Selection: 2
> I chose the second value to produce a scatterplot

Once I enter the desired values in the "Manipulate" pop-up using the gear icon, the expression of the visualization is as follows:
> gf_point(hwy ~ displ, data = mpg) |>\
>   gf_facet_wrap(~ class, ncol = 4) |>\
>   gf_labs(title = "", caption = "")

# **Visualization 2: MPG Legibility**
![Visualization 2](/mpg_legibility.png)

## The visualization above shows how many miles per gallon a vehicle gets on the highway in relation to its class.

This visualization was used to explore how color affects the legibility of information displayed. Key factors considered when creating this image included potential viewers with different types of color blindness. Here, the [3:1 color contrast ratio](https://webaim.org/resources/contrastchecker/) was utilized to help mitigate difficulties in perception of the data. This was done by utilizing colors that are far enough away from one another that those with impaired vision may see them without needing to change the color scale or scheme.

## Notes/Commentary:
1. The visualization utilizes a good color contrast ratio for those with impaired vision, while also giving a complementary and easy-to-look-at color scheme for those without vision impairment(s).
2. The image does a great job of showing the correlation between the hwy (highway miles per gallon) and the class (Type of car) and how those values directly correlate with one another. Using boxplots, you are able to see the groupings of vehicles that lie within normal distances per class, as well as the outliers.
3. Similar to the first visualization, the issue with this image is that it has not been properly defined for potential viewers who may not know the abbreviations for the values on both the x and y axes. It could have used the full definitions of the abbreviations where the axes are labeled, so it would be less confusing/irradicate the need for a guide or reference to the help(mpg) data.
4. Another improvement to note is that the outliers could have had sizing adjustments so that, beyond color impairments, visual impairments for viewers who may not be able to see the outliers may be accommodated as well. 
5. Once again, the data has also not been properly labeled, and I had to execute code in GitHub in order for the visualization to receive a header.

### There have been several notable improvements in this example compared to the image prior to this one.
___
## RStudio Code for MPG Legibility:

ggplot(data = mpg, aes(hwy, class))
+ geom_boxplot(outlier.color = "yellow", fill = "blue", color = "dark blue", outlier.shape = 1)

> This is the original code with the original colors. They are as follows;\
Outlier points = Yellow\
Box Plot Fill = Blue\
Box Plot Outline = Dark Blue

ggplot(data = mpg, aes(x = hwy, y = class)) + geom_boxplot(outlier.color = "darkblue", fill = "green4", color = "darkblue", outlier.shape = 1)
+ theme(plot.background = element_rect(fill = "white"), panel.background = element_rect(fill = "lightgrey", color = "black"))

> This is the new code changes the colors from the original to;\
Outlier points = Dark Blue\
Box Plot Fill = Green4\
Box Plot Outline = Dark Blue\
There are now also added elements in this code that I included to practice changing the colors so I can have more control over the visual;\
Plot Background = White (Color around the panel)\
Panel Background = Light Grey (Where the actual plot is)\
Panel Outline = Black (The outline of the panel)

Try testing out the [color contrast ratio](https://webaim.org/resources/contrastchecker/) by inputting the colors that were used in the code! What is the ratio between the chosen colors in the modified code?

<details>
<summary> Answer: </summary>
The selected colors have color contrast ratios that range between 3:1 and 10:1!
</details>

# Directory:

### [Go Back Home](https://portfoliognat.github.io/Home/)

# Dataset Projects:

[Gini Coefficient Dataset](https://portfoliognat.github.io/Gini/)\
[Map Datasets](https://portfoliognat.github.io/Maps/)
