# Exploring-the-connection-between-policies-and-patents-using-topic-modeling

## Information loss problem
Considering that the policy and patent data may have certain information loss after LLM processing, I chose to use BERTScore and SBERT Similarity to measure.
| | BERTScore Mean | BERTScore Variance | SBERT Similarity Mean | SBERT Similarity Variance |
|----|----|----|----|----|
| policy | 0.8762 | 0.0003 | 0.8447 | 0.0030 |
| patent | 0.8744 | 0.0004 | 0.8186 | 0.0033 |

According to these two data, we can see that the topic consistency and semantic similarity before and after adding LLM are high, and the variance is small, indicating that the processing results are stable and the information retention is high. The conciseness of the text has been improved.

## Experimental results

### Similarity analysis
Similarity between overall policy and patent subject matter: **0.8676723**

Pearson correlation between policy and patent topics: **0.8135**

1-year lagged correlation: **0.8467**

2-year lagged correlation: **0.1702**

This indicates that policy topics and patent topics have a strong correlation in the same period, but cannot prove causality. 1-year lagging correlation: 0.8467 indicates that the impact of policies on patent topics may have a 1-year lag effect, that is, within about 1 year after the policy is issued, the changes in the topics in the patent field are highly consistent with the policy. This value is higher than the direct correlation (0.8135), indicating that the impact of the policy may be more obvious in the next year than in the current year. 2-year lagging correlation: 0.1702 The correlation has dropped significantly, indicating that the impact of the policy has basically weakened after 2 years, or the development of patent technology is affected by other factors.

### Visual Analytics
Topic similarity heat map

- Similarity trend: The policies of 2020-2025 have a high similarity to the patents of 2022-2024 (around 0.6). The similarity of policies after 2026 began to decline, indicating that the impact of policies on patents gradually weakened, and new policies may be needed to promote technological innovation.
- Lag effect: The patents in 2023 have the highest similarity with the policies in 2023 (0.67), indicating that the direct impact of the policy may be most significant after 1 year. The similarity of patents in 2024 has declined, which is consistent with the previous lag correlation analysis (the 1-year lag has the largest impact, and the 2-year lag has a weaker impact).
- Future trend forecast (after 2026): The similarity began to decline significantly in 2026 (down to around 0.3). The similarity in 2030 is only around 0.2, indicating that the impact of the current policy may not last too long, and new policy support is recommended.

Cluster analysis


Through UMAP dimensionality reduction + HDBSCAN clustering, policies and patent topics are divided into multiple clusters. The Silhouette Score is 0.5523, indicating that the topic division is relatively clear; the Davies-Bouldin Index is 0.5565, which further verifies the clustering quality. It can be seen that there is a strong clustering effect in the direction of patent innovation affected by policies, that is, policies may mainly affect certain technical fields rather than widely affecting all patent innovations.

### Future Patent Theme Forecast
| | Predicted value |
|----|----|
| 2025 | 95915|
| 2026 | 127387 |
| 2027| 117016 |

Forecast trend: A new high will be reached in 2026, and then a slight decline will occur in 2027. This may be affected by factors such as policy changes and market demand. It is also necessary to consider that the policy data for 25-26 is not complete.

Predicted patent themes for 2025 (top 10):
  1. clean, complementary, regulation, plc, sources
  2. marine, affordable, ecosystems, ocean, regulations
  3. inspection, routing, beidou, halogen, transport
  4. new, mathematical, assessing, consumption, objective
  5. net, zero, planning, constraint, pet
  6. conditioner, recommended, habits, information, programs
  7. member, conducting, sheet, protrusions, sites
  8. clean, accounting, emission, new, plc
  9. headspace, stator, windheat, vessel, traffic
  10. pttio, maritime, ccs, window, submodels
