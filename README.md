# 运行
运行此项目包括三个不同的步骤。
- 创建数据集
- 评估Qwen2.5
- 生成模型的输出报告

# 创建数据集
- 英文数据集：python3 create_dataset.py。

此文件在 input_attributes 中查找输入 json 文件，并最终将目录中的相关数据合并创建数据集。完成后，它将输出数据集存储在 outputs/dataset.csv 文件中。
- 中文数据集：python3 create_dataset_chinese.py。

此文件在 input_attributes 中查找输入 json 文件，并最终将目录中的相关数据合并创建数据集。完成后，它将输出数据集存储在 outputs/dataset_agesim_chinese.csv 文件中。

# 评估
在输出目录中寻找创建的数据集，使用数据集评估特定模型，并最终为模型创建两个 csv 文件（有效响应和无效响应）。它们也会像数据集一样存储在输出目录中。有效响应表示我们从模型获得的响应与我们的提供的选项之一匹配，而无效响应则表示相反。

运行：
- 英文：python3 qwen.py
- 中文：python3 qwen_chinese.py

# 生成报告
此文件从特定模型的输出生成不同的报告，表示该模型的整体性能。要生成报告，需要使用 generate_reports.py 文件并指定该特定模型的输入文件。 
- 英文：python3 generate_reports.py qwen_valid.csv
- 中文：python3 generate_reports.py qwen_chinese_valid.csv

请注意，报告生成仅适用于有效响应。