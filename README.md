# Network Intrusion Detection with KDD Cup 1999

Project completed as part of the **SY09 - Data Analysis and Data Mining** course at Université de Technologie de Compiègne (UTC).

## Authors

- Jiacheng Zhou  
- Gaëtan Le Frioux  
- Lorys Hamadache  

## Objective

Build a network intrusion detection model using the **KDD Cup 1999** dataset, classifying connections as either normal or attacks.

## Dataset

- Source: [KDD Cup 1999 Data](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)
- 41 features, 5M+ samples
- Attacks grouped into 4 categories: `DoS`, `Probe`, `U2R`, `R2L` + `normal`

## Project Steps

1. **Data Preprocessing**
   - Removed duplicates
   - Normalized features
   - Resampled to balance class distribution

2. **Exploratory Analysis**
   - PCA visualization
   - Feature correlation analysis
   - Identified key discriminant features

3. **Tested Models**
   - `K-Nearest Neighbors (KNN)`
     - Strong performance (94% accuracy, 6% missed attacks with sampling)
   - `Naive Bayes` / `LDA`
     - Poor results due to violated assumptions
   - `Decision Trees / Random Forest`
     - Good at detecting `probe`, poor on `U2R` / `R2L`

4. **Combined Model (KNN + Random Forest)**
   - Best overall performance:  
     - **Global Accuracy: 94.27%**  
     - **Missed Attacks: 6.19%**

## Results Summary

| Model                | Accuracy | Missed Attacks |
|----------------------|----------|----------------|
| KNN (raw)            | 93.67%   | 15.88%         |
| KNN (resampled)      | 94.36%   | 9.86%          |
| Random Forest        | 92.50%   | 18.48%         |
| **KNN + RF (hybrid)** | **94.27%** | **6.19%**     |

## Conclusion

A hybrid model combining the strengths of each approach:
- KNN performs well but struggles with `probe` attacks
- Random Forest performs better on those  
➡️ Combined model significantly reduces missed attacks.

## Resources

- [Full Report (PDF)](./FinalReport.pdf)
- [Original Dataset](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)
- [Project Drive (code & preprocessed data)](https://drive.google.com/drive/folders/1T_X-T6xR1IJPhWZ5lR04Z8Io1rDK8Tdg?usp=sharing)
