# 2022P
互概筆記
## week01
### 1. 建置環境

    桌面 > 葉正聖老師上課軟體 > Processing > 7.zip解壓縮

### 2. 畫正方
    (1) 靜態模式(剛開始)
            void setup()
            {
                size(500,500);
            }

    (2) 動態模式(持續)
    ```p
            void draw()
            {
                  background(#3384D3);
                  fill(0);     //顏色
                  rect(100,100,100,150);　　//長方形（X位置 , Y位置 , 長 , 寬）
                  rect(mouseX,mouseY,100,150);
            }
      ```





### 3. 變成網頁形式

#### 3-1設定 p5.js 
    (1) 點右上角 Java > Manage...
    (2) 下載 p5 .... 


#### 3-2 P語言->js
            （https://pde2js.herokuapp.com/）


#### 4. 滑鼠畫圖

            void setup()　　///只執行一次
            {   
                size(500,500);   ///畫面大小
                background(#FFFFF2);   ///背景顏色
                stroke(255,0,0);   ///畫筆顏色
            }
            void draw()　　///每秒60次
            {   
                if(mousePressed)
                {
                    line(mouseX , mouseY , pmouseX , pmouseY );   ///畫線
                }
            }
            void keyPressed()
            {
                if (key == '1' ) stroke(#4682B4);
                if (key == '2' ) stroke(#6A5ACD);
                if (key == '3' ) stroke(#E6005C);
            }
