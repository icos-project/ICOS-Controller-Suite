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

In this version, the AI coordination API will offer a mechanism for estimating the CPU consumption of the
ICOS agents. This API endpoint service will save a reference to the saved model in the AI analytics module,
which is a CPU-usage prediction model in this case. When a request is made to the API, this model will
forecast CPU usage one minute in the future.

Version 1.3 introduced MLFlow and Jupyter Lab and JupyterHub support, plus notebooks with examples about how to use the API.

Version 2.0 introduces mechanisms for detecting drift and explain model predictions to imporove AI trustworthiness.

## Steps to launch Jupyter services

### 1. JupyterHub

- Run docker command to get inside the ICOS Intelligence Coordination API docker and execute below command:
``` docker exec -u root -it icos_intelligence_docker /bin/bash ```

- Once inside the docker, create users to access your own jupyterhub account
```passwd bentoml```

- Now launch jupyterhub as root pointing to the provided config file:
```jupyterhub -f /path/to/jupyterhub_config.py```
This file should be within the container in `src/notebooks`

- Finally, access jupyterhub from the your browser and enter the password selected for the bentoml user.

### 2. JupyterLab

- Run the POST request from the ICOS Intelligence UI to start the jupyterlab instance with your desired port and token id
```jupyter lab --port 8888 --NotebookApp.token=‘icos_1234’```
- Now access your jupyterlab session from the browser.

## Legal
The ICOS Coordination API is released under the GNU General Public License v3.
Copyright © 2022-2024 CeADAR Ireland. All rights reserved.

🇪🇺 This work has received funding from the European Union's HORIZON research and innovation programme under grant agreement No. 101070177.
