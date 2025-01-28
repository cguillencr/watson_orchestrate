# How to Get Started with Watson Orchestrate to Build a Bot Using Granite-3-8B-Instruct

This guide walks you through creating a bot in Watson Orchestrate using the Assistant Builder and the recommended model `granite-3-8b-instruct`. Follow these steps to set up a bot and configure its actions effectively.

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
2. Add the following to the **Knowledge** section:
```
**Financial Investment Products Categorized by Client Profiles (From Conservative to Aggressive)**  

### **Conservative Profile**  
1. **Secure Treasury Fund**  
   *Description*: A low-risk investment fund focused on government treasury bonds with short-to-medium maturity dates, providing stable returns with minimal volatility.  
   *Assets Included*: U.S. Treasury bonds, municipal bonds, and savings certificates.  

2. **Fixed Deposit Growth Account**  
   *Description*: A time-locked deposit account with a guaranteed interest rate, ideal for preserving capital while earning predictable returns.  
   *Assets Included*: Bank fixed deposits.  

3. **Government Securities Portfolio**  
   *Description*: A portfolio of investment-grade government securities offering reliable returns with virtually no default risk.  
   *Assets Included*: Federal bonds and T-Bills.  

4. **Corporate Bond Ladder**  
   *Description*: A structured investment in high-quality corporate bonds, ensuring consistent interest payouts over staggered maturity dates.  
   *Assets Included*: AAA-rated corporate bonds.  

5. **Capital Preservation Fund**  
   *Description*: A mutual fund designed to safeguard principal investment, offering modest returns by investing in high-rated debt instruments.  
   *Assets Included*: Treasury bills, sovereign bonds, and high-grade corporate bonds.  

---

### **Moderate Profile**  
6. **Balanced Growth Fund**  
   *Description*: A diversified mutual fund combining equities and fixed-income securities to achieve steady growth and moderate risk exposure.  
   *Assets Included*: 50% large-cap stocks, 50% bonds.  

7. **Dividend Yield Portfolio**  
   *Description*: A portfolio focused on stocks from companies with a strong history of paying dividends, offering a blend of income and growth.  
   *Assets Included*: Dividend-paying stocks, REITs, and preferred shares.  

8. **Index Tracker ETF**  
   *Description*: An exchange-traded fund that mirrors the performance of a major stock market index, providing low-cost diversification.  
   *Assets Included*: S&P 500 or Nasdaq 100 stocks.  

---

### **Aggressive Profile**  
9. **Emerging Market Opportunities Fund**  
   *Description*: A high-risk, high-reward fund investing in equities and bonds from rapidly growing emerging markets worldwide.  
   *Assets Included*: Emerging market stocks and sovereign debt.  

10. **High-Growth Tech Venture Portfolio**  
   *Description*: A portfolio focusing on early-stage technology companies and innovative startups, offering the potential for significant capital gains.  
   *Assets Included*: Growth stocks, IPO shares, and venture capital funds.  
```
3. Include the following in the **Instructions** section:
```
Respond as a customer service agent in a friendly and accurate manner.
```

### Final Steps
- Test your bot to ensure the conditional steps and custom actions are working as expected.
  <img src="https://github.com/user-attachments/assets/eae6609a-f604-44d1-8759-a2149d577c35"  width="900" height="300"  />

