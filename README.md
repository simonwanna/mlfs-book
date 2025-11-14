Jacob Schweizer and Simon Wanna

### Grade ‘E’ tasks
- [x] 1. Write a backfill feature pipeline that downloads historical weather data (ideally >1 year of data), loads a csv file with
historical air quality data (downloaded from https://aqicn.org) and registers them as 2 Feature Groups with Hopsworks.
- [x] 2. Schedule a daily feature pipeline notebook that downloads yesterday’s weather data and air quality data, and also the
weather prediction for the next 7-10 days and update the Feature Groups in Hopsworks. Use GH Actions or Modal.
- [x] 3. Write a training pipeline that (1) selects the features for use in a feature view, (2) reads training data with the Feature
View, trains a regression or classifier model to predict air quality (pm25). Register the model with Hopsworks.
- [x] 4. Write a batch inference pipeline that creates a dashboard. The program should download your model from Hopsworks
and plot a dashboard that predicts the air quality for the next 7-10 days for your chosen air quality sensor.
- [x] 5. Monitor the accuracy of your predictions by plotting a hindcast graph showing your predictions vs outcomes
(measured air quality).

### Comments
We downloaded air quality data from the sensor at Linköping Hamngatan-10. After adding the keys/secrets we ran the backfill and training pipelines to create the feature groups, feature views and trained model stored in Hopsworks. Running the workflow published the github pages with predictions and model performance monitoring.

**Note**: need to set status_options: '--untracked-files=all' in workflow to include the generated dashboard files in the commit to update model monitor image.

---

### Grade ‘C’ tasks
- [x] 6. Update your Model by adding a new feature, lagged air quality for the previous 1 day, 2 days, and 3 days. Measure and
explain the performance improvement or regression for these features.

### Comments
We update the third notebook with a block that extend the feature with a lagged version of PM 2.5.

Comparison of performance before and after adding lagged features:

Before: 
- MSE: 137.79417
- R squared: -0.04968505950108093

After:
- MSE: 74.90364
- R squared: 0.43133222360284207

---

### Grade ‘A’ tasks
- [] 7. Provide predictions for all air quality sensors in a Swedish city. Select a city by entering your group number here.
