LightGCN Recommendation
Graph Convolutional Networks (GCNs) are effective for collaborative filtering, but their success is not fully understood. 
LightGCN, a simplified model, retains only the essential neighborhood aggregation component, improving performance significantly (about 16.0% over NGCF). This model simplifies implementation and training while addressing challenges in GCNs. Collaborative filtering focuses on predicting user interactions with products using latent features. Incorporating user interaction history enhances embedding quality and recommendation accuracy.

1. The Retailrocket recommender system dataset consists of four CSV files:
Link: https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset
  a. events.csv: Contains logs of all user interactions (behavior) with items over a period of 4.5 months. The dataset includes 2,756,101 events, comprising 2,664,312 views, 69,332 add-to-carts, and 22,457 transactions by 1,407,580 unique visitors.
  b. itemproperties.csv: Contains a set of properties for each item—such as price, stock status, category, brand, etc. Each property can change over time, so the file includes a timestamp for each value. This file will be divided into two sub-files.
2. Implemented in 2 ways:
   a. LightGCN "pure"
   b. Feauture-enhanced LightGCN
3. Conclusion
   <img width="422" height="280" alt="image" src="https://github.com/user-attachments/assets/b15ec6b2-02e7-4182-ae20-f93916a84e45" />

  This is a comparison chart of the performance of the pure LightGCN model and the LightGCN model combined with categories. It is clearly noticeable that the results of the category-enhanced model are significantly better than those of the standard LightGCN. The category-enhanced LightGCN model achieves a $HR@20$ that is 2.6 times better than LightGCN, and an $NDCG@20$ that is twice as good. This demonstrates that incorporating categories has helped the model learn better the latent relationships among items of the same type. The quality of recommendations has improved, despite the presence of cold-start issues and sparse data.

LightGCN is a simple and easy-to-implement method that leverages the core relationships between users and items by omitting feature transformation and nonlinear activation to make product predictions for users. With the RetailRocket dataset, which is sparse and exhibits cold-start phenomena, the pure LightGCN model achieves a relatively decent result of 0.0451. Incorporating category embeddings into LightGCN is a straightforward hybrid approach that significantly enhances performance, effectively addressing cold-start issues and high sparsity.

ref: LightGCN: Simplifying and Powering Graph Convolution Network for Recommendation - Xiangnan He, Kuan Deng, Xiang Wang, Yan Li, Yongdong Zhang, Meng Wang∗
