# Creating a Financial Advisor Bot with Watson Orchestrate
In this example, a Proof of Value (POV) is created to demonstrate how a bot could be implemented as a financial advisor. This bot can recommend investment products to clients that best match their needs.

## Steps to Create a Bot

### 1. Access Assistant Builder
To get started:
1. Open **Watson Orchestrate**.
2. Navigate to the **AI Assistant Builder** section.
<img src="https://github.com/user-attachments/assets/a2daae6d-97a4-409e-bf72-83655ef45acc" width="900" height="300" />

### 2. Create a new bot
1. At the top of the page, locate and select **Create New**.
<img src="https://github.com/user-attachments/assets/5b898c83-9405-4639-a2e3-2f129bc277d6" width="900" height="300" />

2. Use the following text `Store Bot` in the Assistant name field
3. Then click on **Create assistant**.

### 2. Configure General purpose
1. In the builder interface, locate and select `Change` under the **General purpose** box. <img src="https://github.com/user-attachments/assets/2ae9c63b-ea58-4396-9c27-02ceee7ec675" width="900" height="300" />

2. In the select the model field select: **granite-3-8b-instruct (recommended)**.
3. In the builder interface, locate and select **Add Prompt Instructions**.
4. Use the following prompt text:

   > "As a contact center executive tasked with answering several questions related to insurance coverage and bank products.  
   > Answer the questions accurately and effectively."
<img src="https://github.com/user-attachments/assets/609f779d-41c6-494d-a6b5-603b3c87f851" width="900" height="300" />

### 3. Define Actions and Steps

#### 3.1. Create Initial Actions
1. Click on **Actions**.
2. Select **Set by Assistant**.
3. Add a new action: **Greet Customer**.
<img src="https://github.com/user-attachments/assets/d47faef2-23de-40cc-980b-f36d0bd7e764" width="900" height="300" />

#### 3.2. Configure the First Step
1. In the first step of **Greet Customer**, add the following responses:
   - **Finance**
   - **Insurance**
<img src="https://github.com/user-attachments/assets/89febf35-1848-4377-a118-1222e4fa20a9" width="900" height="300" />

#### 3.3. Add a New Conditional Step
1. Click on **New Step**.
2. Set up the condition: If the user selects **Finance**, respond with:
   - **"What can I help you with?"** <img src="https://github.com/user-attachments/assets/ba2b5330-7372-4dae-9196-b168a2444023"  width="900" height="300" />
3. Configure the **Continue to next step**:
   - **Go to a subaction**
4. Assign the action **Search into My Products** to handle the response. But before follow Step 4, to create this action first. Use the close buttom at the top-right to move back at the `builder interface`.
<img src="https://github.com/user-attachments/assets/ee4dbedd-94e4-4de0-9cd4-1b3a63dc8caf" width="900" height="300" />

### 4. Create a Custom Action

#### 4.1. Define a New Action
1. Go to **Actions Created by You**. <img src="https://github.com/user-attachments/assets/d64e8d55-8164-49b5-9145-08c33211e3e7" />

2. Click **New Action**. 
3. Select **AI-Guided Action**.
4. Name the action **Search into My Products**.
5. Save the action.

#### 4.2. Set Model and Knowledge Base
1. In the action editor, select the model: **granite-3-8b-instruct (recommended)**.
2. Add the following to the **Knowledge** section: [Financial Product Advisor Knowledge](https://github.com/cguillencr/watson_orchestrate/blob/main/demos/financial_product_advisor/Knowledge.md)
3. Include the following in the **Instructions** section:
```
Respond as a customer service agent in a friendly and accurate manner.
```

### Final Steps

- Test your bot to ensure the conditional steps and custom actions are working as expected.  
  <img src="https://github.com/user-attachments/assets/eae6609a-f604-44d1-8759-a2149d577c35" width="900" height="300" />

---

#### Test 1  
**Input:**  
```
Hi, I'm looking to invest in the stock market. What do you recommend?
```

**Response:**  
```
Hello! I'd be happy to help you explore some investment options based on the provided context.

For a balanced approach, you might consider the "Balanced Growth Fund" under the Moderate Profile. This fund combines equities and fixed-income securities to achieve steady growth with moderate risk exposure. It's a good option if you're looking for a mix of income and growth.

If you're interested in companies with a strong history of paying dividends, the "Dividend Yield Portfolio" could be a suitable choice. This portfolio includes dividend-paying stocks, REITs, and preferred shares.

For those seeking higher potential returns, the "Emerging Market Opportunities Fund" under the Aggressive Profile might be of interest. This fund invests in equities and bonds from rapidly growing emerging markets worldwide, offering high-risk, high-reward potential.

Remember, it's important to consider your personal financial goals, risk tolerance, and investment horizon when choosing an investment product. If you need more personalized advice, I would recommend consulting with a financial advisor.
```

**Screenshot:**  
![image](https://github.com/user-attachments/assets/bc78efc6-5a59-4cf8-afc4-bcc172d13543)

---

#### Test 2  
**Input:**  
```
What low-risk investment products do you have available?
```

**Response:**  
```
For clients with a conservative profile, we offer several low-risk investment products. These include:

Secure Treasury Fund: This fund invests in government treasury bonds with short-to-medium maturity dates, providing stable returns with minimal volatility.

Fixed Deposit Growth Account: This is a time-locked deposit account with a guaranteed interest rate, ideal for preserving capital while earning predictable returns.

Government Securities Portfolio: This portfolio consists of investment-grade government securities offering reliable returns with virtually no default risk.

Corporate Bond Ladder: This involves a structured investment in high-quality corporate bonds, ensuring consistent interest payouts over staggered maturity dates.

Capital Preservation Fund: This mutual fund is designed to safeguard principal investment, offering modest returns by investing in high-rated debt instruments.

These options are suitable for those who prioritize capital preservation and seek steady, albeit modest, returns over high growth potential.
```

**Screenshot:**  
![image](https://github.com/user-attachments/assets/1c7a3012-608c-43b1-9306-3350989af012)
