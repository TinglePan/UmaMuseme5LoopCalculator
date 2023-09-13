# UmaMusume5LoopInheritanceCalculator
Calculate the best 5-loop for inheritance in the game UmaMusume. Optimized for best average compatibilities(accounting for parents and grandparents).<br/>
计算五马循环, 最大化平均相性(考虑父母和祖父母)<br/>

# Features
Calculate with custom uma list.<br/>
Provided a priority list, capable of producing an inheritance order for every uma in the 5-loop, optimized for best sum compatibilities in the priority list.<br/>
可使用任意box计算<br/>
可规定五马循环中的偏好种马，计算出五马循环顺序，使偏好种马相性最大化

# Run
With python3, run `python main.py` in the terminal. This starts an interactive session. Follow the prompts to input commands and arguments and get the results.<br/>
在有Python3的环境下, 在终端中运行`python main.py`即可启动交互式会话. 按照提示输入命令和参数即可得到结果

# Usage
After the interactive session starts, type commands first, then follow the instructions and input proper arguments.<br/>
Available commands include 'best_parent', '5loop', 'exit', 'print_all_uma_names'(no quotes)<br/>
Type 'print_all_uma_names' to check the names of all available uma names.<br/>
Type 'exit' to close the session.<br/>
Type 'best_parent' to calculate the best parent for a given uma. After that, follow the prompt and input the target uma name. Then input available uma names(separated with whitespaces) which can be used in the calculation.<br/>
Type '5loop' to calculate a list of 5 uma names for 5-loop inheritance. After that, follow the prompt and input an include list, the result with contain all uma names in the include list. Then input available uma names(separated with whitespaces) which can be used in the calculation. Then input a priority list(optional). If a priority list is provided, the program will calculate a dedicated inheritance order for optimized sum compatibilities in the priority list.<br/>
交互式会话启动后，先输入命令，然后按照提示输入参数<br/>
可用命令包括'best_parent', '5loop', 'exit', 'print_all_uma_names'(不包括引号)<br/>
输入 'print_all_uma_names' 可查看所有可用的马名（使用日文，与数据来源相同）<br/>
输入 'exit' 可退出会话<br/>
输入 'best_parent' 可计算目标马的最佳父辈和祖父辈。输入命令后按照提示输入目标马名。然后输入父辈和祖父辈中可用的马名列表（空格分隔）。<br/>
输入 '5loop' 可计算五马循环。输入命令后按照提示输入包含列表，结果中将包含此列表中所有马。然后输入五马循环中其他可用的马名列表（空格分隔）。然后输入偏好种马列表（可选）。如果提供了偏好种马列表，程序将计算出一个优化偏好种马相性的继承顺序，使得偏好列表中所有种马的相性之和最大化。<br/>

# Example
Input:<br/>
best_parent<br/>
オグリキャップ<br/>
ダイワスカーレット オグリキャップ ウオッカ マヤノトップガン ハルウララ スペシャルウィーク ゴールドシップ アグネスタキオン ウイニングチケット サクラバクシンオー マチカネフクキタル ナイスネイチャ キングヘイロー エルコンドルパサー メジロライアン スーパークリーク グラスワンダー<br/>

Output:<br/>
Score: 213<br/>
Result: オグリキャップ = ウオッカ + グラスワンダー; ウオッカ = グラスワンダー + スペシャルウィーク; グラスワンダー = ウオッカ + スペシャルウィーク<br/>

Input:<br/>
5loop<br/>
スーパークリーク オグリキャップ<br/>
ダイワスカーレット オグリキャップ ウオッカ マヤノトップガン ハルウララ スペシャルウィーク ゴールドシップ アグネスタキオン ウイニングチケット サクラバクシンオー マチカネフクキタル ナイスネイチャ キングヘイロー エルコンドルパサー メジロライアン スーパークリーク グラスワンダー<br/>
スーパークリーク オグリキャップ<br/>

Output:<br/>
スーパークリーク = ナイスネイチャ + スペシャルウィーク<br/>
オグリキャップ = スーパークリーク + ゴールドシップ<br/>
ナイスネイチャ = オグリキャップ + スペシャルウィーク<br/>
スペシャルウィーク = オグリキャップ + ゴールドシップ<br/>
ゴールドシップ = スーパークリーク + ナイスネイチャ<br/>

# Known issues
Grandparents' compatibility R(child, parent, grandparent) is calculated by min(R(child, parent), R(parentX, grandparent), R(child, grandparent)). This is not accurate. To correctly calculate R(child, parent, grandparent), compatibility group data is required, but I cannot find an easy source of that. Any help is appreciated.<br/>
祖父辈的相性R(目标马, 父辈, 祖父辈)的计算方式为min(R(孙, 父母), R(父母X, 祖父母), R(孙, 祖父母))。这种计算方式不准确。要正确计算祖父辈相性需要相性组数据，但是数据来源不好找。欢迎提供数据。<br/>

# Note:
Compatibility data is copied from https://mee1080.github.io/umaishow/. Due to previously mentioned issues, it is recommended to use this site to calculate best parents for a specific uma.<br/>
相性数据拷贝自 https://mee1080.github.io/umaishow/. 由于前述问题，计算目标马的最优继承时推荐使用此网站。<br/>