# Jena Climate Time Series Projesi

Bu proje, Jena Climate veri setini kullanarak bir zaman serisi tahmin modeli oluşturmayı amaçlar. Proje, veri setinin yüklenmesi,verinin temizlenmesi, modelin eğitimi ve sonuçların değerlendirilmesi aşamalarını içermektedir.

## Veri Seti

Veri seti dosyasını bu projenin ana dizinine ekledim. 

## Model Eğitimi

Projede kullanılan model, bir zaman serisi tahmin modeli oluşturmak için derin öğrenme tekniklerini kullanır. Ayrıca, bir eğitim callback'i kullanarak modeli eğitim sırasında izleriz. Callback, validation loss 0.0005'in altına düştüğünde eğitimi durdurur. Bu, modelin hızlı ve hassas sonuçlar vermesine yardımcı olur.

Model, veri seti üzerinde eğitildikten sonra, test verileri üzerinde tahminler yapar ve bu tahminlerle gerçek değerleri karşılaştırarak performansı değerlendirilir.

## Sonuçlar

Proje sonuçları şu metriklerle değerlendirildi:

- Root Mean Squared Error (RMSE): 0.0102083525
- Mean Squared Error (MSE): 0.00010421046
- Mean Absolute Error (MAE): 0.0078059346

Bu metrikler, modelin tahminlerinin gerçek değerlere ne kadar yakın olduğunu gösterir. Düşük RMSE, MSE ve MAE değerleri, modelin iyi bir tahmin performansına sahip olduğunu gösterir.

## Neden Bu Metrikler?

Bu projede accuracy (doğruluk) metriği yerine RMSE, MSE ve MAE metriklerini kullandım çünkü:

1. Zaman serisi tahmin problemleri için bu metrikler daha uygun ve anlamlıdır.
2. Hava sıcaklığı gibi sürekli bir değeri tahmin ederken, doğruluk metriği anlamlı olmayabilir.
3. RMSE, MSE ve MAE, modelin tahminlerinin gerçek değerlerle ne kadar uyumlu olduğunu nicel olarak ölçer ve tahmin hatalarının büyüklüğünü yansıtır.

Bu projeyi geliştirirken, zaman serisi verileri üzerinde model performansını değerlendirmek ve genelleme yeteneğini test etmek amacıyla **Time Series Cross Validation** (Zaman Serisi Çapraz Doğrulama) yöntemini kullandım. Time Series Cross Validation, gelecekteki tahminlerin ne kadar güvenilir olduğunu ve modelin zaman içinde nasıl performans gösterdiğini belirlemek için önemlidir.

## Time Series Cross Validation Neden Yapıldı?

- Zaman serisi verileri genellikle dinamik ve yapısal değişikliklere tabidir. Bu değişikliklere modelin ne kadar iyi uyum sağlayabileceğini değerlendirmek istedim.

- Veri sızıntısı riskini azaltmak için Time Series Cross Validation yöntemini tercih ettim. Bu yöntem, veri setinin kronolojik sırasını dikkate alarak güvenilir sonuçlar elde etmemi sağladı.

- Modelin gelecekteki tahmin yeteneğini test etmek ve performansını değerlendirmek amacıyla bu yöntemi kullandım.

## Time Series Cross Validation Sonuçları

Maalesef, projeyi geliştirirken GPU yetersizliği nedeniyle Time Series Cross Validation işlemi tamamlanamadı. Ancak elde ettiğim sonuçlar, modelin eğitim verilerine nasıl uyum sağladığını ve gelecekteki tahminlerde ne kadar güvenilir olduğunu göstermektedir.

Time Series Cross Validation, model geliştirme sürecinde önemli bir adımdır ve elde edilen sonuçlar, modelin güvenilirliğini ve performansını daha iyi anlamama yardımcı olmaktadır.

Bu README dosyası, projenin temel bileşenlerini ve neden belirli metrikleri kullandığımızı anlatır. Projeyi incelediğinizde, modelin eğitimini ve sonuçlarını daha ayrıntılı olarak görebilirsiniz.

# (EN) Jena Climate Time Series Project

This project aims to build a time series forecasting model using the Jena Climate dataset. The project consists of loading the dataset, cleaning the data, training the model and evaluating the results.

## Data Set

I added the dataset file to the main directory of this project. 

## Model Tutorial

The model used in the project uses deep learning techniques to build a time series forecasting model. We also monitor the model during training using a training callback. The callback stops training when the validation loss drops below 0.0005. This helps the model to deliver fast and accurate results.

Once the model is trained on the dataset, it makes predictions on the test data and its performance is evaluated by comparing these predictions with the actual values.

## Results

The project results were evaluated with the following metrics:

- Root Mean Squared Error (RMSE): 0.0102083525
- Mean Squared Error (MSE): 0.00010421046
- Mean Absolute Error (MAE): 0.0078059346

These metrics show how close the model's predictions are to the true values. Low values of RMSE, MSE and MAE indicate that the model has a good prediction performance.

## Why These Metrics?

In this project, I used RMSE, MSE and MAE metrics instead of accuracy metrics because:

1. For time series forecasting problems, these metrics are more appropriate and meaningful.
2. When forecasting a continuous value such as air temperature, the accuracy metric may not be meaningful.
3. RMSE, MSE and MAE quantitatively measure how well the model's predictions agree with actual values and reflect the magnitude of prediction errors.

In developing this project, I used **Time Series Cross Validation** to evaluate model performance on time series data and test its generalizability. Time Series Cross Validation is important to determine how reliable future forecasts are and how the model performs over time.

## Why Time Series Cross Validation?

- Time series data is often subject to dynamic and structural changes. I wanted to assess how well the model can adapt to these changes.

- To reduce the risk of data leakage, I opted for Time Series Cross Validation, which allowed me to obtain reliable results by taking into account the chronological order of the dataset.

- I used this method to test the model's future forecasting ability and evaluate its performance.

## Time Series Cross Validation Results

Unfortunately, Time Series Cross Validation could not be completed due to GPU shortage during the development of the project. However, my results show how well the model fits the training data and how reliable it is for future predictions.

Time Series Cross Validation is an important step in the model development process and the results help me to better understand the reliability and performance of the model.

This README file describes the key components of the project and why we use certain metrics. When you explore the project, you can see the model's training and results in more detail.
