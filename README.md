# Doctor_Bias

### Detect Implicit Gender Bias in Online Patient Reviews Using Machine Learning
Applied statistical modeling and NLP methods to analyze and extract quantitative data from textual content, to find whether the patient’s expectation and evaluation standards differ for male and female doctors


### Content
(Code: W2v_final_bias_detect 0516.ipynb)
- __Prepare data and clarify gender__
  - Import raw data and concatenate reviews
  - Predict gender using doctor's name
  - Predict gender using patient comments & Filter out other positions
  - Gender clarification & Mark
- __Pre-process via spaCy__
  - Punctuation removal & Lemmatization
  - Spellcheck and correction
- __Build model via word2vec__
- __Measure the gender bias__
  - Build sets of gender words & attribute words
  - Method 1: word analogies generated by model
    - Pattern 1: analogy 'he' + (adj.) - 'she' = ? | converse 'she' + (adj.) - 'he' = ?
    - Pattern 2: analogy 'his' + (noun) - 'her' = ? | converse 'her' + (noun) - 'his' = ?
  - Method 2: vector similarities calculated by model
    - Define & calculate set_diff() for each attribute word set
    - (1) One-sample T-test for each attribute word set
    - (2) Two-sample T-test for attribute word sets
  - Method 0: Word frequency in Male/Female reviews
    - Separate & Pre-process male/female datasets
    - Build models and count word frequency
    - Wilcoxon Signed-Rank Test on word frequencies in male/female models
    
### Conclusion
Gender Bias manifests in online physician reviews. Patients usually hold different standards for male/female doctors.
