# RAG-application

#### 1. 数据提取

> 类比于资料库的资料来源。主要目标是确保资料数据完整，除此之外，还可以新生成一些数据，比如利用大模型对资料进行summary，打标签，以便于后续处理更高效。

- 数据清洗

#### 2. 分块(Chunking)

> 类比于资料应该拆分到多细来存储，用梗话来说就是“对齐颗粒度”。 比如按段落拆，按句子拆，按单词拆等等。

- 调整好chunk_size

#### 3. 向量化(Embedding)

> 类比于把拆分后的内容转换为计算机可处理的向量形式。向量化就是把一个物体拆成多个维度表达。

- 微调Embedding模型

#### 4. 创建索引

> 类比于把向量化后的资料块进行分类、整理，按照一定顺序放在对应位置后给出序号，方便后面的检索查找。索引可以建多个，比如书可以按照图书分类排序，也可以按照出版时间排序。

#### 5. 检索(Retriever)

> 系统会根据用户的提问，在索引中查找最相关的数据块。主要目标就是找到和问题匹配度高的资料(注意此时还没有形成答案)。

- 调整好召回的top_k
- 向量检索、语义检索与知识图谱检索结合

#### 6. 检索评估

#### 7. 重排序(Rerank)

> 语义检索出来的结果相当于是资料初筛，讲究的是效率，重排序顾名思义就是对初步检索结果进行重排序，以便得到更精确的结果。

#### 8. 重排评测

#### 9. 生成(Generator)

> 这一步对应的就是系统终于找到了最准确的资料，将资料整理总结，形成完整报告。实际上就是将重排序后的资料片段加上用户的提示词，提供给大型语言模型LLM，由 LLM 根据上下文生成最终的输出。在这个过程中，主要在提示词、上下文、意图识别方面下功夫。

- 优化prompt
- 用户query重写
- [HyDE改写](https://blog.csdn.net/u014297502/article/details/143023361?spm=1001.2014.3001.5501)

#### 10. 最终评估
