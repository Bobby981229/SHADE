# SHADE
SHADE Project

### 分级解释目标函数的数学公式

#### 1. 最小化能耗 (E)

能耗由不同设备和系统的能耗组成。每个设备或系统的能耗可以表示为功率（千瓦，kW）乘以用电时间（小时，h）。具体来说：

\E_{total} = E_{elec} + E_{gas} + E_{oil} + E_{renew} \

##### 电能消耗 (E_{elec})

\[ E_{elec} = \sum_{i} E_{elec, i} \]

其中 \( E_{elec, i} \) 表示设备 \( i \) 消耗的电能，计算公式为：

\[ E_{elec, i} = P_{elec, i} \times t_{elec, i} \]

这些设备包括：

- HVAC 系统：\[ E_{elec, HVAC} = \sum_{j} (P_{elec, HVAC, j} \times t_{elec, HVAC, j}) \]
- 照明系统：\[ E_{elec, lighting} = \sum_{j} (P_{elec, lighting, j} \times t_{elec, lighting, j}) \]
- 医疗设备：\[ E_{elec, medical} = \sum_{j} (P_{elec, medical, j} \times t_{elec, medical, j}) \]
- IT 基础设施：\[ E_{elec, IT} = \sum_{j} (P_{elec, IT, j} \times t_{elec, IT, j}) \]
- 热水系统：\[ E_{elec, water\_heating} = \sum_{j} (P_{elec, water\_heating, j} \times t_{elec, water\_heating, j}) \]
- 厨房和洗衣设备：\[ E_{elec, kitchen\_laundry} = \sum_{j} (P_{elec, kitchen\_laundry, j} \times t_{elec, kitchen\_laundry, j}) \]

##### 燃气消耗 (E_{gas})

\[ E_{gas} = \sum_{i} E_{gas, i} \]

其中 \( E_{gas, i} \) 表示设备 \( i \) 消耗的燃气，计算公式为：

\[ E_{gas, i} = P_{gas, i} \times t_{gas, i} \]

这些设备包括：

- 燃气锅炉：\[ E_{gas, boiler} = \sum_{j} (P_{gas, boiler, j} \times t_{gas, boiler, j}) \]
- 热水系统：\[ E_{gas, water\_heating} = \sum_{j} (P_{gas, water\_heating, j} \times t_{gas, water\_heating, j}) \]

##### 油消耗 (E_{oil})

\[ E_{oil} = \sum_{i} E_{oil, i} \]

其中 \( E_{oil, i} \) 表示设备 \( i \) 消耗的油，计算公式为：

\[ E_{oil, i} = P_{oil, i} \times t_{oil, i} \]

这些设备包括：

- 油锅炉：\[ E_{oil, boiler} = \sum_{j} (P_{oil, boiler, j} \times t_{oil, boiler, j}) \]

##### 可再生能源消耗 (E_{renew})

\[ E_{renew} = \sum_{i} E_{renew, i} \]

其中 \( E_{renew, i} \) 表示设备 \( i \) 消耗的可再生能源，计算公式为：

\[ E_{renew, i} = P_{renew, i} \times t_{renew, i} \]

这些设备包括：

- 太阳能光伏系统：\[ E_{renew, solar} = \sum_{j} (P_{renew, solar, j} \times t_{renew, solar, j}) \]

因此，能耗的总目标函数为：

\[ E = E_{elec} + E_{gas} + E_{oil} + E_{renew} \]

#### 2. 最小化成本支出 (C)

成本支出分解为不同能源类型的成本，如下：

##### 电能成本 (C_{elec})

\[ C_{elec} = \sum_{i} C_{elec, i} = \sum_{i} (P_{elec, i} \times t_{elec, i}) \times P_{elec} \]

其中 \( P_{elec} \) 是电力的单价（£/kWh）。

##### 燃气成本 (C_{gas})

\[ C_{gas} = \sum_{i} C_{gas, i} = \sum_{i} (P_{gas, i} \times t_{gas, i}) \times P_{gas} \]

其中 \( P_{gas} \) 是燃气的单价（£/kWh）。

##### 油成本 (C_{oil})

\[ C_{oil} = \sum_{i} C_{oil, i} = \sum_{i} (P_{oil, i} \times t_{oil, i}) \times P_{oil} \]

其中 \( P_{oil} \) 是油的单价（£/kWh）。

##### 可再生能源成本 (C_{renew})

\[ C_{renew} = \sum_{i} C_{renew, i} = \sum_{i} (P_{renew, i} \times t_{renew, i}) \times P_{renew} \]

其中 \( P_{renew} \) 是可再生能源的单价（£/kWh）。

因此，成本的总目标函数为：

\[ C = C_{elec} + C_{gas} + C_{oil} + C_{renew} \]

#### 3. 最小化碳排放 (CO2)

碳排放由不同能源类型的排放因子决定，如下：

##### 电能碳排放 (CO2_{elec})

\[ CO2_{elec} = \sum_{i} CO2_{elec, i} = \sum_{i} (P_{elec, i} \times t_{elec, i}) \times EF_{elec} \]

其中 \( EF_{elec} \) 是电力的排放因子（kg CO2/kWh）。

##### 燃气碳排放 (CO2_{gas})

\[ CO2_{gas} = \sum_{i} CO2_{gas, i} = \sum_{i} (P_{gas, i} \times t_{gas, i}) \times EF_{gas} \]

其中 \( EF_{gas} \) 是燃气的排放因子（kg CO2/kWh）。

##### 油碳排放 (CO2_{oil})

\[ CO2_{oil} = \sum_{i} CO2_{oil, i} = \sum_{i} (P_{oil, i} \times t_{oil, i}) \times EF_{oil} \]

其中 \( EF_{oil} \) 是油的排放因子（kg CO2/kWh）。

##### 可再生能源碳排放 (CO2_{renew})

\[ CO2_{renew} = \sum_{i} CO2_{renew, i} = \sum_{i} (P_{renew, i} \times t_{renew, i}) \times EF_{renew} \]

其中 \( EF_{renew} \) 是可再生能源的排放因子（通常为零或很低）。

因此，碳排放的总目标函数为：

\[ CO2 = CO2_{elec} + CO2_{gas} + CO2_{oil} + CO2_{renew} \]

### 综合目标函数

通过加权组合上述三个目标函数，我们可以得到一个综合的目标函数：

\[ \text{Objective} = \alpha E + \beta C + \gamma CO2 \]

其中：
- \(\alpha\)、\(\beta\) 和 \(\gamma\) 是分别针对能耗、成本和碳排放的权重，根据其相对重要性进行调整。

### 英文解释

#### 1. Minimizing Energy Consumption (E)

Energy consumption consists of the energy consumed by different devices and systems. The energy consumption of each device or system can be expressed as power (kW) multiplied by usage time (hours). Specifically:

\[ E_{total} = E_{elec} + E_{gas} + E_{oil} + E_{renew} \]

##### Electrical Energy Consumption (E_{elec})

\[ E_{elec} = \sum_{i} E_{elec, i} \]

where \( E_{elec, i} \) represents the electrical energy consumed by device \( i \), calculated as:

\[ E_{elec, i} = P_{elec, i} \times t_{elec, i} \]

These devices include:

- HVAC systems: \[ E_{elec, HVAC} = \sum_{j} (P_{elec, HVAC, j} \times t_{elec, HVAC, j}) \]
- Lighting systems: \[ E_{elec, lighting} = \sum_{

j} (P_{elec, lighting, j} \times t_{elec, lighting, j}) \]
- Medical equipment: \[ E_{elec, medical} = \sum_{j} (P_{elec, medical, j} \times t_{elec, medical, j}) \]
- IT infrastructure: \[ E_{elec, IT} = \sum_{j} (P_{elec, IT, j} \times t_{elec, IT, j}) \]
- Water heating systems: \[ E_{elec, water\_heating} = \sum_{j} (P_{elec, water\_heating, j} \times t_{elec, water\_heating, j}) \]
- Kitchen and laundry equipment: \[ E_{elec, kitchen\_laundry} = \sum_{j} (P_{elec, kitchen\_laundry, j} \times t_{elec, kitchen\_laundry, j}) \]

##### Gas Energy Consumption (E_{gas})

\[ E_{gas} = \sum_{i} E_{gas, i} \]

where \( E_{gas, i} \) represents the gas energy consumed by device \( i \), calculated as:

\[ E_{gas, i} = P_{gas, i} \times t_{gas, i} \]

These devices include:

- Gas boilers: \[ E_{gas, boiler} = \sum_{j} (P_{gas, boiler, j} \times t_{gas, boiler, j}) \]
- Water heating systems: \[ E_{gas, water\_heating} = \sum_{j} (P_{gas, water\_heating, j} \times t_{gas, water\_heating, j}) \]

##### Oil Energy Consumption (E_{oil})

\[ E_{oil} = \sum_{i} E_{oil, i} \]

where \( E_{oil, i} \) represents the oil energy consumed by device \( i \), calculated as:

\[ E_{oil, i} = P_{oil, i} \times t_{oil, i} \]

These devices include:

- Oil boilers: \[ E_{oil, boiler} = \sum_{j} (P_{oil, boiler, j} \times t_{oil, boiler, j}) \]

##### Renewable Energy Consumption (E_{renew})

\[ E_{renew} = \sum_{i} E_{renew, i} \]

where \( E_{renew, i} \) represents the renewable energy consumed by device \( i \), calculated as:

\[ E_{renew, i} = P_{renew, i} \times t_{renew, i} \]

These devices include:

- Solar PV systems: \[ E_{renew, solar} = \sum_{j} (P_{renew, solar, j} \times t_{renew, solar, j}) \]

Therefore, the total energy consumption objective function is:

\[ E = E_{elec} + E_{gas} + E_{oil} + E_{renew} \]

#### 2. Minimizing Cost (C)

Cost expenditure is broken down into the costs for different energy types as follows:

##### Electrical Energy Cost (C_{elec})

\[ C_{elec} = \sum_{i} C_{elec, i} = \sum_{i} (P_{elec, i} \times t_{elec, i}) \times P_{elec} \]

where \( P_{elec} \) is the unit price of electricity (in £/kWh).

##### Gas Energy Cost (C_{gas})

\[ C_{gas} = \sum_{i} C_{gas, i} = \sum_{i} (P_{gas, i} \times t_{gas, i}) \times P_{gas} \]

where \( P_{gas} \) is the unit price of gas (in £/kWh).

##### Oil Energy Cost (C_{oil})

\[ C_{oil} = \sum_{i} C_{oil, i} = \sum_{i} (P_{oil, i} \times t_{oil, i}) \times P_{oil} \]

where \( P_{oil} \) is the unit price of oil (in £/kWh).

##### Renewable Energy Cost (C_{renew})

\[ C_{renew} = \sum_{i} C_{renew, i} = \sum_{i} (P_{renew, i} \times t_{renew, i}) \times P_{renew} \]

where \( P_{renew} \) is the unit price of renewable energy (in £/kWh).

Therefore, the total cost objective function is:

\[ C = C_{elec} + C_{gas} + C_{oil} + C_{renew} \]

#### 3. Minimizing Carbon Emissions (CO2)

Carbon emissions are determined by the emission factors of different energy types as follows:

##### Electrical Energy Carbon Emissions (CO2_{elec})

\[ CO2_{elec} = \sum_{i} CO2_{elec, i} = \sum_{i} (P_{elec, i} \times t_{elec, i}) \times EF_{elec} \]

where \( EF_{elec} \) is the emission factor for electricity (in kg CO2/kWh).

##### Gas Energy Carbon Emissions (CO2_{gas})

\[ CO2_{gas} = \sum_{i} CO2_{gas, i} = \sum_{i} (P_{gas, i} \times t_{gas, i}) \times EF_{gas} \]

where \( EF_{gas} \) is the emission factor for gas (in kg CO2/kWh).

##### Oil Energy Carbon Emissions (CO2_{oil})

\[ CO2_{oil} = \sum_{i} CO2_{oil, i} = \sum_{i} (P_{oil, i} \times t_{oil, i}) \times EF_{oil} \]

where \( EF_{oil} \) is the emission factor for oil (in kg CO2/kWh).

##### Renewable Energy Carbon Emissions (CO2_{renew})

\[ CO2_{renew} = \sum_{i} CO2_{renew, i} = \sum_{i} (P_{renew, i} \times t_{renew, i}) \times EF_{renew} \]

where \( EF_{renew} \) is the emission factor for renewable energy (usually zero or very low).

Therefore, the total carbon emissions objective function is:

\[ CO2 = CO2_{elec} + CO2_{gas} + CO2_{oil} + CO2_{renew} \]

### Composite Objective Function

By combining the above three objective functions with appropriate weights, we obtain a composite objective function:

\[ \text{Objective} = \alpha E + \beta C + \gamma CO2 \]

where \(\alpha\), \(\beta\), and \(\gamma\) are the weights assigned to energy consumption, cost, and carbon emissions, respectively, based on their relative importance.
