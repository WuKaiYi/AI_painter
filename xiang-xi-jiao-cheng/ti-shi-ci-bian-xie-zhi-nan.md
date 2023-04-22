---
description: Guide to Writing Prompts
---

# 提示词编写指南

## 機畫師 基於 Stable Diffusion 進行開發，因此大部分編寫規則與Stable Diffusion相同

## Prompt等同於提示詞，是提示詞跟專業的表達，通常用於與各種AI應用溝通

### Ai繪圖通用prompt關鍵字規則

在AI繪圖中，正向prompt包括masterpiece, best quality等，可以用來描述畫質和畫面。反向prompt則包括nsfw（not safe for work）、lowres、bad anatomy等，可以根據畫面情況選擇不想出現的畫面。

**prompt權重：**越靠前的prompt權重越大。例如，若將景色prompt放在前面，則人物會相對較小；反之，人物會變大或呈現半身狀態。

**圖片大小對Prompt效果的影響：**圖片越大，則需要更多的Prompt，否則Prompt可能會相互污染。

**prompt權重調整方法：**使用括號()可增加括號中prompt在畫面中的權重x1.1，\[] 可減小prompt權重x0.91。

### Prompt格式優化

Prompt 優化步驟5步驟

1.  **步驟1. 簡易換行用3段式表達**

    掌握核心概念，並用分段進行說明。
2.  **步驟2. prompt第一段填上畫質和畫風關鍵字**

    畫質和畫風，例如photo、painting、oil painting。
3.  **步驟3. 第2段強調畫面主體與細節**

    主體細節概括人、事、物、景等畫面核心內容，例如：人物主要特徵、主要動作、物體主要特徵、主景或景色大框架。畫面細節例如：人數。
4.  **步驟4. 第3段補充畫面場景細節（或人物細節）**

    常見放在這段的說明是 highly detailed clothes, green engravings on clothes, embarrassed laughing, the overall tone of the image is happy.
5.  **步驟5. 重複嘗試與優化**

    不同模型（ckpt）對 Prompt 的敏感程度不同，一套完善的 prompt 在不同的模型中，表達效果會有差異。每個模型都有自己的特色，需根據模型特色，慢慢調試 prompt 組合。

### prompt 範例

製作出好的prompt必須從問一系列問題開始：

1. 您想要照片還是畫作？ **=>畫作**
2. 主題是什麼？人物？動物還是風景？ **=>貓**
3. 您想添加哪些細節？\
   特殊燈光。柔和、環境、環形燈、霓虹 **=>自然光**\
   環境。室內、室外、水下、太空中 **=>在天空中**\
   色彩方案。鮮豔、黑暗、柔和色調 **=>使用明亮的顏色**
4. 畫面風格？3D渲染、吉卜力工作室、電影海報 **=> 3D渲染**

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-1-1024x363.png.webp" alt=""><figcaption></figcaption></figure>

得到以下兩個結果，一個是用逗點隔開的關鍵字，另外是組合成一句話：

* Painting, cat, wearing a suit, natural light, in the sky, using bright colors, 3D render
* A 3D rendered painting of a cat wearing a suit, in the sky, with natural light and bright colors

左邊是呈現一副畫，畫中有prompt的描述；右邊是一張畫作風格的圖，有prompt指定元素。明顯右邊符合一開始的設定。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00000-1072759536.png.webp" alt=""><figcaption><p>一幅以3D渲染技術創作的畫作，描繪一隻穿著西裝的貓，在天空中，自然光照射下，色彩鮮艷（A 3D rendered painting of a cat wearing a suit, in the sky, with natural light and bright colors）</p></figcaption></figure>

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00001-257563771.png.webp" alt=""><figcaption><p>畫作、貓、穿著西裝、自然光、在天空中、使用鮮艷顏色、3D渲染<br>（Painting, cat, wearing a suit, natural light, in the sky, using bright colors, 3D render）</p></figcaption></figure>

圖片輸出的順序和呈現方式，與精準用關鍵字描述需求都一樣重要。建議將概念明確列出，並用逗點分開，而不是試圖將其擠入一個簡單的句子中。

### Prompt 符號

機畫師 都提供了一些特殊的符號來幫助您更精確地控制圖像生成過程。以下是這些符號的使用方式：

“+” 和 “ AND ”：這兩個符號都用於連接短關鍵字，以表示您希望同時滿足這些條件。使用 “AND” 時，需要在兩端加上空格。例如『beach + sun glasses』 或 『beach AND sun glasses』。

“|”：這是循環繪製符號（融合符號），用於在多個 Prompt 之間創建循環繪製效果。例如『(green hair：1.1) | (black hair：1.4)”』，Ai 會根據這些權重在 green hair 和 black hair 之間循環繪製，你就能得到黑綠漸層的髮色啦。

括號：在 機畫師 中，使用括號 () 可以增加括號內 prompt 的權重 x1.1，而使用方括號 \[] 可以減小 prompt 的權重 x0.91。這有助於在生成圖像時更精確地控制各個元素的重要性。

使用這些符號和權重可以讓您更好地控制 Stable Diffusion 的生成。

### Prompt解釋修飾詞與實際效果

修飾詞是可以改變圖像風格、格式或角度的詞語。有一些經過驗證能夠提高圖像質量的神奇詞語或短語。

在本節中，我們將討論您可以在prompt中使用的不同類型的修飾詞。

#### 攝影修飾詞

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00016-1219200005.png.webp" alt=""><figcaption><p>prompt關鍵字 Polaroid 拍立德</p></figcaption></figure>

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00049-741221465.png.webp" alt=""><figcaption><p>prompt關鍵字 Tilt-shift 移軸</p></figcaption></figure>

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00084-741221466.png.webp" alt=""><figcaption><p>prompt關鍵字 Portrait 肖像</p></figcaption></figure>

#### 風格修飾詞

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-3-1024x343.png.webp" alt=""><figcaption></figcaption></figure>

#### 鏡頭修飾詞

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-6-1024x369.png.webp" alt=""><figcaption></figcaption></figure>

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-2-1024x379.png.webp" alt=""><figcaption></figcaption></figure>

#### 藝術修飾詞

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-5-1024x352.png.webp" alt=""><figcaption></figcaption></figure>

#### 用 prompt 增強圖片細節

使用合適的  prompt 可以有效地幫助圖片增加細節，以下是一些範例：

**HDR**：HDR（高動態範圍）可以幫助圖像在明暗區域保留更多的細節，提高圖像的對比度和色彩豐富度，使圖片看起來更生動、立體。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-7-1024x436.png.webp" alt=""><figcaption></figcaption></figure>

**Highly detailed**：這個提示將引導 AI 在圖像中呈現更多細緻的細節，例如紋理、陰影和光線等。這將使圖像更為真實，增強其視覺效果。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-4-1024x356.png.webp" alt=""><figcaption></figcaption></figure>

**Studio lighting**：透過模擬演播室燈光效果，可以為圖像添加一些漂亮的紋理，使其更具吸引力。此外，適當的光線和陰影可以突顯圖像中的細節，使其更具立體感。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image-9-1024x334.png.webp" alt=""><figcaption></figcaption></figure>

選擇合適的 Stable Diffusion prompt 可以根據需求改善圖

| **提高圖像質量的提示**        | **用途**                                       |
| -------------------- | -------------------------------------------- |
| HDR, UHD, 64K        | (HDR、UHD、4K、8K 和 64K) 這樣的質量詞可以帶來巨大的差異提升照片的質量 |
| Highly detailed      | 畫出更多詳細的細節                                    |
| Studio lighting      | 添加演播室的燈光，可以為圖像添加一些漂亮的紋理                      |
| Professional         | 加入該詞可以大大改善圖像的色彩對比和細節                         |
| Vivid Colors         | 給圖片添加鮮豔的色彩，可以為你的圖像增添活力                       |
| Bokeh                | 虛化模糊了背景，突出了主體，像 iPhone 的人像模式                 |
| High resolution scan | 讓你的照片具有老照片的樣子賦予年代感                           |
| Sketch               | 素描                                           |
| Painting             | 繪畫                                           |

### Prompt參數教學

#### 參數：解析度 – 預設512×512

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/image.png.webp" alt="Stable Diffusion 參數 解析度"><figcaption></figcaption></figure>

這個參數非常直覺。您可以選擇生成圖像的寬度和高度。但重要的是要知道，該模型是在 512×512 的圖像上進行訓練的，一般來說，這些尺寸提供了最佳的質量和構圖，因此建議作為初學者時，保持使用這些尺寸。

#### 參數：CFG – 預設7 在機畫師中為 文字指導

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/%E6%88%AA%E5%9C%96-2023-03-26-%E4%B8%8A%E5%8D%8811.18.35-1024x81.jpg.webp" alt="Stable Diffusion參數 CFG"><figcaption></figcaption></figure>

您可以將此參數視為「創造力與prompt」的比例。較低的數字給AI更多的自由來展現創意，而較高的數字則迫使它嚴格遵循prompt。

* CFG 2 – 6：具有創意，但可能不遵循prompt；做圖喪失靈感時可以考慮使用。
* CFG 7 – 10：對於大多數prompt來說推薦使用。在創意和引導生成之間取得良好平衡。 
* CFG 10 – 15：當您確信您的prompt足夠好/具體時。 
* CFG 16 – 20：一般不推薦使用，除非prompt詳細描述得很好；可能影響整體性和質量。

#### 參數：Sampling Steps 採樣步驟 – 預設為20 機畫師 中 為步驟

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/%E6%88%AA%E5%9C%96-2023-03-26-%E4%B8%8A%E5%8D%8811.22.43.jpg.webp" alt="Sampling Steps 採樣步驟"><figcaption></figcaption></figure>

Stable Diffusion通過從充滿噪聲的畫布開始，逐步將其去噪，以達到最終輸出。此參數控制去噪步驟的數量。通常情況下，步驟越高效果越好，但是有一定的程度上限，超過也沒用。對於初學者，建議保持預設值。

#### 參數：Seed 種子 – 預設為隨機

種子是一個控制初始噪聲的數字。當所有參數固定時，種子是每次生成不同圖像的原因。在大多數Stable Diffusion的實現中，預設情況下，每次生成圖像時，種子會自動更改。如果您保持prompt、種子和所有其他參數不變，則可以得到相近、甚至幾乎相同的結果。

有時候對於修改prompt來達到做圖效果，選一樣種子可能是更適合的做法。因此，嘗試保存一個好的種子，並稍微調整prompt以獲得理想內容，同時保持相同構圖。這也可以用來測試不同修飾詞的效果。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/%E6%88%AA%E5%9C%96-2023-03-27-%E4%B8%8A%E5%8D%888.22.52-1024x289.jpg.webp" alt="Stable Diffusion 參數 Seed 種子"><figcaption></figcaption></figure>

seed參數在使用 img2img圖改圖的功能時尤其好用，可參考 [**Stable Diffusion img2img 教學**](https://gooptions.cc/stable-diffusion-img2img-%E6%95%99%E5%AD%B8/)**，圖改圖換臉、換服裝、換背景或風格＋以圖繪圖實測案例。**

#### 參數：Sampling method 取樣方法

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/%E6%88%AA%E5%9C%96-2023-03-26-%E4%B8%8A%E5%8D%8811.59.22.jpg.webp" alt="Stable Diffusion 參數 Sampling method 取樣方法"><figcaption></figcaption></figure>

取樣是在生成過程中對圖像進行去噪的方法，由於它們在計算圖像生成過程中的下一步方面有所不同，因此需要不同的時間和不同的步驟數來達到可用圖像。我建議初學者使用DDIM，因為它速度快，通常只需10個步驟就可以生成好的圖像，使得實驗和改進變得容易且快速。產出擬真人物圖片時，我喜歡用DPM++ 2S a。

### Stable Diffusion Prompt重要技巧

關鍵字出現順序與關鍵字本身一樣重要，例如下圖，用一樣的seed和prompt，沒在開頭先說『放大鏡』的話，放大鏡並不會出現在圖片中。

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/03/00321-6.png.webp" alt=""><figcaption></figcaption></figure>

Sherlock Holmes held a magnifier 福爾摩斯握著一個放大鏡

<figure><img src="https://gooptions.cc/wp-content/uploads/2023/04/00316-2.png.webp" alt=""><figcaption></figcaption></figure>

a magnifier held by Sherlock Holmes 一個放大鏡被福爾摩斯握著

###

引用自[https://gooptions.cc/stable-diffusion-prompt%E6%95%99%E5%AD%B8/](https://gooptions.cc/stable-diffusion-prompt%E6%95%99%E5%AD%B8/)
