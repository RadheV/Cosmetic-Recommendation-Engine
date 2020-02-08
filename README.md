# Cosmetic-Recommendation-Engine
*Mapping cosmetic items based on their ingredients similarities and giving content-based filtering recommendation*

When making a decision of trying a new skincare product on the market, there is always a hesitation on whether the product will aggravate the skin condition rather than improving. More often, the primary cause for the prior adverse skin reaction is particular ingredient(s) in a skincare product. Though we have the complete transparency to the list of ingredients in the labels of every product, we can't exactly pinpoint the exact ingredient - best option would be avoid using products are similar to previous product purchase that caused high distress to our skins. That brings me to build a simple cosmetic recommendation.

As a first step, I decided to do webscrapping on a very popular cosmetics website - Sephora. Since I would like to focus on only skin care items, I narrowed to just 6 categories — moisturizing cream, facial treatments, cleanser, facial mask, eye treatment, and sunscreen. The dataset has 1630 items in total. The dataset contains information on the brand, the price, the rank, skin types and the chemical components of each item.

The focus is to narrow down to the ingredients of products and get the similarities based on them.

After cleaning and pre-processing the dataset, I moved on to creating a document-term matrix (DTM). Here each cosmetic product will correspond to a document, and each chemical composition will correspond to a term to form a “cosmetic-ingredient” matrix.

The dimension of this matrix is 190 x 2710 which means there are 2710 features in our data. I used T-distributed Stochastic Neighbor Embedding (t-SNE)  to reduce the dimension of the dataset while keeping the similarities between the instances.

Lastly, let's move on to compare the similarity between each points. 

Take one particular product say **Daily Reviving Concentrate by KIEHL'S** as it previously caused you skin distress. You would want to avoid skin products that are of similar to it. 

![myItem](https://github.com/RadheV/Cosmetic-Recommendation-Engine/blob/master/images/image.png)

Sort the result in ascending order will give you a list of skincare products of have similar properties - recommendation for products that you should stay away.

![Sorting](https://github.com/RadheV/Cosmetic-Recommendation-Engine/blob/master/images/image_2.png)

Conversely, sort the result in descending order and it will recommend you a list of products that you could safely (with caution) try out.

