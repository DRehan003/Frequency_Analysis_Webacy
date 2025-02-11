<h1> Frequency And Correlation Analysis of Smart Contract Vulnerabilities </h1>

Essential Terminology:
- __Smart Contract__: A self-executing program  stored on blockchain that automatically carries out an agreement when certain conditions are met without needing a middleman. <br>
  - For Example: <br>
    Let’s say you want to buy a digital artwork. A smart contract can be set up so that as soon as you send the payment, the artwork is automatically transferred to you. No need for a 
    third party like PayPal or a bank.
  - Smart contracts use cases are ever growing. They can be even used for something as simple as a pair of friends making a bet on which team will win a sports game.
   - Why Are They Important? <br>
     - No Middlemen → No banks, lawyers, or companies needed to enforce the contract
     - Transparent → Everyone can see how the contract works (no hidden rules)
     - Secure & Immutable → Once written on the blockchain, it can’t be changed or tampered with
  <br>
- __Risk Tag__: Think of risk tags like warning labels on food—they alert you to potential dangers before you interact with a wallet or contract. These risk tags are provided by Webacy, a company that provides a security platform that helps protect crypto and NFT assets. There are a total of 32 risk_tags that we will be using. Each risk tag represents a different type of risk.
  - What do they detect?
    - Risks of a contract taking your funds through scam, hacks, or fraud
    - Hacking of your tokens
    - Suspicious activity such as involvement in shady transactions
    - Fake contracts mimicking legit ones

<h1> Part 1: Frequency Analysis </h1>

Objective: Document the occurrence rates of each risk tag across the dataset, providing a clear quantification of the most prevalent vulnerabilities. <br>

<h2> Frequency Analysis in Excel </h2>

<h3> Step 1: Prepare for analysis </h3>

1. Convert all the True and False values to boolean values (1 or 0). We do this so that can turn words into numbers and therefore make it easier to calculate how many smart contracts is labeled with a particular risk tag. <br>

2. To make the data easier to work with you can freeze the top row so you can always see your column headers as you scroll down. This is particularly useful with large datsets. (Go to View > Freeze Panes > Freeze Top Row.)
   
3. Create a new worksheet dedicated to the summary table. This helps keep your analysis organized and separate from the raw data.

4. In column A of the new worksheet, list all the risk tags you are analyzing. Start from A2, leaving A1 for the header "Risk Tag".

<h3> Step 2: Calculating the Frequencies and Percentages </h3>

1. Set Up Frequency Calculation
   
In column B next to each risk tag, calculate the frequency of True values.
Label column B as "Frequency of True".
For example, if the risk tag 'Is_honeypot' is in column B of a worksheet named 'Data', in B2 you would enter:
=COUNTIF(Data!B:B, TRUE)

3. Calculate Total Number of Entries

Determine the total number of entries in your dataset to use in calculating percentages.
Place this formula in a cell in the summary worksheet, for example in B1 (consider renaming it to a more descriptive cell name for clarity):
=COUNTA(Data!B2:B101) // Adjust the range as necessary
Ensure this range matches the total data entries (excluding headers).

3. Calculate the Percentage of True Values

In column C next to the frequency count, calculate the percentage that each frequency represents relative to the total number of entries.
Label column C as "Percentage of True".
In C2, you would enter:
=B2 / $B$1
Format the cells in Column C to percentage format for better readability.

4. Drag to Fill the Formulas

After entering the formulas in B2 and C2 for the first risk tag, use the fill handle to drag the formula down through the column to automatically adjust it for the remaining risk tags.
This action copies the formula while adjusting the row references accordingly but keeps the reference to the total number of entries absolute (using $ signs).

<h3> Step 3: Visualization </h3>

1. Highlight all of your frequency data including the headers.

2. Insert a Bar Chart: Go to Insert > Charts > Bar Chart and choose the first simple bar chart option. Excel will generate a bar chart displaying the frequency of True values for each risk tag.

<h3> Step 4: Findings </h3>

What are the most frequently seen risk tags? <br>
1. Exploitation (43%)
2. Bad_contract (34%)
3. external_dependencies (29%)

What are the least frequently seen risk tags? <br>
1. illegal_unicode
2. is_airdrop_scam
3. is_blacklisted

<h1> Part 2: Correlation Analysis </h1>

Objective: Create a visual representation of the correlation matrix to highlight potential relationships between different risk tags. <br>

<h1> Conclusion </h1>

How did the frequency and correlation findings provide actionable insights into improving smart contract security? Include potential implications for preventive measures and the prioritization of security efforts. <br>


