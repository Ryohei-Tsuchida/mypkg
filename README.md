# mypkg
[![test](https://github.com/Ryohei-Tsuchida/mypkg/actions/workflows/prime.yml/badge.svg)](https://github.com/Ryohei-Tsuchida/mypkg/actions/workflows/prime.yml)

ROS2のパッケージ

## リポジトリ内のノード,ファイル一覧

### randam_number.py
* パブリッシャを持つノード. 1~100のランダムな整数10個を`/random_numbers`を通じて送信する.
   * トピックに流れるメッセージの型は32ビットの符号付き整数の配列.

### prime_ans.py
* サブスクライバを持つノード. トピック`/random_numbers`から1~100のランダムな整数10個を受信し,素数を選ぶ問題を出力し,その後30秒後に答えを出力する.

### randam_number_ans.py
* randam_number.pyとprime_ans.pyを同時に起動する.

## 実行手順
### randam_number.pyとprime_ans.py
* `ros2 run`実行方法
```bash
端末1$ ros2 run mypkg prime_ans
端末2$ ros2 run mypkg randam_number
```
実行後, 下記のような問題が出力される.実行後すぐに問題が出力されない場合もあり,その場合30秒後に問題が出力される.
```bash
[INFO] [1703922289.513912013] [random_ans]: Select a prime number from the following list:
[INFO] [1703922289.514429083] [random_ans]: [74, 79, 9, 22, 71, 43, 53, 17, 85, 93]
```
問題出力30秒後に,下記ような答えが出力される.終了は`Ctrl+C`をする.問題から素数がどれかを考えよう.
```bash
[INFO] [1703922318.981318353] [random_ans]: Time up! The answer is:
[INFO] [1703922318.981896856] [random_ans]: [79, 71, 43, 53, 17]
```

## 必要なソフトウェア
* Python

## テスト環境
* Ubuntu 20.04
* ROS2 foxy

## 著作権・ライセンス
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます．
* このパッケージのコードの一部は，下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
   * [ryuichiueda/my_slides/robosys_2022/lesson8](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson8.html#/)
   * [ryuichiueda/my_slides/robosys_2022/lesson9](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson9.html#/)
   * [ryuichiueda/my_slides/robosys_2022/lesson10](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson10.html#/)
   * [ryuichiueda/my_slides/robosys_2022/lesson11](https://ryuichiueda.github.io/my_slides/robosys_2022/lesson11.html#/)  
* © 2023 Ryohei Tsuchida
