## 深度學習(Deep Learning)

引入相關套件  
numpy  
pandas  
sklearn  
keras  
tensorflow  
  
完成後做前置處理，調整路徑名稱，將各個資料夾裡面的圖片取出後assign_label，  
將flowers資料夾下的所有圖片的label都叫flower_type  
這裡有使用cv2.resize將圖片縮放成IMG_SIZE大小設定為150  
  
而後使用plt套件來show一些圖片或數據，plt專門處理實驗上的數據折線圖或者圖片狀況  
  
在前置處理中，X是所有圖片的資料，每個圖片有150 x 150的像素，  
每個像素由3個數字表示RGB，值域為0~255，  
因此X是一個[總訓練圖片數量x150x150x3]的陣列，  
而Z就是一個長度為[總訓練圖片數量]的陣列，  
兩個陣列的index代表這張圖片(X[i])對應的答案為何(Z[i])  

Y這邊將Z變成One hot encoding，  
如果有五種類別依序是Daisy、Sunflower、Tulip、Dandelion、Rose，  
而今天Z[3]的值(即X[3]的答案)為Tulip，  
那麼原本Z[3] = 'Tulip'就轉變成Y[3] = [0,0,1,0,0]，  
也就是說是哪個種類為1，不是的則是0。  
X=X/255 因RGB值域為0 to 255要標準化為0 to 1。  
  
並將train跟test切割，並設定亂樹種子，建立CNN模型後開始訓練。  
顯示出折線圖結果，並算出性能指標。  

