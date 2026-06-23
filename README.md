# ai-ecommerce-evaluation-quality
End-to-end AI evaluation project demonstrating how to assess, validate, and improve AI-generated e-commerce outputs using structured rubrics, quantitative analysis, and data quality frameworks.

The project evaluates chatbot interactions, product information, and SEO performance summaries to identify inaccuracies, detect edge cases, and provide evidence-based recommendations for improving AI reliability and business decision-making.
# 🧠 AI Evaluation of E-commerce Chatbot Responses Using Rubric-Based Quality Scoring

## 📌 Overview
This project evaluates the quality of AI-generated chatbot responses in an e-commerce environment using a structured rubric-based scoring framework.

The evaluation combines:
- quantitative scoring  
- error taxonomy analysis  
- targeted manual review  

---

## 🎯 Objectives
- Evaluate chatbot responses across key quality dimensions  
- Identify recurring failure patterns  
- Compare performance across intents and categories  
- Generate actionable AI improvement insights  

---

## 📊 Dataset
- **Bitext Retail & E-commerce Chatbot Dataset**
- Sample size: **390 rows (stratified by category)**
- Fields:
  - prompt  
  - intent  
  - category  
  - ai_response  

---

## ⚙️ Methodology

### ✅ Evaluation Framework
Each response is scored using a **1–5 scale** across:
- Accuracy  
- Relevance  
- Completeness  
- Consistency  
- Business Usefulness  
- Clarity  

---

### ✅ Error Taxonomy
Responses are classified using:
- `overly_generic_response`
- `missing_key_step_or_omission`
- `too_verbose_or_inefficient`

---

### ✅ Workflow
1. Data cleaning and standardisation  
2. Stratified sampling (390 rows)  
3. Semi-automated scoring  
4. Targeted manual review:
   - low-quality responses  
   - edge cases  
   - error clusters  
5. Aggregation and visualisation  

---

## 📈 Visual Analysis

### 📊 Rubric Score Distribution
![Rubric Score Distribution](visuals/rubric_score_distribution.png)

**Insight:**  
Relevance and Consistency are the strongest dimensions, while Completeness and Business Usefulness are slightly lower — indicating responses are correct but not always fully actionable.

---

### ⚠️ Error Taxonomy Distribution
![Error Taxonomy Distribution](visuals/error_taxonomy_distribution.png)

**Insight:**  
Overly generic responses dominate, followed by verbosity issues, while missing steps are relatively rare. This shows the key issue is **lack of specificity, not correctness**.

---

### 🔍 Response Quality by Intent
![Response Quality by Intent](visuals/response_quality_by_intent.png)

**Insight:**  
Performance is consistent across intents, suggesting stable reliability but limited adaptation to different query types.

---

### 🛒 Response Quality by Category
![Response Quality by Category](visuals/response_quality_by_category.png)

**Insight:**  
Quality remains stable across categories, reinforcing that the chatbot is reliable but not highly optimised for category-specific context.

---

### ⚡ Edge Case Analysis


## ⚡ Edge Case Examples

| Prompt | Intent | Category | Error Type | Evaluation Summary | Improvement Recommendation |
|------|--------|----------|------------|-------------------|---------------------------|
| "I want to add product to cart now!!!" | add_product | CART | overly_generic_response | Response is relevant but uses standardised phrasing and lacks specific guidance. | Provide clearer, step-based instructions tailored to user context. |
| "why haven't I received my order???" | track_order | DELIVERY | overly_generic_response | Response acknowledges the issue but remains generic and does not guide next steps effectively. | Include actionable steps such as checking tracking details or contacting support. |
| "refund me right now this is unacceptable" | request_refund | PAYMENT | overly_generic_response | Response remains polite and aligned with intent but lacks urgency and targeted resolution steps. | Provide clear refund process steps and priority escalation guidance. |
| "where is my stuff and when will it come" | track_delivery | DELIVERY | overly_generic_response; missing_key_step_or_omission | The answer addresses delivery but omits steps for tracking or resolving delays. | Add tracking instructions and expected timelines. |
| "can I change my order and refund it?" | change_order | ORDER | overly_generic_response | Multi-intent request handled partially; response does not clearly separate actions. | Break into structured steps addressing both change and refund processes. |
| "do u guys even know my problem?" | customer_service | GENERAL | overly_generic_response | Response is polite but fails to address the implied frustration and unclear request. | Ask clarifying questions before giving a generic response. |
| "I need help ASAP with my payment issue" | payment_issue | PAYMENT | overly_generic_response | Response is relevant but lacks urgency handling and detailed troubleshooting steps. | Provide step-by-step troubleshooting and escalation options. |
| "I want to return but I don't know how" | return_product | RETURNS | missing_key_step_or_omission | Response acknowledges return request but does not provide clear instructions. | Include detailed return procedure and necessary conditions. |
| "help me order product now quickly" | place_order | ORDER | overly_generic_response | Response is correct but too generic and not adapted to urgency. | Provide direct quick-order steps and shortcuts. |
| "why is this product out of stock again?" | product_availability | INVENTORY | overly_generic_response | Response explains stock issue but lacks meaningful explanation or alternatives. | Suggest restock timelines or alternative products. |

**Insight:**  
> These edge-case examples demonstrate that while the chatbot maintains correctness and tone under difficult conditions, it frequently defaults to generic responses instead of context-aware, action-oriented guidance.
The chatbot handles difficult prompts (e.g., rude or ambiguous queries) effectively, but still produces generic responses instead of context-aware answers.

---

## 💡 Key Insight

> The chatbot performs reliably but lacks optimisation.  
> The primary limitation is not correctness, but insufficient specificity and contextual awareness.

---

## 🏢 Business Implications

- ✅ Reliable for customer support  
- ⚠️ Generic responses may reduce:
  - user trust  
  - satisfaction  
  - perceived intelligence  
- ⚠️ Potential negative impact on e-commerce conversion  

---

## 🚀 Recommendations

- Improve response specificity  
- Reduce template-based outputs  
- Enhance completeness in transactional workflows  
- Introduce intent-aware response tuning  
- Optimise response length and clarity  

---

## ⚠️ Challenges & Solutions

| Challenge | Solution |
|----------|---------|
| Small initial sample | Used 390 stratified sample |
| No errors detected initially | Improved error detection logic |
| Notebook execution issues | Structured pipeline + run-all |
| Weak initial visuals | Expanded dataset coverage |
| Auto-scoring limitations | Added targeted manual review |

---

## 🔧 What I Would Improve Next

- Extend evaluation to additional datasets  
- Add inter-rater agreement checks  
- Refine error taxonomy  
- Build scoring interface  
- Compare auto vs manual scoring  
- Add KPI-based evaluation extension  

---

## 🛠 Tools Used

- Python (pandas, numpy)  
- Matplotlib / Seaborn  
- Jupyter Notebook  

---

## 🔄 Before vs Improved Response Examples

These examples demonstrate how chatbot responses can be improved from generic responses to more structured, actionable, and user-focused outputs.

---

### Example 1 — Add to Cart (CART)

**User Prompt:**  
"I want to add product to cart now!!!"

**Before (AI Response):**  
"I'm here to help you with that! You can add the product to your cart easily."

**Issues:**  
- overly generic  
- lacks clear steps  

**Improved Response:**  
"To add the product to your cart:
1. Select the product you want.
2. Click the **'Add to Cart'** button.
3. Review your cart to confirm the item has been added.

If you're using the mobile app, tap the cart icon after adding the item to verify."

---

### Example 2 — Delivery Issue (DELIVERY)

**User Prompt:**  
"why haven't I received my order???"

**Before (AI Response):**  
"I can help you with your order. Please check your delivery status."

**Issues:**  
- vague  
- not actionable  

**Improved Response:**  
"You can track your order by:
1. Going to the **'My Orders'** section
2. Selecting the order
3. Clicking **'Track Delivery'**

If your delivery is delayed:
- Check the expected delivery date
- Contact support for an update

Would you like me to help you track your order now?"

---

### Example 3 — Refund Request (PAYMENT)

**User Prompt:**  
"refund me right now this is unacceptable"

**Before (AI Response):**  
"I'm here to assist you with your request. Refunds can be processed."

**Issues:**  
- lacks urgency  
- lacks steps  

**Improved Response:**  
"I understand your concern, and I’ll help you resolve this quickly.

To request a refund:
1. Go to **'My Orders'**
2. Select the item
3. Click **'Request Refund'**

If this is urgent, you can contact support directly for faster processing. Let me know if you want assistance initiating the refund."

---

### Example 4 — Multi-intent (ORDER)

**User Prompt:**  
"can I change my order and refund it?"

**Before (AI Response):**  
"I can assist you with that request."

**Issues:**  
- does not handle multiple intents  
- unclear  

**Improved Response:**  
"You can do both depending on your order status:

✅ **To change your order:**
- Go to **'My Orders'**
- Select the order
- Choose **'Modify Order'** (if available)

✅ **To request a refund:**
- Select the order
- Click **'Request Refund'**

Note: If the order has already shipped, you may need to request a refund instead of modifying it."

---

### Example 5 — Edge Case (Rude Query)

**User Prompt:**  
"do u guys even know my problem?"

**Before (AI Response):**  
"I'm here to help you with your issue."

**Issues:**  
- no clarification  
- generic  

**Improved Response:**  
"I'm here to help — could you please share a bit more about the issue you're facing with your order or product?

Once I have more details, I’ll guide you step by step."

---

### 🔍 Key Takeaway

> The improved responses are:
- more structured ✅  
- more actionable ✅  
- more context-aware ✅  

This demonstrates that improving chatbot performance is less about correctness and more about **response quality optimisation**.

## 📂 Project Structure
