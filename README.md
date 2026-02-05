# IJC437 Predicting Song Popularity Using Acoustic Features and Metadata
**1.1 Research aim**

The aim of this study is to identify which song-level characteristics are associated with popularity in the MusicOSet dataset and to evaluate whether acoustic features and metadata can predict whether a song is classified as popular

**Research questions**
- RQ1: What are the distributions and relationships of acoustic features and metadata variables (solo vs collaboration; explicit vs non-explicit) in the MusicOSet dataset?
- RQ2: To what extent can acoustic features distinguish popular from non-popular songs?
- RQ3: Does adding metadata improve the prediction of song popularity compared with using acoustic features alone?

**Models**
1. Model 1: is_pop ~ duration_ms + acousticness + danceability + energy + instrumentalness + liveness + loudness + speechiness + valence + tempo
2. Model 2: is_pop ~ song_type + explicit
3. Model 3: is_pop ~ duration_ms + acousticness + danceability + energy + instrumentalness + liveness + loudness + speechiness + valence + tempo + song_type + explicit

**Key findings**
1. Acoustic features have statistically significant but limited predictive value. Danceability and Valence were positively associated with popularity, while speechiness, acousticness, energy and instrumentalness were negatively associated. Overall fit of the Model 1 was low (Nagelkerke R² ≈ 0.02) and discrimination was close to chance (AUC ≈ 0.570).
2. Metadata provides weak signals and adds little on top of acoustics. Explicitness was consistently associated with lower odds of popularity, while collaboration was not a reliable predictor. Model 3 with combined acoustics and metadata only marginally improved performance (Nagelkerke R² ≈ 0.024).

**Limitations**
1. The MusicOSet dataset contains 10,228 songs (post-1985), which is small in comparison with the volume of music released in the real world. For context, there were close to 10.5 million songs released in 2024 alone. Therefore, 10,228 songs across 30 years do not feel like a representative enough data frame and limit how confidently results can represent the wider industry.
2. MusicOset contains songs that already have some level of chart presence and popularity. This makes the task more about distinguishing more vs less popular songs within an already relatively successful pool, rather than predicting popularity from a truly representative set.
3. Popularity measure is_pop is binary. Using a continuous measure such as streams on platforms or chart position would provide more information. The binary definition of popularity reduces variation and can make prediction harder because many songs with different success levels are treated as the same outcome.
4. The analysis focuses on acoustics and two metadata variables, but popularity is strongly shaped by factors like marketing, social media exposure, and artist fanbase. Which likely explains the limited performance of the models.

**Assumptions**
1. The dependent variable is_pop is an acceptable representation for popularity for the purpose of this coursework, even though it simplifies what success actually is.
2. The acoustic variables are measured consistently throughout the years by an algorithm and reflect the musical properties that they are intended to represent.
3. Songs from different years in the dataset are comparable enough that one model can be fitted across the whole 1985-2018 period. Relationships between features and popularity are stable.

**Future work**
1. Future work would greatly benefit from adding richer context predictors such as follower and listening count, chart history. These are directly linked to artist exposure and could substantially improve prediction
2. Train different models such as random forest to repeat the analysis.
3. Repeat modelling within genres to test whether acoustic features behave differently across different genres of music.
4. Use continuous popularity measures such as popularity scores and chart ranks as they carry more information than a binary label. Will allow us to analyse how much popularity changes rather that only popular vs not popular. 

In conclusion, this project shows that while acoustic features and simple metadata can detect small associations with song popularity, they provide limited predictive power on their own. The key finding is that modelling popularity requires more information beyond audio features.
