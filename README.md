
# IBM Developer Model Asset Exchange: Fairness Measures

This is an library to measure fairness measures. It uses AIF Fairness 360 toolkit.
The AI Fairness 360 toolkit is an open-source library to help detect and remove bias in machine learning models. The AI Fairness 360 Python package includes a comprehensive set of metrics for datasets and models to test for biases, explanations for these metrics, and algorithms to mitigate bias in datasets and models.

The AI Fairness 360 interactive experience provides a gentle introduction to the concepts and capabilities. The tutorials and other notebooks offer a deeper, data scientist-oriented introduction. The complete API is also available.

Being a comprehensive set of capabilities, it may be confusing to figure out which metrics and algorithms are most appropriate for a given use case. To help, we have created some guidance material that can be consulted.

We have developed the package with extensibility in mind. This library is still in development. We encourage the contribution of your metrics, explainers, and debiasing algorithms.



## Model Metadata
| Domain | Application | Industry  | Framework | Training Data | Input Data Format |
| ------------- | --------  | -------- | --------- | --------- | -------------- |
| structured | Classification | Banking | Scikit | Adult | CSV file |

## References

Optimized Preprocessing (Calmon et al., 2017)
Disparate Impact Remover (Feldman et al., 2015)
Equalized Odds Postprocessing (Hardt et al., 2016)
Reweighing (Kamiran and Calders, 2012)
Reject Option Classification (Kamiran et al., 2012)
Prejudice Remover Regularizer (Kamishima et al., 2012)
Calibrated Equalized Odds Postprocessing (Pleiss et al., 2017)
Learning Fair Representations (Zemel et al., 2013)
Adversarial Debiasing (Zhang et al., 2018)
Meta-Algorithm for Fair Classification (Celis et al.. 2018)


## Licenses

OpenSource


## Pre-requisites:

* python flask
* python 3.6/2.7


# Steps

1. install IBM AIF360
2. Install black box auditing
3. Install Flask
4. Run python app.py



### 3. Use the Model

The API server automatically generates an interactive Swagger documentation page. Go to `http://{server}:6000` to load
it. From there you can explore the API and also create test requests.


You should see a JSON response like that below:

```
{
    "accuracy": 0.4150359314538419,
    "average_abs_odds_difference": 0.12442294799467912,
    "average_odds_difference": -0.12442294799467912,
    "base_rate": 0.2504145936981758,
    "between_all_groups_coefficient_of_variation": 0.02370441198845565,
    "binary_confusion_matrix": {
        "FN": 3,
        "FP": 5288,
        "TN": 1492,
        "TP": 2262
    },
    "disparate_impact": 0.7305508105661994,
    "equal_opportunity_difference": -0.002138389696761056,
    "error_rate": 0.5849640685461581,
    "error_rate_difference": -0.03624433173950825,
    "error_rate_ratio": 0.9392555315892861,
    "false_discovery_rate": 0.7003973509933775,
    "false_discovery_rate_difference": 0.1862850042142511,
    "false_discovery_rate_ratio": 1.2855995998344993,
    "false_negative_rate": 0.0013245033112582781,
    "false_negative_rate_difference": 0.0021383896967610786,
    "false_negative_rate_ratio": 3.083860759493671,
    "false_omission_rate": 0.002006688963210702,
    "false_omission_rate_ratio": 0.2706185567010309,
    "false_positive_rate": 0.7799410029498525,
    "false_positive_rate_difference": -0.2467075062925972,
    "false_positive_rate_ratio": 0.7179617089891585,
    "generalized_binary_confusion_matrix": {
        "GFN": 1092.9851565078861,
        "GFP": 1084.184219398682,
        "GTN": 5695.815780601319,
        "GTP": 1172.0148434921139
    },
    "generalized_entropy_index": 0.0485171091737039,
    "negative_predictive_value": 0.9979933110367893,
    "num_false_negatives": 3,
    "num_false_positives": 5288,
    "num_generalized_false_negatives": 1092.9851565078861,
    "num_generalized_false_positives": 1084.184219398682,
    "num_generalized_true_negatives": 5695.815780601319,
    "num_generalized_true_positives": 1172.0148434921139,
    "num_pred_negatives": 1495,
    "num_pred_positives": 7550,
    "performance_measures": {
        "ACC": 0.4150359314538419,
        "FDR": 0.7003973509933775,
        "FNR": 0.0013245033112582781,
        "FOR": 0.002006688963210702,
        "FPR": 0.7799410029498525,
        "GFNR": 0.4825541529836142,
        "GFPR": 0.15990917690246048,
        "GTNR": 0.8400908230975397,
        "GTPR": 0.5174458470163859,
        "NPV": 0.9979933110367893,
        "PPV": 0.29960264900662253,
        "TNR": 0.2200589970501475,
        "TPR": 0.9986754966887417
    },
    "positive_predictive_value": 0.29960264900662253,
    "selection_rate": 0.8347153123272526,
    "statistical_parity_difference": -0.2463497732919414,
    "theil_index": 0.051421746623506064,
    "true_negative_rate": 0.2200589970501475,
    "true_positive_rate": 0.9986754966887417,
    "true_positive_rate_difference": -0.002138389696761056
}
```

### 4. Development

To run the Flask API app in debug mode, edit `config.py` to set `DEBUG = True` under the application settings. You will
then need to rebuild the Docker image (see [step 1](#1-build-the-model)).

