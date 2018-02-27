---
output: html_document
---

# Exploring predictors of impaired fasting glucose during adolescence - a longitudinal study

This repository contains my MSc Statistics dissertation for Sheffield University; submitted August 2017. 

## Background

The prevalence of childhood overweight and obesity are rising and have multiple causes. Consequences for health include the development of diabetes and it is therefore important to identify individuals at risk. Simple measures of adiposity such as BMI are limited due to their inability to distinguish fat from lean mass whereas dual-energy X-ray absorptiometry (DEXA) is considered a gold standard technique for body composition assessment. A novel measure of DEXA-derived body shape (trunk to leg volume) been proposed in adults [1] but this has not been assessed in children. 

## Objective

The aim of this project was to investigate how total and regional body composition changes during adolescence, particularly in relation to gender and pubertal timing, can be used to predict the onset of impaired fasting glucose. 

## Methods

347 normal healthy children (173 male; 174 female) from the EarlyBird prospective study were considered for this study to model their prevalence of impaired fasting glucose ($5.6$mmol/L $\geq$ glucose $<7$mmol/L) between ages 9 and 16. Missing data were substantial and were imputed where necessary to facilitate reasonable models using last observation carried forward and mean imputation methods. Separate models for total body measures, regional body measures and trunk to leg volume ratio were considered. Measures included both lean and fat indices (or percentage for the regional models), physical activity, age, gender and socio-economic status. Generalised linear mixed effect models were used assuming a random effect for each child to adjust for individual trend effects and a Lasso approach was used to identify important independent variables.

## Results

Only 198 children (95 male; 103 female) were considered suitable for the study due to data completeness after imputation, of which 36 (23 male; 13 female) had detectable impaired fasting glucose. For the models considering only total body lean and fat indicies, the Lasso algorithm found total body lean mass index to be highly significant ($p < 0.001$) and positive whereas total body fat mass index was removed (the parameter was shrunk to zero). The algorithm also found age to be positive and highly significant ($p < 0.001$) and the interaction between age and lean mass index to be highly significant ($p < 0.001$) and negative; and all other parameters were removed from the model. The interaction effect between age and lean mass index is complex; children with lower lean mass indices at a younger age have lower odds of developing impaired fasting glucose but have a higher risk closer to adulthood than those children with higher lean mass index. The interaction parameter was much smaller than age and lean mass index.

Regional models focussed on lean or fat mass percentages of compartmental areas of the body: trunk, arms and legs. The lean mass percentage model found only the trunk lean mass percentage to be significant ($p < 0.05$). The interaction between the lean masses and age were important, though non-significant ($p > 0.05$), in the model. The regional fat percentage model showed that trunk fat percentage ($p < 0.05$) and its interaction with gender ($p < 0.05$) are indicative of impaired fasting glucose though many other non-significant ($p > 0.05$) variables were retained in the model. Converse to the total body and regional lean percentage models, gender and age remain in the model though are non-significant ($p > 0.05$).

No evidence was found to suggest that the novel trunk to leg volume ratio is indicative of impaired fasting glucose in children as this variable was removed from all models by the Lasso.

## Conclusion

Lean mass index and age are indicative in the prevalence of impaired fasting glucose in children along with their interaction. This is in contrast with other research which typically suggests [2, 3] that it is fat levels which are indicative and not lean levels, though this is usually measured in adults. Given the complexity of the interaction, it may well be that lean mass index is important in the prevalence of pre-diabetes in children but it is fat mass index that is important for adults.

## References

1 Wilson J, Kanaya A, Fan B et al. Ratio of trunk to leg volume as a new body shape metric for diabetes and mortality. 2013;**8**:e68716. doi:10.1371/journal.pone.0068716

2 Gómez-Ambrosi J, Silva C, Galofré JC et al. Body adiposity and type 2 diabetes: Increased risk with a high body fat percentage even having a normal bmi. Obesity (Silver Spring) 2011;**19**:1439–44. doi:10.1038/oby.2011.36

3 Weiss R. and Caprio S. The metabolic consequences of childhood obesity. Best Pract Res Clin Endocrinol Metab 2005;**19**(3):405-419. doi:10.1016/j.beem.2005.04.009