# cs224n_spring
研一自学cs224n，不定期更新学习心得+绕坑指南

Assignment 1

踩坑1：:运行第一个import相关单元格报错
“
---------------------------------------------------------------------------
TypeError Traceback (most recent call last)Cell In[1], line 20 17 plt.rcParams['figure.figsize'] = [10, 5] 19 from datasets import load_dataset---> 20 imdb_dataset = load_dataset("stanfordnlp/imdb") 22 import re 23 import numpy as np
...
1061 self.write(MARK + DICT) 1063 self.memoize(obj)-> 1064 self._batch_setitems(obj.items(), obj)
TypeError: Pickler._batch_setitems() takes 2 positional arguments but 3 were given
”

原因：
根据readme指令conda env create -f env.yml中，env.yml未指定具体Python版本，仅要求python>=3.10，因此vscode自行下载了最新Python3.14，导致与dill库等不兼容。

解决方法：
