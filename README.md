# LCD（ACM1602NI-FLW-FBW)


## 環境

- Raspberry Pi 3(Raspbeian Jessie)

## Functions
### 基本関数
- `int setI2c(int *fd);`  

  RaspberyPiに置いてI2Cの初期設定をする関数  
  ###### 引数
  - ファイルディスクリプタを代入するint型変数のアドレス
- `void lcdSet(int fd);`  

  setI2cで設定されたファイルディスクリプタのLCDの初期設定をする関数
- `void setCursor(int fd, int n);`  

  LCDのカーソル（文字を表示し始める位置）を設定する関数
- `void clearDisplay(int fd);`  

  LCDのディスプレイを綺麗にする（初期化）する関数
- `void lcdWrite(int fd, unsigned char rs, unsigned char data);`  

  LCDにデータを書き込む（送る）関数
- `void lcdPrint(int fd, char *str, int row, int col);`  

  LCDに文字を表示させる関数

### 応用関数
- `void lcdPrint_flow(int fd, char *str, int row, double speed);`  

  LCDに文字を右から左に流れるように表示する関数
- `void lcdPrint_loop(int fd, char *str, int row, double speed);`  

  `void lcdPrint_flow`の見切れた文字がその瞬間に反対側から流れてくるようにした関数
- `void lcdPrint_rowp(int fd, char *str, double speed);`  

  文字がLCD内をぐるぐる回る関数

### その他関数
- `void strReverse(char *sstr, char *str);`

  文字列を反転させる関数
