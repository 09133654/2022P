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
```p
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
```



### 3.撲克牌
```p
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
```



### 4.牌面中文字
```p
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
```


### 5.中文字變色
```p
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
```


### 6.隨機選牌
```p
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
```

## week03
### 0. Shuffle亂數洗牌(牌會出現一樣)複習
```p
void setup(){
  size(500,500);
  PFont font = createFont("標楷體", 35);
  textFont(font);
  myShuffle();
}
void myShuffle(){
  String [] flower = {"黑桃","紅心","方塊","梅花"};//陣列
  face1 = flower[int(random(4))] + int(random(13)+1);
  face2 = flower[int(random(4))] + int(random(13)+1);
  face3 = flower[int(random(4))] + int(random(13)+1);
  face4 = flower[int(random(4))] + int(random(13)+1);
}
void mousePressed(){
  myShuffle();
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

滑鼠點擊換牌(出現一樣)
```


### 1. 52張牌
```p
void setup(){
  size(700,700);
}

void draw(){
  background(#FFFFF2);
  for(int i=0; i<52; i++){ //迴圈
    int x = (i%10)*60; //除法10餘數, 個位數
    int y = int(i/10)*120; //十位數
    rect( x, y, 60,120 );
  }
}
```



### 2. 牌面出現中文
```p
void setup(){
  size(700,700);
  PFont font = createFont("標楷體", 10);
  textFont(font);
}
String [] faces = {
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K" };

void draw(){
  background(#FFFFF2);
  for(int i=0; i<52; i++){ //迴圈
    int x = (i%10)*60; //除法10餘數, 個位數
    int y = int(i/10)*120; //十位數
    fill(255); rect( x, y, 60,120 );
    fill(0); text( faces[i], x+25, y+80);//text("ID:"+i, x+25, y+80);
  }
}  
```

### 3. 優化卡面
```p
void setup(){
  size(800,600);
  PFont font = createFont("標楷體", 16);
  textFont(font);
}
String [] faces = {
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "紅心A","紅心2","紅心3","紅心4","紅心5","紅心6","紅心7","紅心8","紅心9","紅心10","紅心J","紅心Q","紅心K",
  "方塊A","方塊2","方塊3","方塊4","方塊5","方塊6","方塊7","方塊8","方塊9","方塊10","方塊J","方塊Q","方塊K",
  "梅花A","梅花2","梅花3","梅花4","梅花5","梅花6","梅花7","梅花8","梅花9","梅花10","梅花J","梅花Q","梅花K" };

void draw(){
  background(#FFFFF2);
  for(int i=0; i<52; i++){ //迴圈
    int x = (i%13)*60; //除法10餘數, 個位數
    int y = int(i/13)*120; //十位數
    fill(255); rect( x, y, 60,120 );
    if( faces[i].indexOf("紅心")==-1 && faces[i].indexOf("方塊")==-1) fill(0);
    else fill(255,0,0);
    text( faces[i], x+10, y+60);//text("ID:"+i, x+25, y+80);
  }
}  
```


### 4. 52張牌中點擊2張牌隨機換位
```p
void setup(){
  size(800,600);
  PFont font = createFont("標楷體", 16);
  textFont(font);
}
String [] faces = {
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "紅心A","紅心2","紅心3","紅心4","紅心5","紅心6","紅心7","紅心8","紅心9","紅心10","紅心J","紅心Q","紅心K",
  "方塊A","方塊2","方塊3","方塊4","方塊5","方塊6","方塊7","方塊8","方塊9","方塊10","方塊J","方塊Q","方塊K",
  "梅花A","梅花2","梅花3","梅花4","梅花5","梅花6","梅花7","梅花8","梅花9","梅花10","梅花J","梅花Q","梅花K" };

void draw(){
  background(#FFFFF2);
  for(int i=0; i<52; i++){ //迴圈
    int x = (i%13)*60; //除法10餘數, 個位數
    int y = int(i/13)*120; //十位數
    fill(255); rect( x, y, 60,120 );
    if( faces[i].indexOf("紅心")==-1 && faces[i].indexOf("方塊")==-1) fill(0);
    else fill(255,0,0);
    text( faces[i], x+10, y+60);//text("ID:"+i, x+25, y+80);
  }
}  
void mousePressed(){
  int a = int(random(52));
  int b = int(random(52));
  //目標: faces[a] vs. faces[b] 交換
  String temp = faces[a];
  faces[a] = faces[b];
  faces[b] = temp;
}  
```

### 5. 洗牌且4張牌不會一樣(0+4結合)
```p
void setup(){
  size(500,500);
  PFont font = createFont("標楷體", 35);
  textFont(font);
  myShuffle();
}
String [] faces = {
  "黑桃A","黑桃2","黑桃3","黑桃4","黑桃5","黑桃6","黑桃7","黑桃8","黑桃9","黑桃10","黑桃J","黑桃Q","黑桃K",
  "紅心A","紅心2","紅心3","紅心4","紅心5","紅心6","紅心7","紅心8","紅心9","紅心10","紅心J","紅心Q","紅心K",
  "方塊A","方塊2","方塊3","方塊4","方塊5","方塊6","方塊7","方塊8","方塊9","方塊10","方塊J","方塊Q","方塊K",
  "梅花A","梅花2","梅花3","梅花4","梅花5","梅花6","梅花7","梅花8","梅花9","梅花10","梅花J","梅花Q","梅花K" };
void myShuffle(){
 for(int k=0; k<10000; k++){
   int a = int(random(52));
    int b = int(random(52));
    //目標: faces[a] vs. faces[b] 交換
    String temp = faces[a];
    faces[a] = faces[b];
    faces[b] = temp;
  }
  face1 = faces[0];
  face2 = faces[1];
  face3 = faces[2];
  face4 = faces[3];
}
void mousePressed(){
  myShuffle();
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
```

## week04
## A 
### 1. 製作一顆球且恆動
```p
void setup(){

  size(500,500);

}

int x=250, y=250;//變數(位置)

void draw(){

  ellipse( x, y, 10, 10);//橢圓

  x = x + 1;

  y = y + -1;

}
```


### 2. 球碰到邊框會反彈
```p
void setup(){
  size(500,500);
}
float x=250, y=250;//變數(位置)精細
float vx = 1.0 , vy = -0.5;
void draw(){
  ellipse( x, y, 10, 10);//橢圓
  x = x + vx;
  y = y + vy;
  if( x > 500) vx = -vx;
  if( y < 0) vy = -vy;
  if( x < 0) vx = -vx;
}
```

### 3. 去掉球殘影且碰到底部長條會反彈
```p
void setup(){
  size(500,500);
}
float x=250, y=250;//變數(位置)精細
float vx = 1.0 , vy = -0.5;
void draw(){
  background(#FFFFF2);//背景,去除殘影
  int boardX = mouseX;
  rect(boardX, 470, 100, 20);//控制的板子
  ellipse( x, y, 10, 10);//橢圓
  x = x + vx;
  y = y + vy;
  if( x > 500) vx = -vx;
  if( y < 0) vy = -vy;
  if( x < 0) vx = -vx;
  if( y>470 && x>boardX && x<boardX+100 ) vy = -vy;
}
```

### 4.改變球碰板子後移速且控子板子長度
```p
void setup(){
  size(500,500);
}
float x=250, y=250;//變數(位置)精細
float vx = 2.0 , vy = -1.5;
float boardX, boardY=470, boardW=100, boardH=20;
void draw(){
  boardX = mouseX-boardW/2;
  background(#FFFFF2);//背景,去除殘影
  rect(boardX, boardY, boardW, boardH);//控制的板子
  ellipse( x, y, 10, 10);//橢圓
  x = x + vx;
  y = y + vy;
  if( x > 500) vx = -vx;
  if( y < 0) vy = -vy;
  if( x < 0) vx = -vx;
  if( (y>boardY && y<boardY+boardH) &&
      (x>boardX && x<boardX+boardW) ){
    vy = -vy;
    vx += (mouseX-pmouseX)/2;//mouse的移動速度
  }
  if(mousePressed && mouseButton==LEFT) boardW *= 1.01;//左鍵板子變長1%
  if(mousePressed && mouseButton==RIGHT) boardW *= 0.99;//右鍵板子縮短1%
}
```


## B
### 1.多個棋子
```p
void setup(){
  size(500,500);
}
void draw(){
  //用迴圈,來畫出很多棋
  for(int x=50; x<=450; x+=50){
    for(int y=50; y<=450; y+=50){
      ellipse(x, y, 50, 50);
    }
  }
}
```


### 2.陣列9X9個黑白棋
```p
void setup(){
  size(500,500);
}
int [][] go ={
  {0,0,0,1,0,0,0,0,1},
  {0,0,0,0,0,1,0,0,0},
  {0,1,0,0,0,0,0,0,1},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,1,0,0,1},
  {0,0,0,1,0,0,0,0,1},
  {0,1,0,0,0,0,1,0,0},
  {0,0,0,1,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
};//陣列 array 9X9
void draw(){ //用迴圈,來畫出很多棋
  for(int i=0; i<9; i++){//左手i 對應y座標
    for(int j=0; j<9; j++){//左手j 對應x座標
    if( go[i][j]==1) fill(0);
    else fill(255);
      ellipse(50+j*50, 50+i*50, 50, 50);
    }
  }
}
```

### 3.畫出棋盤並減少棋子數量
```p
void setup(){
  size(500,500);
}
int [][] go ={
  {0,0,0,1,0,0,0,0,1},
  {0,0,0,0,0,1,0,0,0},
  {0,1,0,0,0,0,0,2,1},
  {0,0,2,0,0,0,0,0,0},
  {0,0,0,2,0,1,0,0,1},
  {0,0,0,1,0,0,0,0,1},
  {0,1,0,0,0,0,1,0,0},
  {0,0,0,1,2,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
};//陣列 array 9X9
void draw(){ //用迴圈,來畫出很多棋
  background(246, 194, 108);//木頭色棋盤
  for(int i=1; i<=9; i++){ //用迴圈畫線
    line(50, 50*i, 450, 50*i);//湊出來的
    line(50*i, 50, 50*i, 450);//湊出來的
  }
  for(int i=0; i<9; i++){//左手i 對應y座標
    for(int j=0; j<9; j++){//左手j 對應x座標
      if( go[i][j]==1){
        fill(0);//1:黑棋
        ellipse(50+j*50, 50, 40, 40);
      }else if(go[i][j]==2){
        fill(255);//2:白棋
        ellipse(50+j*50, 50+i*50, 40, 40);
      }
    }
  }
}
```


### 4.下棋
```p
void setup(){
  size(500,500);
}
int [][] go ={
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0},
  {0,0,0,0,0,0,0,0,0}
};//陣列 array 9X9
int N=0;//目前有幾個棋子
void mousePressed(){
  int j = (mouseX-25)/50; //右手j, 對應x座標
  int i = (mouseY-25)/50; //左手i, 對應y座標
  go[i][j] = (N%2==0) ? 1 :2 ; ///if(N%2==0) 用1, 否則2
  N++;//多了一個棋子
}
void draw(){ //用迴圈,來畫出很多棋
  background(246, 194, 108);//木頭色棋盤
  for(int i=1; i<=9; i++){ //用迴圈畫線
    line(50, 50*i, 450, 50*i);//湊出來的
    line(50*i, 50, 50*i, 450);//湊出來的
  }
  for(int i=0; i<9; i++){//左手i 對應y座標
    for(int j=0; j<9; j++){//左手j 對應x座標
      if( go[i][j]==1){
        fill(0);//1:黑棋
        ellipse(50+j*50, 50+i*50, 40, 40);
      }else if(go[i][j]==2){
        fill(255);//2:白棋
        ellipse(50+j*50, 50+i*50, 40, 40);
      }
    }
  }
}
```
