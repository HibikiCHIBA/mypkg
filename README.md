# mypkg
![test](https://github.com/HibikiCHIBA/mypkg/actions/workflows/test.yml/badge.svg)

- 本リポジトリは ROS 2 パッケージである. 
- 機能として, talker ノードがカウントアップした数値を, トピックを通して Int16 型のメッセージとして listener ノードが受信し, その数値を出力する. 

# Node & Topic
- talker と listener の2つのノードで構成されている. 
- talker はカウントアップした数値を, countup というトピックを通して Int16 型のメッセージで送信する. 
- listener は countup トピックから Int16 型のメッセージを受信して出力する. 

# Demo
実行例を示す. 実行には端末が2つ必要で, talker 側を端末A, listener 側を端末Bとする. 
- 端末A（ talker ）
```
$ ros2 run mypkg talker
```
- 端末B（ listener ）
```
$ ros2 run mypkg listener
[INFO] [1704209869.569326572] [listener]: Listen: 0
[INFO] [1704209870.063658511] [listener]: Listen: 1
[INFO] [1704209870.565507849] [listener]: Listen: 2
[INFO] [1704209871.065470237] [listener]: Listen: 3
[INFO] [1704209871.565540734] [listener]: Listen: 4
[INFO] [1704209872.063807467] [listener]: Listen: 5
[INFO] [1704209872.565407613] [listener]: Listen: 6
[INFO] [1704209873.065392425] [listener]: Listen: 7
[INFO] [1704209873.565437927] [listener]: Listen: 8
[INFO] [1704209874.065499671] [listener]: Listen: 9
[INFO] [1704209874.565479448] [listener]: Listen: 10
(以下略)
```

# Launch
- launch ファイルの実行例を示す. talk_listen.launch.py を実行することで起動. 複数のノードを起動することなく, 単独起動で複数ノードを起動することができる. 
```
$ ros2 launch mypkg talk_listen.launch.py
[INFO] [launch]: All log files can be found below /home/hibiki/.ros/log/2024-01-03-00-40-12-205610-Hibiki-PC-29830
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [29832]
[INFO] [listener-2]: process started with pid [29834]
[listener-2] [INFO] [1704210012.981471202] [listener]: Listen: 0
[listener-2] [INFO] [1704210013.459137225] [listener]: Listen: 1
[listener-2] [INFO] [1704210013.959126749] [listener]: Listen: 2
[listener-2] [INFO] [1704210014.459072818] [listener]: Listen: 3
[listener-2] [INFO] [1704210014.959110450] [listener]: Listen: 4
[listener-2] [INFO] [1704210015.459130116] [listener]: Listen: 5
[listener-2] [INFO] [1704210015.959106126] [listener]: Listen: 6
[listener-2] [INFO] [1704210016.459100709] [listener]: Listen: 7
[listener-2] [INFO] [1704210016.959095922] [listener]: Listen: 8
[listener-2] [INFO] [1704210017.459052608] [listener]: Listen: 9
[listener-2] [INFO] [1704210017.959036774] [listener]: Listen: 10
(以下略)
```

# Environment
* Ubuntu 20.04.4 LTS
  * ROS 2 Foxy
* python 3.8.10
## Testing Environment
* Ubuntu 22.04 LTS
  * ROS 2 Humble

# License
* このソフトウェアパッケージは, [3条項BSDライセンス](https://opensource.org/license/bsd-3-clause/)の下, 再配布および使用が許可されています. 
* このパッケージのコードは，上田隆一先生の[スライド](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
* © 2023 Hibiki Chiba
