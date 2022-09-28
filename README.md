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
            
            void draw()
            {
                  background(#3384D3);
                  fill(0);     //顏色
                  rect(100,100,100,150);　　//長方形（X位置 , Y位置 , 長 , 寬）
                  rect(mouseX,mouseY,100,150);
            }
             





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

## week02
### 1.一張卡
```p
//畫卡片

size(500,500);

rect(90,90, 170, 270, 20);

fill(#EFFA5B);

rect(100,100, 150, 250, 20);//弧度
```


### 2.多張卡

void setup(){

  size(500,500);

}

int W=25;

void draw(){

  drawCard(100,100);//使用函式

  drawCard(130,130);//使用函式

  drawCard(160,160);//使用函式

}

void drawCard(int x, int y){

  fill(255);

  rect(x-W/2,y-W/2, 150+W, 250+W, 20);//弧度

  fill(#EFFA5B);

  rect(x,y, 150, 250, 20);//弧度

}




### 3.撲克牌
void setup(){
  size(500,500);
}
int W=25;
void draw(){
  drawPokerCard(100,100, "S3");//使用函式
  drawPokerCard(130,150, "H6");//使用函式
  drawPokerCard(160,210, "D7");//使用函式
  drawPokerCard(190,260, "CQ");//使用函式
}/////牌面:Spade, Heart, Dimand, Club
void drawPokerCard(int x, int y, String face){
  fill(255);
  rect(x-W/2,y-W/2, 150+W, 250+W, 20);//弧度
  fill(#EFFA5B);
  rect(x,y, 150, 250, 20);//弧度
  fill(0);
  textSize(35);
  text(face, x, y+35);
}




### 4.牌面中文字
void setup(){

  size(500,500);

  PFont font = createFont("標楷體", 35);

  textFont(font);

}

int W=25;

void draw(){

  drawPokerCard(100,100, "黑桃3");//使用函式

  drawPokerCard(130,150, "紅心6");//使用函式

  drawPokerCard(160,210, "方塊7");//使用函式

  drawPokerCard(190,260, "梅花Q");//使用函式

}/////牌面:Spade, Heart, Dimand, Club

void drawPokerCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2, 150+W, 250+W, 20);//弧度

  fill(#EFFA5B);

  rect(x,y, 150, 250, 20);//弧度

  fill(0);

  textSize(35);

  text(face, x, y+35);

}



### 5.中文字變色
void setup(){

  size(500,500);

  PFont font = createFont("標楷體", 35);

  textFont(font);

}

int W=25;

void draw(){

  drawPokerCard(100,100, "黑桃3");//使用函式

  drawPokerCard(130,150, "紅心6");//使用函式

  drawPokerCard(160,210, "方塊7");//使用函式

  drawPokerCard(190,260, "梅花Q");//使用函式

}/////牌面:Spade, Heart, Dimand, Club

void drawPokerCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2, 150+W, 250+W, 20);//弧度

  fill(#EFFA5B);

  rect(x,y, 150, 250, 20);//弧度

  fill(0);//黑色的字

  if( face.indexOf("黑桃") == -1 && face.indexOf("梅花") == -1 ) fill(#FF0000);

  textSize(35);

  text(face, x, y+35);

}



### 6.隨機選牌
void setup(){

  size(500,500);

  PFont font = createFont("標楷體", 35);

  textFont(font);

  String [] flower = {"黑桃","紅心","方塊","梅花"};//陣列

  face1 = flower[int(random(4))] + int(random(13)+1);

  face2 = flower[int(random(4))] + int(random(13)+1);

  face3 = flower[int(random(4))] + int(random(13)+1);

  face4 = flower[int(random(4))] + int(random(13)+1);

  //取整數 0...12所以在加1

}

String face1, face2, face3, face4;

int W=25;

void draw(){

  drawPokerCard(100,100, face1);//使用函式

  drawPokerCard(130,150, face2);//使用函式

  drawPokerCard(160,210, face3);//使用函式

  drawPokerCard(190,260, face4);//使用函式

}/////牌面:Spade, Heart, Dimand, Club

void drawPokerCard(int x, int y, String face){

  fill(255);

  rect(x-W/2,y-W/2, 150+W, 250+W, 20);//弧度

  fill(#EFFA5B);

  rect(x,y, 150, 250, 20);//弧度

  fill(0);//黑色的字

  if( face.indexOf("黑桃") == -1 && face.indexOf("梅花") == -1 ) fill(#FF0000);

  textSize(35);

  text(face, x, y+35);

}

