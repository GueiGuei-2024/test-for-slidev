---
layout: section
---

# Patient Lab Data Review
### 日期範圍：2026-04-17 ~ 2026-04-18

---
layout: default
---

# 1. 生化檢驗與氣體分析 (Biochemistry & ABG)

<div class="grid grid-cols-2 gap-4">
<div>

| 項目 (單位) | 數值 | 臨床註記 |
| :--- | :--- | :--- |
| **Glucose** (mg/dL) | <span style="color:red">**575**</span> | **Severe Hyperglycemia** |
| **Sodium** (mmol/L) | <span style="color:red">**126**</span> | Hyponatremia |
| **Creatinine** (mg/dL) | <span style="color:red">**1.42**</span> | eGFR: 49-52 |
| **B-Ketone** | <span style="color:red">**1+**</span> | Ketosis suspicious |
| **Na+** (ABG) | <span style="color:red">**128.2**</span> | |
| **K+** (mmol/L) | 4.2 | |

</div>
<div>

| ABG 項目 | 數值 | 臨床意義 |
| :--- | :--- | :--- |
| **pH** | 7.454 | Normal/Mild Alkalemia |
| **PCO2** (mmHg) | <span style="color:red">**30.1**</span> | Respiratory Compensation |
| **HCO3-** (mmol/L) | <span style="color:red">**20.6**</span> | Metabolic Acidosis |
| **PO2** (mmHg) | <span style="color:red">**49.5**</span> | **Hypoxemia (Type I RF)** |
| **sO2c** (%) | <span style="color:red">**87.5**</span> | |
| **Lactate** | 1.3 | Normal |

</div>
</div>



---
layout: default
---

# Lab Results: Hematology

<div class="text-sm h-100 overflow-y-auto">

| 檢驗名稱 | 數值 | 單位 |
| :--- | :--- | :--- |
| **WBC** | <span style="color:red">**11.9**</span> | 10^3/μL |
| **Hb** | <span style="color:red">**11.1**</span> | g/dL |
| **Platelet** | 225 | 10^3/μL |
| <span class="pl-4 text-gray-500">Segment</span> | <span style="color:red">**88.9**</span> | % |
| <span class="pl-4 text-gray-500">Lymphocyte</span> | <span style="color:red">**4.0**</span> | % |
| <span class="pl-4 text-gray-500">Mono</span> | 6.9 | % |
| <span class="pl-4 text-gray-500">Eos</span> | 0.0 | % |
| <span class="pl-4 text-gray-500">Baso</span> | 0.2 | % |
| **PT (INR)** | <span style="color:red">**1.4**</span> | |
| **APTT** | 29.8 | secs |
| **MDW** | <span style="color:red">**23.11**</span> | |

</div>

<style>
/* 如果覺得 text-sm 還不夠小，可以直接微調表格字體 */
table {
  font-size: 1 rem;
  line-height: 1.2;
}
</style>

---
layout: default
---

# 3. 尿液分析與病毒篩檢 (U/A & Virus Kit)

<div class="grid grid-cols-2 gap-4">
<div>

### 尿液分析 (U/A)
| 項目 | 數值 | 臨床意義 |
| :--- | :--- | :--- |
| **SG** | <span style="color:red">**>= 1.050**</span> | Highly concentrated |
| **Protein** | <span style="color:red">**3+**</span> | Proteinuria |
| **Glucose** | <span style="color:red">**2+**</span> | Glycosuria |
| **Blood** | <span style="color:red">**2+**</span> | Hematuria |
| **RBC** | 3~5 | /HPF |
| **Ketone** | Negative | |

</div>
<div>

### 病毒快速診斷 (Rapid Test)
| 檢體：鼻咽拭子 | 結果 |
| :--- | :--- |
| **Influenza A** | <span style="color:green">Negative</span> |
| **Influenza B** | <span style="color:green">Negative</span> |
| **SARS-CoV-2 Ag** | <span style="color:green">Negative</span> |

<br>

> **Summary:**
> 1. 高血糖 (575 mg/dL) 伴隨尿糖與血鈉低。
> 2. 呼吸衰竭/低血氧 (PO2 49.5)。
> 3. 感染跡象 (WBC/Seg 增加, MDW 高)。

</div>
</div>

---
layout: default
---

<div class="relative z-20">
  <h1>2020 CT Scan</h1>
</div>

<CTScanner 
folder="CT_image" 
  prefix="test" 
  :maxIndex="31"
 />

<style>
/* 確保 h1 渲染後不會被 slidev 預設樣式吃掉 */
h1 {
  color: white
}
</style>