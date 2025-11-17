


---

##  Dataset

The models were trained on the **Figaro-1k** dataset, a standard benchmark for this task.

* **Training Data:** 840 images
* **Testing Data:** 210 images

---

##  Training

* **Epochs:** 50
* **Loss Function:** 
    *
    * **Dice Loss** for ground truth mask \(A\) and predicted mask \(B\):



\[
\text{Dice Loss}(A, B) = 1 - \frac{2 \cdot |A \cap B|}{|A| + |B|}
\]





---

##  Performance

After 50 epochs, the model achieved the following results on the 210-image Figaro-1k test set:

| Model              | IoU (Intersection over Union) | Dice Coefficient |
| :----------------- | :---------------------------: | :--------------: |
| PSPNet (ResNet‑50) | 0.89                          | 0.94             |
| PSPNet (ResNet‑152)| 0.89                          | 0.94             |
| Res U-Net          | 0.86                          | 0.93             |



## Near future work
  At the current stage, we recognize that the models performance leaves to desire : while the predicted masks have the coarse form right the details near the hair boundary need improvement.

 * We're starting the training of these models on **CelebA-Hair dataset** . The primary issue is that colab crashes at time when training is launched and with the training dataset alone being 20k+ images heavy even the first epoch doesn't conclude ( 13% takes 40 min ) and colab crashes.
 * We're also considering using descriptors featured engineered from dataset as input to our models ( HOG , LBP ) to see if that improves the models performance
 * Try other models .
