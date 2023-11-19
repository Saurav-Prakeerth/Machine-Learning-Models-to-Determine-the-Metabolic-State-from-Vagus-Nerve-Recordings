# Machine-Learning-Models-to-Determine-the-Metabolic-State-from-Vagus-Nerve-Recordings

## Abstract
Metabolic disorders such as type-2 diabetes are approaching epidemic levels across the globe in terms of impact and cost to individuals and wider healthcare systems. The vagus nerve has become a major target for the diagnosis and treatment of several metabolic disorders, as it innervates organs such as the spleen, digestive tract, liver and kidneys, with both afferent and efferent functions. Rapid advances in the past decade in neuro-sensing and neuro-modulation have opened up new avenues for early diagnosis and closed-loop neuro-modulatory therapy for diabetes and other similar conditions. However, the widespread adoption of these devices has been largely limited by the significant gaps in our understanding of vagus nerve signalling and the underlying coding schemes of its various signal components.

This investigation aims to apply cutting-edge signal processing frameworks, feature extraction schemes and novel machine learning (ML) classifiers to approach this problem from a new perspective by introducing minimal assumptions about the function of structural elements of the waveform. In particular, this study focuses on developing binary and ternary classification pipelines to predict metabolic states from the vagus nerve measurements from rats. In the proposed system, once data is collected from the specimens, it is passed through the classification pipeline which consists of 3 stages, namely, preprocessing, feature extraction, and classification. Different combinations of options for these pipeline stages are explored and evaluated in terms of accuracy, reliability and efficiency.

Our analyses confirmed that hypoglycemic classification produces greater prediction accuracy than the ternary metabolic state classification, which matches the trend observed in previous literature (Masi et al., 2019). Moreover, in our preliminary investigation, the architectures based on ensembles of decision tree classifiers emerged as the superior model template in comparison to other models investigated, and were focused on for the remainder of the study. Notably, the Extra Trees classifier was the most performant base model across all the feature transforms and datasets tested. This model inherently mitigated the risk of overfitting and handled dataset class imbalance effectively. Moreover, it was characterised by a level of computational efficiency that surpassed other baseline decision tree ensembles and produced interpretable and visualisable predictions, which is crucial for diagnostic and therapeutic applications.

In previous studies, a subsection of the non-responder specimens was omitted in some trials to identify the potential effects of this segmentation on accuracy (Zanos et al., 2018). All other trials used the combined, unsegmented dataset. Optimising the Extra Trees model further with a hyperparameter optimisation strategy using Tree-structure Parzen Estimators produced three pipelines that consistently yielded AUC ROC scores surpassing 0.70 for both responder and non-responder classification.
The most computationally lightweight pipeline of the three used the responder dataset with the Catch22 feature transform. On the other hand, the most accurate combination was the unsegmented dataset paired with features extracted from VN spike rates. The third of the best-performing Extra Trees pipelines worked with features extracted from spike rates and amplitudes and produced the lowest variability. Finally, the effect of state-of-the-art resampling and batch effect elimination techniques were evaluated on these pipelines. These model augmentation methods failed to produce any statistically relevant improvements to the model performance.

Overall, this study presents a comprehensive analysis of the accuracy, reliability and efficiency trade-offs of a large variety of signal processing and classification schemes, highlighting optimal model design parameters for each configuration. The most performant model configurations identified approximately equal the bias and variance of the most advanced contemporary neural decoding systems while operating at a much lower computational overhead, approaching the problem from a new perspective. These new insights take us one step closer to practical implementations of closed-loop monitoring and neuro-modulation technologies. In the case of diabetes, these systems offer novel, unobtrusive treatment modes which do not require periodic finger-prick glucometer measurements and insulin injections, utilising VN stimulation instead. Furthermore, the explorations in this study could also form a foundation for decoding pipelines for neural monitoring applications in other domains.

The ```classifier_trials.ipynb``` notebook in this repository contains most of the classifiers trialled in this project.

