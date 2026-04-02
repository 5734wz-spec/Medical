

# 项目介绍
本项目将包括两部分的内容：
1) 基于垂直网站数据的医药知识图谱构建
2) 基于医药知识图谱的自动问答

# 运行方式
1、配置要求：要求配置neo4j数据库及相应的python依赖包。neo4j数据库用户名密码记住，并修改相应文件。  
2、知识图谱数据导入：python build_medicalgraph.py，导入的数据较多，估计需要几个小时。  
3、启动问答：python chatbot_graph.py


# 脚本目录
prepare_data/datasoider.py：网络资讯采集脚本  
prepare_data/datasoider.py：网络资讯采集脚本  
prepare_data/max_cut.py：基于词典的最大向前/向后切分脚本  
build_medicalgraph.py：知识图谱入库脚本    　　

# 脚本结构
question_classifier.py：问句类型分类脚本  
question_parser.py：问句解析脚本  
chatbot_graph.py：问答程序脚本  

# 支持问答类型

| 问句类型 | 中文含义 | 问句举例 |
| :--- | :---: | :---: |
| disease_symptom | 疾病症状| 乳腺癌的症状有哪些？ |
| symptom_disease | 已知症状找可能疾病 | 最近老流鼻涕怎么办？ |
| disease_cause | 疾病病因 | 为什么有的人会失眠？|
| disease_acompany | 疾病的并发症 | 失眠有哪些并发症？ |
| disease_not_food | 疾病需要忌口的食物 | 失眠的人不要吃啥？ |
| disease_do_food | 疾病建议吃什么食物 | 耳鸣了吃点啥？ |
| food_not_disease | 什么病最好不要吃某事物 | 哪些人最好不好吃蜂蜜？ |
| food_do_disease | 食物对什么病有好处| 鹅肉有什么好处？ |
| disease_drug | 啥病要吃啥药 | 肝病要吃啥药？ |
| drug_disease | 药品能治啥病 | 板蓝根颗粒能治啥病？ |
| disease_check | 疾病需要做什么检查 | 脑膜炎怎么才能查出来？|
| check_disease |　检查能查什么病 | 全血细胞计数能查出啥来？ |
| disease_prevent | 预防措施| 怎样才能预防肾虚？ |
| disease_lasttime | 治疗周期 | 感冒要多久才能好？ |
| disease_cureway | 治疗方式 | 高血压要怎么治？ |
| disease_cureprob | 治愈概率 | 白血病能治好吗？ |
| disease_easyget | 疾病易感人群 | 什么人容易得高血压？ |
| disease_desc | 疾病描述 | 糖尿病 |

# 数据
数据处理之后会得到一个json格式化文件，这个文件在我后面利用RAG优化时将会用到
