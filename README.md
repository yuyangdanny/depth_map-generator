# depth_map-generator:
</br> <li> 由於考慮到深度相機kinetic容易受到室外光照影響，而發生偵測不到較遠距離及室外的深度訊息。
</br>故使用了生成對抗網路來讓網路學習到轉換的方法，就可以單單利用一般的rgb鏡頭就可轉換出具有深度訊息的幀。
</br>可以降低硬體設備成本，亦可使室外的影響降低，以及使偵測距離更遠。
</br>
# method:
</br> <li> 利用GAN網路在kitti數據集上生成深度圖
</br>將我的預訓練checkpoint放在這:[pre-trained checkpoint](https://mega.nz/fm/Mo92Va5I "Title") 
</br>
# Discriminator:
</br> <li> 這次使用的與以往的判別器都是使用數值1與0來判定生成的圖像是否為真不同。
</br>而此方案的判別器是使生成的圖片去分割為小的區域，使判別器在判別時，可以一個區塊一個區塊的去判別。
</br>因此這次是使用matrix來作為判斷為真假的依據。
# 以下提供簡單的演示:
</br>這是生成器訓練5次的結果:![A](https://github.com/yuyangdanny/depth_map-generator/blob/master/image/traning5.PNG)
</br>這是生成器訓練14次的結果:![A](https://github.com/yuyangdanny/depth_map-generator/blob/master/image/traning14.PNG)
</br>這是對未訓練的raw data生成的結果:
</br>![A](https://github.com/yuyangdanny/depth_map-generator/blob/master/image/predict.PNG)
