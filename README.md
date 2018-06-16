# word-frequency-count
# 利用Python做一个词频统计
## 词频统计
　　对纯英语的文本文件【Eg: 瓦尔登湖(英文版).txt】的英文单词出现的次数进行统计，并记录起来
## 代码实现
	import string
	from os import path
	with open('瓦尔登湖(英文版).txt','rb') as text1:
    	words = [word.strip(string.punctuation).lower() for word in str(text1.read()).split()]
    	words_index = set(words)
	    count_dict = {index:words.count(index) for index in words_index}
	    with open(path.dirname(__file__) + '/file1.txt','a+') as text2:
	        text2.writelines('以下是词频统计的结果：' + '\n')
	        for word in sorted(count_dict,key=lambda x:count_dict[x],reverse=True):
	            text2.writelines('{}--{} times'.format(word,count_dict[word]) + '\n')
	        text1.close()
	        text2.close()

## 代码解析
[Python 词频统计](https://www.cnblogs.com/littlebob/p/9189794.html) 
