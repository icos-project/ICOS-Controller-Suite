# ICOS Intelligence Coordination API 

## Credits

- The Innovation and Development Group of CeADAR, Ireland's National Centre for Applied AI, based in University College Dublin, has defined the CPU utilization models and developed this full API and its setup. Jaydeep Samanta, Sebastian Cajas Ordoñez, Dr. Andrés L. Suárez-Cetrulo and Dr. Ricardo Simón Carbajo have performed this work.
- The National and Kapodistrian University of Athens (NKUA) has contributed with anomaly detection and LSTM models for the current version.
- This work has been performed as part of partial fulfillment of the Intelligence layer of the EU HORIZON project No. 101070177 with name IoT to Cloud Operating System (ICOS).

## License

- All sourcecode in this repository is developed by CeADAR Ireland under GNU GPL v3. 
- This API and cpu utilisation models, plus ARIMA functions to work over the main frameworks, are licensed under GNU v3.0 by CeADAR Ireland.
- LSTM models and classification models for anomaly detection by NKUA, as a subpart of the runnable files but not source code. Source code by NKUA is not part of this repository. Such source code may or not follow a similar license to this repository.

## Version 2.0

The AI coordination module facilitates optimisation, predictive analytics, and applying machine learning
models across the edge-cloud continuum. It entails implementing policies for utilising, sharing, and
updating models. This acts as an interface and provides coordination between the meta-kernel and user
layers providing and requesting services. This component helps to coordinate with other intelligence
layers of the same domain in the continuum, providing ICOS with the ability to learn collaboratively.

In this version, the AI coordination API will offer a mechanism for estimating the CPU and memory consumption 
of the ICOS agents. This API endpoint service will save a reference to the saved model in the AI analytics module,
which is a CPU-usage or Memory-usage prediction model in this case. When a request is made to the API, this model will
forecast metric usage one minute in the future. This version will also provides mechanisms for detecting drift
and explain model predictions to improve AI trustworthiness. Additionally, each prediction will provide a confidence 
score and confidence interval to indicate how good is the prediction. Finally, to address complex resource management
scenarios, a new Pytorch model (POC) for multivariate prediction is added to predict combined CPU and memory forecasting
along with capabilities to perform model compression.

Version 1.3 introduced MLFlow and Jupyter Lab and JupyterHub support, plus notebooks with examples about how to use the API.

Version 2.0 introduces mechanisms for detecting drift and explain model predictions to imporove AI trustworthiness.

Version 2.0.3 introduces new Pytorch model to train multivariate metrics (CPU and Memory), perform model compression
and provides learning curves in MLFlow. This version also provides model confidence scores along with predictions. Jupyterlab
and JupyterHub support is removed from this version and added in the agent suite.

## Legal
The ICOS Coordination API is released under the GNU General Public License v3.
Copyright © 2022-2024 CeADAR Ireland. All rights reserved.

🇪🇺 This work has received funding from the European Union's HORIZON research and innovation programme under grant agreement No. 101070177.
