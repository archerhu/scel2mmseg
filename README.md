将搜狗(sogou)的细胞词库转换为mmseg的词库

功能：

 - scel2mmseg.py: 将.scel文件转换为mmseg格式的.txt文件
 
 使用方法： python scel2mmseg.py a.scel a.txt

 批量转换方法：python scel2mmseg.py scel文件目录 a.txt
 
 说明：新增加的所有词的词频都为1，对于格式的解释如下：[摘自 http://jjw.in/server/226 ]
> 每条记录分两行。其中，第一行为词项，其格式为：[词条]\t[词频率]。需要注意的是，对于单个字后面跟这个字作单字成词的频率，这个频率需要在大量的预先切分好的语料库中进行统计，用户增加或删除词时，一般不需要修改这个数值；对于非单字词，词频率处必须为1。第二行为占位项，是由于LibMMSeg库的代码是从Coreseek其他的分词算法库（N-gram模型）中改造而来的，在原来的应用中，第二行为该词在各种词性下的分布频率。LibMMSeg的用户只需要简单的在第二行处填”x:1″即可

 - mergedict.py: 将mmseg的多个.txt文件合并为一个.txt
 
 使用方法： python mergedict.py unigram.txt b.txt c.txt new.txt
 
 说明： .txt可以使mmseg格式的，也可以是每行一个词的格式（这样词频默认为1）
 
 注意：因为merge的时候会判重，一个词在前面出现过，就不会追加到新产生的文件中,所以要将unigram.txt放到最前面



