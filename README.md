# An Implementation of Encoder-Decoder in Translation from Chinese to English
## directory structure
```
|-- dataset  
    | -- train.en  
    | -- train.zh  
    | -- test.en  
    | -- test.zh   
    | -- dev.en  
    | -- dev.zh 
    | -- vocab.en
    | -- vocab.zh
| -- 30epochs.pth
| -- data.json
| -- encoderDecoder.ipynb
| -- requirements.txt
``` 
The`train.en`and`train.zh`files are training collections in English and Chinese, respectively  
The`test.en`and`test.zh`files are testing collections in English and Chinese, respectively  
The test and dev data are the same  
**Provides weight files for training 30 epochs**:`30epochs.pth`  
`data.json `: The file contains custom tables, training sets, and test sets in both English and Chinese  
## network structure  
GRU is used in both Encoder and Decoder  
- embed-dim = 64
- num-hidden = 128
- num-layers = 2
- dropout = 0.1
- vocabZh-size = 32697
- vocabEn-size = 22811 
## devDependencies 
`python >= 3.9`  
`pip install requirements`    
## examples  
```
zh: 全国 政协 副主席 , 中国 工程 院 院长 宋健 等 出席 鉴定会 .
translation: song jian , vice chairman of the national committee of the chinese people 's political consultative conference , and wang <unk> , vice chairman of the national people 's congress .
 label: song jian , vice chairman of the national committee of the chinese people 's political consultative conference and president of the chinese academy of engineering , attended the appraisal meeting .
bleu : 0.7309074863041676

zh: " 和平 统一 , 一国两制 " 的 方计 已 被 越来越 多人 所 认识 , 接受 .
translation: the " one country , two systems " formula and the basic principle of " one country , two systems . "
 label: the principle of " one country , two systems " has been understood and accepted by more and more people .
bleu : 0.5802256926944428

zh: ( 时事 政治 ) 九届 全国 人大 常委会 举办 第二十二 法制 讲座 李鹏 主持 并 讲话 新华社 北京 8月31日 电 九届 全国 人大 常委会 今天 在 人民 大会堂 举办 第二十二 法制 讲座 .
translation: beijing , 28 dec ( xinhua ) - - the ninth national people 's congress [ npc ] standing committee held a meeting to commemorate the deliberation of the ninth npc standing committee .
 label: beijing , 31 aug ( xinhua ) - - the standing committee of the ninth national people 's congress (npc) held its 22 nd lecture on the legal system in the great hall of the people today .
bleu : 0.5401811485739879

zh: 上半年 贷款 累计 增加 7152亿 元 , 同比 多 增加 951亿 元 .
translation: in the first half of the year , the amount of loan loans totaled 3.1135 trillion yuan , up a total of <unk> percent over the same period last year .
 label: during the first half of this year , the accumulated increase in the total loan amount was 715.2 billion yuan , up by 95.1 billion yuan over the same period last year .
bleu : 0.6527745137003019

zh: 江泽民 总书记 指出 " 吏治 的 腐败 , 是 最大 的 腐败 " , 必须 " 从 源头 上 预防 和 治理 腐败 " .
translation: jiang zemin pointed out : " the corruption is the basic corruption of the rural areas , and the corruption is the basic guarantee for the " corruption " and " corruption . "
 label: general party secretary jiang zemin pointed out that " the corruption of the system of cadres is the biggest corruption " and that it is imperative to " prevent and control corruption at the source . "
bleu : 0.5467260581745265
```