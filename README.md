# Economics Education Research
Previous research has established that transition from face-to-face instruction to distance education during the COVID-19 pandemic adversely impacts the academic performance of students in grade 3 through 8. To date, however, little is known if similar effects of instruction mode changes apply to students with higher grade levels. This study investigates this gap by using high school test proficiency and dropout rates data from six U.S. states. Contrary to the existing literature, this study reveals that, on average, test performance remained stable during the pandemic, with no substantial widening of achievement gaps among marginalized groups. Additionally, the effect of instruction mode varied considerably across diverse education and social contexts, with some states demonstrating notable benefits from virtual and hybrid learning. Changes in dropout rates exhibit greater variability and less economic and statistical significance, suggesting intricate dropout dynamics influenced by various pandemic-related disruptions beyond mere instruction mode changes. 

Special thanks to Prof. Arvind Krishna, Prof. Charles Manski, Prof. Joel L. Horowitz, and Prof. Richard Walker for their guidance and constructive feedback.

Full Paper: [Impacts of Pandemic Instruction Mode on High School Students' Education Outcomes: Evidence from U.S. States](https://acrobat.adobe.com/id/urn:aaid:sc:VA6C2:2f0197f0-2f15-4698-a99c-dcd390efa3b7)

## Repository Description

>[!TIP]
>`<outcome>` is either mathpass, elapass, dropout, or all<br />
>`<state>` is the name of U.S. states<br />

### data: 

Each `state` folder contains replication code `<state>_cleaning.ipynb` used to create `<state>_<outcome>.csv` in the `final_csv` folder

Data Source: [Arizona](https://www.azed.gov/accountability-research/data), [Colorado](https://www.cde.state.co.us/cdereval), [Georgia](https://gosa.georgia.gov/dashboards-data-report-card/downloadable-data), [Illinois](https://www.isbe.net/Pages/Data-Analysis.aspx), [Indiana](https://www.in.gov/doe/it/data-center-and-reports/), [Wisconsin](https://dpi.wi.gov/wisedash/download-files/type?field_wisedash_upload_type_value=All), [COVID-19 Instruction Mode](https://www.covidschooldatahub.com/)

### descriptive_analysis:

> [!NOTE]  
> In social science research, descriptive analysis is pivotal for unveiling data patterns and characteristics. This study visualizes test proficiency and dropout rate changes by state, demographics, and instruction modes to effectively communicate complex information in a concise and accessible manner. However, it is crucial to acknowledge that these changes cannot be used to draw significant conclusions about the effect of instruction mode on education outcomes. An identification strategy is essential to disentangle other factors and biases. Attention to statistical significance of weighted point estimates reinforces the need for caution in drawing insights solely from descriptive graphs.

`descriptive_analysis.ipynb`: replication code used to create weighted mean csv file in the `figure_csv` folder

`descriptive_analysis_ci.ipynb`: replication code used to output the 95% confidence interval of weighted mean calculations

`figure_csv`: csv files used to generate figures in the `figure` folder via Stata

### influential_analysis: 

> [!NOTE]  
> Influential point analysis is used to ensure the reliability of statistical results. By identifying and removing observations that exert substantial influences on parameters of interest, this study strengthens the validity and generalizability of regression results. The DFBETAS are statistics that indicate the effect deleting each observation has on the estimates for the regression coefficients. A high DFBETAS value indicates high influence of an observation and should be considered to remove to ensure that the estimated coefficients are not skewed by certain high-influential observations and thus not representative of the total population.

`before_removal_dfbetas`: DFBETAS values for each parameter of interest before influential entities removal

`after removal_dfbetas`: DFBETAS values for each parameter of interest after influential entities removal

`dfbetas_computation.ipynb`: replication code used to create DFBETAS values

`dfbetas_visualization.ipynb`: replication code used to create DFBETAS plots

`removed_entities`: influential enitities ultimately removed in the final data sample

### model_diagnostic:

> [!NOTE]
> Although the choice of model specifications is initiated with domain knowledge, rigorous statistical analysis is conducted to ensure the appropriateness of model selection and that the data sample suffices key model assumptions. Residuals, studentized residuals, and Cook's distance are plotted to assess the adequacy of regression models and to further identify influential data points. 

`model_diagnostic.ipynb`: replication code for model selection, model assumption check, and plotting residuals, studentized residuals, and Cook's distance

### visualization:

Each `outcome` folder contains visualizations of DFBETAS plots, residual plots, studentized residual plots, and cook's distance plots

