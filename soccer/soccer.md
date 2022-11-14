## Hawk Eye Project
[Link](https://nihal111.github.io/hawk_eye/)

1. Download dataset
   [URL](https://nhoma.github.io/)
   Sports Field Localization Via Deep Structured Models

   <dataset>
   - image
   - ground-truth homography matrix

2. create dataset for query (with augumented)
    ```
    python warpandgen.py --dataset ...
    ```

3. Prepare pix2pix dataset
   concatenate rgb image + edge map image
   ```
   python warpImage.py
   ```

4. Train pix2pix
   ex) example test code for facades dataset
   ```
   cd pix2pix_code
   python train.py --dataroot ./datasets/facades --name facades_pix2pix --model pix2pix --direction BtoA
   ```

5. create query image for knn process
   ```
   pix2pix_query.sh
   ```

6. Compute KNN process
   ```
   python knn_fullprocess.py
   ``` 


## try
- player detection and pose estimation(youtube video)
- estimate person front direction
- team classification with deep learning
- calculate goal probability with player detection/team classification/person front direction/distance
- calculate and find the candidates of pass route for high goal probability(Dijikustra Method with xG cost)