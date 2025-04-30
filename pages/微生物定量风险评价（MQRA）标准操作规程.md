- 目的
	- 提供一套严谨的基础研究框架和数据方法来源，方便快速掌握QMRA技术
	- 提供代码工具，简化计算和绘图过程
- 范围
- 术语
- 所需软件
- 操作步骤
	- 数据输入
		- 原始采样参数
			- 整理为规范的excel
				- 采样信息
				  collapsed:: true
					- collapsed:: true
					  
					  **日期 (sample_date)**
						- **英文列名:** `sample_date`
						- **数据类型:** 日期时间 (`datetime64[ns]`)
						- **约束条件:**  `'YYYY-MM-DD'` 或 `'YYYY/MM/DD'`。
						- **缺失值:** 不允许
					- collapsed:: true
					  
					  **采样点 (sampling_location)**
						- **英文列名:** `sampling_location`
						- **数据类型:** 文本
						- **约束条件:** 值必须属于一个预定义的列表
						- **缺失值:** 不允许。
					- collapsed:: true
					  
					  **平行样编号 (parallel_sample_id)**
						- **英文列名:** `parallel_sample_id`
						- **数据类型:** 文本 (`object`)
						- **约束条件:** 格式必须是 `数字-数字` (例如 '1-1', '1-2', '2-1')。可以用正则表达式 `^\d+-\d+$` 来精确匹配，或者简单检查是否包含 `-` 且两部分是数字。
						- **缺失值:** 不允许 (每个样本都需要平行编号)。
					- collapsed:: true
					  
					  **微生物名称 (microorganism_name)**
						- **英文列名:** `microorganism_name`
						- **数据类型:** 文本/分类 (`object` 或 `category`)
						- **约束条件:** 值必须属于一个预定义的列表，例如 `['Aspergillus fumigatus', 'Staphylococcus aureus']` (根据你研究的微生物填充)。
						- **缺失值:** 不允许 (必须明确测定的是哪种微生物)。
					- collapsed:: true
					  
					  **安德森第几级 (andersen_stage)**
						- **英文列名:** `andersen_stage`
						- **数据类型:** 整数 (`int64`)
						- **约束条件:** 必须是 1 到 6 之间的整数 (包括 1 和 6)。
						- **缺失值:** 不允许 (必须知道样本来自哪个级别)。
					- collapsed:: true
					  
					  **采样时间(min) (sampling_time_min)**
						- **英文列名:** `sampling_time_min`
						- **数据类型:**  `int64`
						- **约束条件:** 必须是大于 0 的数值。
						- **缺失值:** 不允许 (采样时间是计算浓度的关键参数)。
					- collapsed:: true
					  
					  **培养数量(CFU) (colony_count_cfu)**
						- **英文列名:** `colony_count_cfu`
						- **数据类型:** 整数 (`int64`)
						- **约束条件:** 必须是大于或等于 0 的整数 (菌落数不能是负数，可以为 0)。
						- **缺失值:** 不允许 (没有读数应明确记录为 0，而不是留空)。
				-
			- 使用终端导入数据
			-
		- 暴露模型参数
- 数据管理与存档
- 质量保证与控制