# Data Analysis Report: Benthic Biota Photo-Survey

## Introduction

This report presents the analysis of benthic biota data collected from photo-surveys across two transects of the Eastern Mediterranean continental shelf. The data includes coverage values (in percentage) for different broad taxonomic groups. The survey was conducted across two sites, two seasons, and three seafloor depths, with four replicate transects surveyed at each location.

## Methodology

### Data Collection

The data used in this analysis is from the file "Photosurvey_processed_data.csv." It contains percentage coverage values for various taxonomic groups across different transects.

### Variables

- **Site:** Two sites were surveyed.
- **Season:** Data was collected in two different seasons.
- **Seafloor Depth:** Three seafloor depths were considered per year.

### Taxonomic Group of Interest

For this analysis, we focus on the taxonomic group **Bryozoa**. We will examine its coverage with respect to site, season, and seafloor depth. Additionally, we will explore the correlation between Bryozoa and other taxonomic groups.

## Data Analysis

### Loading Data and required library's

```r
library(ggplot2)
library(dplyr)
library(tidyr)
library(broom)
library(grid)
library(cowplot)
library(corrplot)
library(Hmisc)
library(ARTool)
library(EBImage)


# Load the metadata- NOTE: we work at the transect level.
photo_metadata=read.csv("Photosurvey_metadata.csv", header=TRUE, row.names=1, stringsAsFactors = TRUE)

# Load the processed and filtered coverage data by taxonomic group
photosurvey_coverage=read.csv("Photosurvey_processed_data.csv", header=TRUE, row.names=1, stringsAsFactors = TRUE)

# Make sure the order of transect_IDs is the same in the data and the metadata
ord=match(row.names(photosurvey_coverage), row.names(photo_metadata))
photo_metadata=photo_metadata[ord,]

# Merge metadata and coverage values
Photosurvey=cbind(photo_metadata, photosurvey_coverage)
str(Photosurvey)

```
## coverage in relation to site

```r
ggplot(Photosurvey, aes(x=site, y=Bryozoa))+
geom_boxplot(outlier.shape = NA)+
geom_point(aes(color=as.factor(depth)),position=position_jitter(width=0.2),size=2)+
theme_light()+ 
theme(legend.text = element_text(size = 15))+
facet_grid(.~depth)
```
![coverage in relation to site and depth](/images/fixt_relation_to_site.png)

This graph shows the distribution of Bryozoa coverage at two sites, Achziv and SdotYam, with each boxplot representing the variability in coverage at each site. The y-axis represents the percentage coverage of Bryozoa, while the x-axis differentiates the two sites. Each point represents an individual observation, color-coded by seafloor depth: 10 meters (red), 25 meters (green), and 45 meters (blue). The boxplots indicate that Achziv has a lower median coverage of Bryozoa compared to SdotYam, axsept in the 45 meter depth ther Achziv has a hayer median coverage though both sites exhibit wide variability. Points at 45 meters depth (green) show significant presence and higher coverage values at both sites.

Additionally we used two statistical tests: the Bartlett test to check whether the variances of Bryozoa coverage are equal across the two sites, and the Kruskal-Wallis test, a non-parametric method for testing whether samples originate from the same distribution

```r
#1. test homogeneity of variance

bartlett.test(Photosurvey$Bryozoa~Photosurvey$site)

#2. test difference in coverage levels

kruskal.test(Bryozoa~site, data=Photosurvey)
```
the Bartlett's output was: K-squared = 12.803, df = 1, p-value = 0.000346

A p-value of 0.000346 is much less than the common significance level (e.g., 0.05), indicating that the variances of Bryozoa coverage between the two sites are significantly different.

the Kruskal-Wallis output was: chi-squared = 9.8088, df = 1, p-value = 0.001737

A p-value of 0.001737 is much less than the common significance level (e.g., 0.05), indicating that there is a significant difference in Bryozoa coverage between Achziv and SdotYam.

## coverage in relation to season

```r
ggplot(Photosurvey, aes(x=season, y=Bryozoa, fill=site))+
geom_boxplot(outlier.shape = NA)+
geom_point(position=position_jitterdodge(jitter.width = 0.2), size=1)+
theme_light()+
facet_grid(.~depth)
```
![season_grath](/images/coverage_season.png)

 This graph illustrates the distribution of Bryozoa coverage across two sites (Achziv and SdotYam) and two seasons (Fall and Spring) at three different depths (10, 25, and 45 meters). Each panel represents a specific depth, with the x-axis indicating the season and the y-axis showing the percentage coverage of Bryozoa. Achziv is represented in red and SdotYam in blue. The boxplots display the median (horizontal line inside the box), the interquartile range (box), and the data range (whiskers), with individual data points overlaid. The graph shows that Bryozoa coverage varies widely across seasons and depths, with noticeable differences between the two sites. For instance, at 10 meters depth, SdotYam shows higher median coverage in Fall compared to Achziv, while at 25 meters, Achziv has higher coverage in Fall and lower in Spring. At 45 meters, Achziv consistently shows higher median coverage than SdotYam in both seasons. This indicates a complex interaction between site, season, and depth affecting Bryozoa coverage.

 ## correspondence/interaction (e.g., correlation) between Bryozoa and other taxonomic groups

 ```r
# variables 10 to 22 have the measurements
corrs=rcorr(as.matrix(Photosurvey[,10:22]), type="spearman")


#we need a function that will take the square matrix and turn it to long format.
flattenCorrMatrix <- function(cormat, pmat) {
  ut <- upper.tri(cormat)
  data.frame(
    row = rownames(cormat)[row(cormat)[ut]],
    column = rownames(cormat)[col(cormat)[ut]],
    cor  =(cormat)[ut],
    p = pmat[ut]
  )
}

#now we apply this function to our data
corrs_flat=flattenCorrMatrix(corrs$r, corrs$P)

#add p value adjustment using the Benjamini-Hochber method (BH)
corrs_flat$p.adj=p.adjust(corrs_flat$p, "BH")

write.csv(corrs_flat, "Taxonomic_groups_spearman.csv")

# now plot your correlation of interest e.g., my taxon of interest and live coverage
str(Photosurvey)

ggplot(Photosurvey, aes(x=Algae, y=Bryozoa))+
  geom_point()+
  geom_smooth(method='lm')+
  theme_light()
 ```
In summary this code performs a series of steps to calculate and visualize the correlations between different taxonomic groups in the Photosurvey data we chos to visualize the the correlations between Bryozoa and Algae

![season_grath](/images/correlations_between_Bryozoa_Algae.png)

This scatter plot shows the relationship between the percentage coverage of Algae and Bryozoa in the photo-survey data. Each point represents a sample from the survey. The x-axis represents Algae coverage, and the y-axis represents Bryozoa coverage. The plot includes a linear regression line (in blue) with a shaded area indicating the confidence interval. The negative slope of the line suggests a strong inverse relationship between Algae and Bryozoa coverage, indicating that as Algae coverage increases, Bryozoa coverage tends to decrease. This negative correlation is evident from the downward trend of the data points and the fitted regression line.

## Summary
This analysis of the benthic biota photo-survey data revealed significant variations in Bryozoa coverage across different sites, seasons, and seafloor depths. Achziv generally showed lower Bryozoa coverage compared to SdotYam, except at 45 meters depth where Achziv exhibited higher median coverage. Seasonal variations were also notable, with differences in Bryozoa coverage between Fall and Spring observed at various depths. Additionally, a strong negative correlation between Bryozoa and Algae coverage was identified, suggesting competitive interactions or other ecological dynamics influencing their distributions. These findings underscore the complexity of benthic ecosystems and highlight the importance of considering multiple environmental factors when assessing biotic coverage and interactions in marine habitats.
