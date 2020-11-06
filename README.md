---
title: "Tools for Quantitative Archaeology – in R"
authors:
  - "Joe Roe <<joe@joeroe.io>>"
date: "2020-11-06"
output:
  md_document:
    variant: "markdown_github"
    preserve_yaml: true
---

<!-- Generated from README.Rmd -->

[Tools for Quantitative Archaeology](http://tfqa.com) (TFQA) is a
collection of DOS programs developed by Keith Kintigh to perform
statistical analyses used in archaeology. TFQA includes 50 programs and
so gives a good representation of the range of analyses used by
archaeologists. The purpose of this document is to track which of these
analyses are currently available in R packages. We hope it will be
useful in both porting TFQA-based analyses to R, and in highlighting
which methods are not yet implemented in R packages.

The table below presents a list of [TFQA
programs](http://tfqa.com/programs.htm) and their equivalent functions
in R. By “equivalent”, we mean R functions that provide substantially
the same functionality as the original TFQA program with a similar
high-level user interface; we can assume that all of the analyses listed
can be performed in R if the user is prepared to reimplement them
themselves. The list of R equivalents is also not intended to be
exhaustive. The packages/functions listed are a subjective assessment of
the “best” (most complete/widely used/actively maintained) way to get
the same results as the TFQA program using R. See
[open-archeo.info](http://open-archaeo.info/) for a general list of
archaeology-related R packages.

TFQA is still available and actively maintained. Some of the more
recently added programs are also available as free and open source
software (see <https://github.com/kintigh>). Matt Peeples has also
[ported many to R scripts](https://mattpeeples.net/?page_id=656). This
list should therefore be seen as list of alternatives to TFQA (for those
who prefer R, open source software, and/or cannot run DOS programs),
rather than superseding it.

This is a work-in-progress. Please feel free to contribute by [editing
the table](/sslarch/tfqar/blob/main/tfqar.csv) and submitting a pull
request, or [opening an issue](/sslarch/tfqar/issues) with suggestions.

R equivalents of TFQA programs
------------------------------

Generated from [tfqar.csv](/sslarch/tfqar/blob/main/tfqar.csv).

<!--html_preserve-->
<div id="ckxxmrkxau"
style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">
<thead class="gt_col_headings">
<tr>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
TFQA Program
</th>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
Description
</th>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
Available in R?
</th>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
R package(s)
</th>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
R function(s)
</th>
<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="font-weight: bold;">
Notes
</th>
</tr>
</thead>
<tbody class="gt_table_body">
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Spatial Analysis
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CONTIG
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Monte Carlo evaluation of the statistical significance of the observed…
</summary>
Monte Carlo evaluation of the statistical significance of the observed
degree of contiguity of grid units assigned to the same cluster.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
FISHER
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Calculates Fisher’s Exact test
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
stats
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
stats::fisher_test()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
GRID
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Aggregates point-provenience data into counts by type for each grid…
</summary>
Aggregates point-provenience data into counts by type for each grid
unit.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://r-spatial.github.io/sf/">sf</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
sf::st_join()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://mattherman.info/blog/point-in-poly">Tutorial</a>
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
HOA
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Computes Hodder and Okell’s A and dispersion ratios
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
KMEANS
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs k-means cluster analysis with extensive output designed to
facilitate…
</summary>
Performs k-means cluster analysis with extensive output designed to
facilitate interpretation. The program can be used to cluster analyze
any data set, but has special features developed for use in
archaeological spatial analysis. In particular, Kintigh and Ammerman’s
(1982) k-means pure locational clustering method can be performed. The
program also executes the clustering for Whallon’s (1984) unconstrained
clustering method on data smoothed using the GRID or LDEN programs.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
Unpackaged script:
<a href="https://github.com/mpeeples2008/Kmeans">mpeeples2008/Kmeans</a>
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
KMPLT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Plots the SSE and (2 dimensional) cluster configuration results of…
</summary>
Plots the SSE and (2 dimensional) cluster configuration results of
KMEANS on screen and creates hard-copy publishable quality plots
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
Unpackaged script:
<a href="https://github.com/mpeeples2008/Kmeans">mpeeples2008/Kmeans</a>
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
KOETJE
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs the Monte Carlo analysis of homogeneity of cluster
configurations…
</summary>
Performs the Monte Carlo analysis of homogeneity of cluster
configurations as suggested by Koetje (1987).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
LDEN
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs Johnson’s (1984) Local Density Analysis on point-provenienced
or grid…
</summary>
Performs Johnson’s (1984) Local Density Analysis on point-provenienced
or grid data. The program also outputs counts or percentages of points
of different types that occur within a circular neighborhood around each
data point.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
LDPLT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Plots selected local density coefficients computed by LDEN against
radius,…
</summary>
Plots selected local density coefficients computed by LDEN against
radius, so behavior of coefficients for different pairs of classes can
be easily observed over a range of radii
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
NEIG
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
An efficient, general-purpose nearest-neighbor (Whallon 1984) and
gravity model program…
</summary>
An efficient, general-purpose nearest-neighbor (Whallon 1984) and
gravity model program useful for intrasite spatial analysis or regional
analysis. It allows categorization of items by class (e.g. site type or
tool type) and permits the calculation of within or between class
neighbors.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
RANDPT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Generates random sets of coordinates, including for clumped
distributions with…
</summary>
Generates random sets of coordinates, including for clumped
distributions with different parameters. Also random walks any number of
points in an existing distribution with arbitrary number of steps and
step length.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Partially
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://spatstat.org/">spatstat</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
spatstat::rpoint()<br />spatstat::runifpoint()<br />spatstat::rpoispp()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
Not sure about the “random walk” part.
</p>

</div>

</td>
</tr>
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Diversity
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
BOONE
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Calculates, for a set of proveniences with counts by artifact…
</summary>
Calculates, for a set of proveniences with counts by artifact class,
Boone’s (1987) assemblage heterogeneity measure and related values.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
DIVERS
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Calculates richness and evenness (H/Hmax) dimensions of diversity for a…
</summary>
Calculates richness and evenness (H/Hmax) dimensions of diversity for a
given data set and uses Monte-Carlo methods to derive expected diversity
for a model distribution over a range of sample sizes (Kintigh 1984,
1989).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
DIVMEAS
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Calculates several diversity measures including Richness, Simpson’s,
Shannon’s, Brillouin’s, and…
</summary>
Calculates several diversity measures including Richness, Simpson’s,
Shannon’s, Brillouin’s, and the Renyi and Delta families of generalized
diversity measures for any given distribution of counts.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://tabula.archaeo.science/">tabula</a>,
<a href="https://CRAN.R-project.org/package=vegan">vegan</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
tabula::index_richness()<br />tabula::index_heterogeneity()<br />vegan::renyi()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
tabula is not currently available on CRAN
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
DIVPLT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Plots the results of DIVERS on screen and creates publishable…
</summary>
Plots the results of DIVERS on screen and creates publishable quality
plots
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
EVALC
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs a Monte Carlo evaluation of the significance of an…
</summary>
Performs a Monte Carlo evaluation of the significance of an observed
value of Simpson’s C measure of diversity relative to a given assumption
about the population.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
RAREFY
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs rarefaction analysis for sets of sample counts in a…
</summary>
Performs rarefaction analysis for sets of sample counts in a CSV file as
described by Baxter (2001). Provides expected richness, standard
deviation of the expected, Z score, and probability for each larger
sample to every smaller sample size. Also outputs expected richness for
each sample up to its sample size for graphing.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Distance
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
BAYES
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
This program implements Bayesian methods for proportions as described
by…
</summary>
This program implements Bayesian methods for proportions as described by
Iversen (1984). Intervals are calculated and graphed for Bayesian
estimates of proportions based on both flat and informative priors.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
BINOMIAL
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Computes binomial probabilities and population proportion intervals for
a sample.
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
BRSAMPLE
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Provides a Monte Carlo estimate of the sampling error of…
</summary>
Provides a Monte Carlo estimate of the sampling error of differences of
the Brainerd Robinson coefficient calculated between a sample and a
known population or between two samples drawn from the same population
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CLCA
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs a Complete Linkage Cluster Analysis on up to 180…
</summary>
Performs a Complete Linkage Cluster Analysis on up to 180 cases. It
takes as input an upper triangular distance matrix, as is created by the
DIST program. As output, it lists the sequence of item/cluster joins and
fusion values but does not create a dendrogram.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
DIST
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Computes a triangular matrix of distance or similarity measures:
Euclidean…
</summary>
Computes a triangular matrix of distance or similarity measures:
Euclidean Distance, Pearson’s r, Brainerd-Robinson Coefficient,
Jaccard’s Coefficient, Simple Matching Coefficient, and Gower
Coefficient.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Partially
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://CRAN.R-project.org/package=vegan">vegan</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
vegan::vegdist()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
vegan implements Euclidean, Jaccard, and Gower distances.
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
FORD
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Plots a publishable quality battleship curve (Ford) diagram
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://tabula.archaeo.science/">tabula</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
tabula::plot_ford()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
tabula is not currently available on CRAN
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
POISSON
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Computes Poisson and negative binomial probabilities, given expected
counts.
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
resampleBRED
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Provide Monte Carlo estimates of the sampling error of differences…
</summary>
Provide Monte Carlo estimates of the sampling error of differences of
the Brainerd-Robinson and Euclidean Distance coefficients calculated
between a sample and a known population or between two samples drawn
from the same population, as described and applied in Deboer et
al. (1996).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
TWOWAY
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Provides tests of independence and measures of association and prints…
</summary>
Provides tests of independence and measures of association and prints
tables that have been standardized with a number of techniques. Standard
Chi² and G tests of independence are provided. Using Monte Carlo
methods, Chi² and G tests can be performed on tables with very small
expected counts. A Chi² goodness of fit test (with externally determined
expected values) can also be calculated. Measures of association include
Yule’s Q, Phi, Cramer’s V and proportional reduction of error measures
Tau and Lambda. Table standardization methods include median polish
(Lewis 1986) and Mosteller (multiplicative) standardization as well as
Haberman’s z-score standardization for independent variables used by
Grayson (1984) and Allison’s binomial probability-based z-score
standardization. It will also print row, column, and cell percents, Chi²
cell contributions, and Chi² expected values.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Dating and Demography
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
ARRANGE
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Creates a probabilistic estimate of the range of site dates…
</summary>
Creates a probabilistic estimate of the range of site dates based on the
proportions of dated ceramic types in the assemblage. Output includes a
density plot against time. The program also calculates mean ceramic
dates. This method is described in Steponaitis and Kintigh (1993).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
Unpackaged script:
<a href="https://github.com/mpeeples2008/Mean-Ceramic-Date-and-Error-Estimation">mpeeples2008/Mean-Ceramic-Date-and-Error-Estimation</a>
</p>

</div>

</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
C14
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
provides a graphical way to analyze sets of radiocarbon dates….
</summary>
provides a graphical way to analyze sets of radiocarbon dates. Each
radiocarbon date is treated not as a single point in time but as a
normally distributed probability with a mean and standard deviation
given by the lab. In evaluating several dates, for each interval the
probability distributions associated with the dates are summed. For each
temporal interval, an expected number of dates is calculated and plotted
in a histogram.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://github.com/ahb108/rcarbon/">rcarbon</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
rcarbon::plot()<br />rcarbon::spd()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CALCULATE_K
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Calculates K for for use in Cowgill’s formula that estimates…
</summary>
Calculates K for for use in Cowgill’s formula that estimates the span of
true interval producing an observed set of measured dates with Gaussian
errors. It calculates the value of K for any standard deviation of a
Normal Distribution. See Cowgill and Kintigh (2020).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
DSPLIT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Compares and combines radiocarbon samples using the procedure published
in…
</summary>
Compares and combines radiocarbon samples using the procedure published
in Archaeometry by Wilson and Ward (1981).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
MATCHINTERVAL
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Performs a MonteCarlo evaluation of the correspondence between temporal
intervals…
</summary>
Performs a MonteCarlo evaluation of the correspondence between temporal
intervals with extreme climate events and the occurrence dates of major
cultural changes as described and applied by Kintigh & Ingram (2018).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
PHASELEN
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Provides a Monte Carlo analysis to estimate the span of…
</summary>
Provides a Monte Carlo analysis to estimate the span of true span
producing an observed set of measured dates with Gaussian errors such as
radiocarbon and obsidian hydration dates. The program has an option for
calibration.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
ROOMACCUM
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Estimates within-period rates of population growth (or decline) given
structure…
</summary>
Estimates within-period rates of population growth (or decline) given
structure counts dated to a sequence of chronological periods as
described and applied by Kintigh and Peeples (2020). It assumes a
knowledge of the number of structures that date to each specific period,
the period lengths, and an estimated structure use life. The population
growth rate estimates are derived by simulating the construction (due to
replacement and population growth) and abandonment (due to the
completion of the use life or population decline) of individual
structures such that the observed number of rooms dating to a period
matches the simulated number of rooms.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Subsurface Testing
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
PLACESTP
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Calculates the optimal placement of test units in a rectangular…
</summary>
Calculates the optimal placement of test units in a rectangular or
linear survey area. For a user-specified number of survey transects (or
user-specified lengthwise and width-wise spacing of test units), in any
one of three basic configurations, the program will print out the
coordinates of the optimal test unit placement, along with some
statistics about the largest circular site that can go unsampled in the
survey area. This program implements the formulae provided by Krakker,
Shott, and Welch (1983) and revised in Kintigh (1988).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
STP
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Probabilistic evaluation of subsurface testing designs as described in
Kintigh…
</summary>
Probabilistic evaluation of subsurface testing designs as described in
Kintigh 1988. STP uses Monte-Carlo methods to evaluate the effectiveness
of a test unit layout within a survey area to locate sites with a given
size and artifact density.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr class="gt_group_heading_row">
<td colspan="6" class="gt_group_heading" style="font-weight: bold;">
Utility
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
ADFUTIL
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Generates random data sets and manipulates files in the data…
</summary>
Generates random data sets and manipulates files in the data format used
by the analysis programs. It allows the creation of random data set of
any size. Variables may be uniform or normally distributed variables
with user specified ranges or means standard deviations. ADFUTIL allows
the deletion of columns (variables), selective deletion of rows
(observations) based on values in a column, replacement of values in a
column, randomization of columns for Monte Carlo analysis, the addition
of new columns from another data set, and selection of a random sample
of cases.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CNTCNV
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Program to speed data input and increase entry accuracy for…
</summary>
Program to speed data input and increase entry accuracy for count data,
where the number of categories is large relative to the number of items
counted for an observation (e.g. surface collection counts of 40 ceramic
type divided into 8 vessel forms). It permits a highly abbreviated input
format but it writes out a standard matrix (of the sort read by most
analysis programs) with one count per category of each observation. The
program provides labeled printouts of the data and can perform elaborate
aggregation of count categories and simple aggregation of observations.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CntEdit
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
CntEdit is a companion program to CNTCNV and can be…
</summary>
CntEdit is a companion program to CNTCNV and can be used to do global or
selective substititions of row or column field values in a data file
formatted for CNTCNV.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CntRefmt
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
CntRefmt is a companion program to CNTCNV that reformats
row-column-count…
</summary>
CntRefmt is a companion program to CNTCNV that reformats
row-column-count segments of records formatted for CntCnv, e.g, to make
differently formatted files consistent or to change the spacing to make
reading easier.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
CONVSYS
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Converts a SYSTAT internal format data file into a raw…
</summary>
Converts a SYSTAT internal format data file into a raw data file, a
variable label file, and a case label file that can be used these and
other programs that read free-format ASCII data. Works with versions 2.0
and above of SYSTAT, on files of any size.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
HPPLOT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Provides a flexible user interface to a Hewlett Packard compatible…
</summary>
Provides a flexible user interface to a Hewlett Packard compatible
plotters. Its can create a customized analysis graphics from a raw data
file edited to include the plot commands.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
MVC
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Permits arbitrarily complex copying of sets of columns in an…
</summary>
Permits arbitrarily complex copying of sets of columns in an input
record into sets of columns in an output record. It can extract data
from fixed-format data records for use with analytical programs that
require free format input. Files of any size can be processed.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
SCAT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Produces screen and publishable quality scatter plots of variables. All…
</summary>
Produces screen and publishable quality scatter plots of variables. All
points may be plotted with the same symbol, or different symbols can be
plotted based on the value of a variable.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://ggplot2.tidyverse.org/">ggplot2</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
ggplot2::geom_point()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
SORTLINE
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
A general purpose sort utility, SORTLINE sorts fixed-format data files…
</summary>
A general purpose sort utility, SORTLINE sorts fixed-format data files
of up to 32,767 lines into an order defined by any number of
user-specified sort fields.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
Yes
</td>
<td class="gt_row gt_left" style="vertical-align: top;">

<div class="gt_from_md">

<p>
<a href="https://dplyr.tidyverse.org/">dplyr</a>
</p>

</div>

</td>
<td class="gt_row gt_left" style="vertical-align: top;">
dplyr::arrange()
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
SPLIT
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Divides a large file into sections that can be recombined…
</summary>
Divides a large file into sections that can be recombined with the DOS
COPY command. Thus, large hard disk file can be split and copied onto
several floppies.
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
<tr>
<td class="gt_row gt_left" style="vertical-align: top;">
UNTAB
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
<details>
<summary>
Replaces tabs and control characters in a file with blanks…
</summary>
Replaces tabs and control characters in a file with blanks so they can
be used with analysis programs that require pure ASCII files
(e.g. SYSTAT).
</details>
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
<td class="gt_row gt_left" style="vertical-align: top;">
</td>
</tr>
</tbody>
<tfoot class="gt_sourcenotes">
<tr>
<td class="gt_sourcenote" colspan="6">
TFQA program descriptions copied from
<a href="http://tfqa.com/programs.htm">http://tfqa.com/programs.htm</a>
</td>
</tr>
</tfoot>
</table>

</div>

<!--/html_preserve-->
