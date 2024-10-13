# Exploratory Data Analysis on Credit History of Bank Users
## Problem Statement
- The loan providing companies find it hard to give loans to the people due to their insufficient or non-existent credit history. Because of that, some consumers use it to their advantage by becoming a defaulter.
- Use EDA to analyse the patterns present in the data
- Ensure that the applicants capable of repaying the loan are not rejected
- Two types of risks are associated with the bank’s decision of loan approval based on the applicant’s profile:
  - If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
  - If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company.
## Scenario and Decision
- The data given below contains the information about the loan application at the time of applying for the loan. It contains two types of scenarios:
  - **The client with payment difficulties**
    - he/she had late payment more than X days on at least one of the first Y instalments of the loan in our sample,
  - **All other cases**
    - All other cases when the payment is paid on time.
- When a client applies for a loan, there are four types of decisions that could be taken:
  - **Approved**
    - The Company has approved loan Application
  - **Cancelled**
    - The client cancelled the application sometime during approval. Either the client changed her/his mind about the loan or in some cases due to a higher risk of the client, he received worse pricing which he did not want.
  - **Refused**
    - The company had rejected the loan (because the client does not meet their requirements etc.).
  - **Unused offer**
    - Loan has been cancelled by the client but at different stages of the process.
In this case study, you will use EDA to understand how consumer attributes and loan attributes influence the tendency to default.
## Business Objectives
- To identify patterns which indicate if a client has difficulty paying their instalments
  - Action based on patterns such as
    - Denying the loan
    - Reducing the amount of loan
    - Lending (to risky applicants) at a higher interest rate, etc.
  - Ensure that the consumers capable of repaying the loan are not rejected
  - Identification of applicants that are capable of repaying using EDA is the aim of this case study
- Understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.
  - The company can utilise this knowledge for its portfolio and risk assessment.
  - To develop your understanding of the domain, you are advised to independently research a little about risk analytics - understanding the types of variables and their significance should be enough.
## Data Sets
Dataset has 3 files as explained below: 
- 'application_data.csv’
  - contains all the information of the client at the time of application.
  - The data is about whether a client has payment difficulties.
- 'previous_application.csv’
  - contains information about the client’s previous loan data.
  - It contains the data on whether the previous application had been Approved, Cancelled, Refused or Unused offer.
- 'columns_description.csv’
  - is data dictionary which describes the meaning of the variables.
## Columns Description
<html xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:x="urn:schemas-microsoft-com:office:excel"
xmlns="http://www.w3.org/TR/REC-html40">

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Excel.Sheet>
<meta name=Generator content="Microsoft Excel 15">
<link rel=File-List href="columns_description_files/filelist.xml">
<!--table
	{mso-displayed-decimal-separator:"\.";
	mso-displayed-thousand-separator:"\,";}
.xl157315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:bottom;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl657315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl667315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl677315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:right;
	vertical-align:bottom;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl687315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
.xl697315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:right;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl707315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl717315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
.xl727315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:700;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:center;
	vertical-align:middle;
	border:.5pt solid windowtext;
	background:#D9E1F2;
	mso-pattern:black none;
	white-space:nowrap;}
.xl737315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:700;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:center;
	vertical-align:middle;
	border:.5pt solid windowtext;
	background:#D9E1F2;
	mso-pattern:black none;
	white-space:nowrap;}
.xl747315
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:700;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:center;
	vertical-align:middle;
	border:.5pt solid windowtext;
	background:#D9E1F2;
	mso-pattern:black none;
	white-space:normal;}
-->
</head>

<body>
<!--[if !excel]>&nbsp;&nbsp;<![endif]-->
<!--The following information was generated by Microsoft Excel's Publish as Web
Page wizard.-->
<!--If the same item is republished from Excel, all information between the DIV
tags will be replaced.-->
<!----------------------------->
<!--START OF OUTPUT FROM EXCEL PUBLISH AS WEB PAGE WIZARD -->
<!----------------------------->

<div id="columns_description_7315" align=center x:publishsource="Excel">

<table border=0 cellpadding=0 cellspacing=0 width=663 style='border-collapse:
 collapse;table-layout:fixed;width:497pt'>
 <col width=129 style='mso-width-source:userset;mso-width-alt:4403;width:97pt'>
 <col class=xl677315 width=28 style='mso-width-source:userset;mso-width-alt:
 955;width:21pt'>
 <col width=225 style='mso-width-source:userset;mso-width-alt:7680;width:169pt'>
 <col width=48 style='mso-width-source:userset;mso-width-alt:1638;width:36pt'>
 <col class=xl667315 width=120 style='mso-width-source:userset;mso-width-alt:
 4078;width:90pt'>
 <col class=xl687315 width=113 style='mso-width-source:userset;mso-width-alt:
 3840;width:84pt'>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl727315 width=129 style='height:28.5pt;width:97pt'>Dataset</td>
  <td class=xl737315 width=28 style='border-left:none;width:21pt'>#</td>
  <td class=xl727315 width=225 style='border-left:none;width:169pt'>Column</td>
  <td class=xl727315 width=48 style='border-left:none;width:36pt'>Dtype</td>
  <td class=xl727315 width=120 style='border-left:none;width:90pt'>Group</td>
  <td class=xl747315 width=113 style='border-left:none;width:84pt'>Group
  Description</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>0</td>
  <td class=xl657315 style='border-top:none;border-left:none'>SK_ID_CURR</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_id</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Identification</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>1</td>
  <td class=xl657315 style='border-top:none;border-left:none'>TARGET</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_target</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Target</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>2</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_CONTRACT_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_contract</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Contract Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>3</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CODE_GENDER</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=4 class=xl707315 style='border-top:none'>appl_pers</td>
  <td rowspan=4 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Personal-I Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>4</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_OWN_CAR</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>5</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_OWN_REALTY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>6</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CNT_CHILDREN</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>7</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_INCOME_TOTAL</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=4 class=xl707315 style='border-top:none'>appl_contract</td>
  <td rowspan=4 class=xl717315 width=113 style='border-top:none;width:84pt'>Contract
  Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>8</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_CREDIT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>9</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_ANNUITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>10</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_GOODS_PRICE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>11</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_TYPE_SUITE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=5 class=xl707315 style='border-top:none'>appl_pers_stts</td>
  <td rowspan=5 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Status Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>12</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_INCOME_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>13</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_EDUCATION_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>14</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_FAMILY_STATUS</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>15</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_HOUSING_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>16</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REGION_POPULATION_RELATIVE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_regn_ratg</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Client�s Region Rating</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>17</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_BIRTH</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=4 class=xl707315 style='border-top:none'>appl_pers_days</td>
  <td rowspan=4 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Personal-II (Days Relative)</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>18</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_EMPLOYED</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>19</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_REGISTRATION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>20</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_ID_PUBLISH</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>21</td>
  <td class=xl657315 style='border-top:none;border-left:none'>OWN_CAR_AGE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_pers</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Client�s Personal-I Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>22</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_MOBIL</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=6 class=xl707315 style='border-top:none'>appl_pers_flag</td>
  <td rowspan=6 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Personal-III (Flags)</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>23</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_EMP_PHONE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>24</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_WORK_PHONE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>25</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_CONT_MOBILE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>26</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_PHONE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>27</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_EMAIL</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>28</td>
  <td class=xl657315 style='border-top:none;border-left:none'>OCCUPATION_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>appl_pers</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Personal-I Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>29</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CNT_FAM_MEMBERS</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>30</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REGION_RATING_CLIENT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>appl_regn_ratg</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Region Rating</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>31</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REGION_RATING_CLIENT_W_CITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>32</td>
  <td class=xl657315 style='border-top:none;border-left:none'>WEEKDAY_APPR_PROCESS_START</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>appl_strt</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Application
  Start On</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>33</td>
  <td class=xl657315 style='border-top:none;border-left:none'>HOUR_APPR_PROCESS_START</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>34</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REG_REGION_NOT_LIVE_REGION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=6 class=xl707315 style='border-top:none'>appl_regn_mtch</td>
  <td rowspan=6 class=xl717315 width=113 style='border-top:none;width:84pt'>Client�s
  Region Information Matching</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>35</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REG_REGION_NOT_WORK_REGION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>36</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVE_REGION_NOT_WORK_REGION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>37</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REG_CITY_NOT_LIVE_CITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>38</td>
  <td class=xl657315 style='border-top:none;border-left:none'>REG_CITY_NOT_WORK_CITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>39</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVE_CITY_NOT_WORK_CITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>40</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ORGANIZATION_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_pers_stts</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Client�s Status Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>41</td>
  <td class=xl657315 style='border-top:none;border-left:none'>EXT_SOURCE_1</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=3 class=xl707315 style='border-top:none'>appl_extn_ratg</td>
  <td rowspan=3 class=xl717315 width=113 style='border-top:none;width:84pt'>External
  Source Ratings</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>42</td>
  <td class=xl657315 style='border-top:none;border-left:none'>EXT_SOURCE_2</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>43</td>
  <td class=xl657315 style='border-top:none;border-left:none'>EXT_SOURCE_3</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>44</td>
  <td class=xl657315 style='border-top:none;border-left:none'>APARTMENTS_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=14 class=xl707315 style='border-top:none'>appl_buld_avg</td>
  <td rowspan=14 class=xl717315 width=113 style='border-top:none;width:84pt'>Normalized
  average indices about building</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>45</td>
  <td class=xl657315 style='border-top:none;border-left:none'>BASEMENTAREA_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>46</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BEGINEXPLUATATION_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>47</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BUILD_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>48</td>
  <td class=xl657315 style='border-top:none;border-left:none'>COMMONAREA_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>49</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ELEVATORS_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>50</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ENTRANCES_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>51</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMAX_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>52</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMIN_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>53</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LANDAREA_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>54</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAPARTMENTS_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>55</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAREA_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>56</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAPARTMENTS_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>57</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAREA_AVG</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>58</td>
  <td class=xl657315 style='border-top:none;border-left:none'>APARTMENTS_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=14 class=xl707315 style='border-top:none'>appl_buld_mode</td>
  <td rowspan=14 class=xl717315 width=113 style='border-top:none;width:84pt'>Normalized
  mode indices about building</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>59</td>
  <td class=xl657315 style='border-top:none;border-left:none'>BASEMENTAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>60</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BEGINEXPLUATATION_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>61</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BUILD_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>62</td>
  <td class=xl657315 style='border-top:none;border-left:none'>COMMONAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>63</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ELEVATORS_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>64</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ENTRANCES_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>65</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMAX_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>66</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMIN_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>67</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LANDAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>68</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAPARTMENTS_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>69</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>70</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAPARTMENTS_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>71</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>72</td>
  <td class=xl657315 style='border-top:none;border-left:none'>APARTMENTS_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=14 class=xl707315 style='border-top:none'>appl_buld_medi</td>
  <td rowspan=14 class=xl717315 width=113 style='border-top:none;width:84pt'>Normalized
  median indices about building</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>73</td>
  <td class=xl657315 style='border-top:none;border-left:none'>BASEMENTAREA_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>74</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BEGINEXPLUATATION_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>75</td>
  <td class=xl657315 style='border-top:none;border-left:none'>YEARS_BUILD_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>76</td>
  <td class=xl657315 style='border-top:none;border-left:none'>COMMONAREA_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>77</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ELEVATORS_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>78</td>
  <td class=xl657315 style='border-top:none;border-left:none'>ENTRANCES_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>79</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMAX_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>80</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLOORSMIN_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>81</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LANDAREA_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>82</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAPARTMENTS_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>83</td>
  <td class=xl657315 style='border-top:none;border-left:none'>LIVINGAREA_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>84</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAPARTMENTS_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>85</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NONLIVINGAREA_MEDI</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>86</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FONDKAPREMONT_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=5 class=xl707315 style='border-top:none'>appl_buld_mode_2</td>
  <td rowspan=5 class=xl717315 width=113 style='border-top:none;width:84pt'>Normalized
  mode indices about building-II</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>87</td>
  <td class=xl657315 style='border-top:none;border-left:none'>HOUSETYPE_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>88</td>
  <td class=xl657315 style='border-top:none;border-left:none'>TOTALAREA_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>89</td>
  <td class=xl657315 style='border-top:none;border-left:none'>WALLSMATERIAL_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>90</td>
  <td class=xl657315 style='border-top:none;border-left:none'>EMERGENCYSTATE_MODE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>91</td>
  <td class=xl657315 style='border-top:none;border-left:none'>OBS_30_CNT_SOCIAL_CIRCLE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=4 class=xl707315 style='border-top:none'>appl_pers_obsr</td>
  <td rowspan=4 class=xl717315 width=113 style='border-top:none;width:84pt'>Observation
  of client's social surroundings</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>92</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DEF_30_CNT_SOCIAL_CIRCLE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>93</td>
  <td class=xl657315 style='border-top:none;border-left:none'>OBS_60_CNT_SOCIAL_CIRCLE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>94</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DEF_60_CNT_SOCIAL_CIRCLE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>95</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_LAST_PHONE_CHANGE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>appl_pers_days</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Client�s Personal-II (Days Relative)</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>96</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_2</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=20 class=xl707315 style='border-top:none'>appl_docu_flag</td>
  <td rowspan=20 class=xl717315 width=113 style='border-top:none;width:84pt'>Flags
  for documents submitted by client</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>97</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_3</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>98</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_4</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>99</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_5</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>100</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_6</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>101</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_7</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>102</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_8</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>103</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_9</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>104</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_10</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>105</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_11</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>106</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_12</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>107</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_13</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>108</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_14</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>109</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_15</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>110</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_16</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>111</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_17</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>112</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_18</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>113</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_19</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>114</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_20</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>115</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_DOCUMENT_21</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>116</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_HOUR</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=6 class=xl707315 style='border-top:none'>appl_bure_eqry</td>
  <td rowspan=6 class=xl717315 width=113 style='border-top:none;width:84pt'>Number
  of enquiries to Credit Bureau about the client</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>117</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_DAY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>118</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_WEEK</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>119</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_MON</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>120</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_QRT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>application_data</td>
  <td class=xl697315 style='border-top:none;border-left:none'>121</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_YEAR</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>&nbsp;</td>
  <td class=xl657315 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl657315 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl657315 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl657315 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl657315 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>0</td>
  <td class=xl657315 style='border-top:none;border-left:none'>SK_ID_PREV</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>prev_id</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Identification</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>1</td>
  <td class=xl657315 style='border-top:none;border-left:none'>SK_ID_CURR</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>2</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_CONTRACT_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>prev_comm</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Common
  with application data</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>3</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_ANNUITY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>4</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_APPLICATION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_amnt</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Amount Information</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>5</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_CREDIT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_comm</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Common with application data</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>6</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_DOWN_PAYMENT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_amnt</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Amount Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>7</td>
  <td class=xl657315 style='border-top:none;border-left:none'>AMT_GOODS_PRICE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=3 class=xl707315 style='border-top:none'>prev_comm</td>
  <td rowspan=3 class=xl717315 width=113 style='border-top:none;width:84pt'>Common
  with application data</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>8</td>
  <td class=xl657315 style='border-top:none;border-left:none'>WEEKDAY_APPR_PROCESS_START</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>9</td>
  <td class=xl657315 style='border-top:none;border-left:none'>HOUR_APPR_PROCESS_START</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>10</td>
  <td class=xl657315 style='border-top:none;border-left:none'>FLAG_LAST_APPL_PER_CONTRACT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>prev_flag</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Last
  Application Flags</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>11</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NFLAG_LAST_APPL_IN_DAY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>12</td>
  <td class=xl657315 style='border-top:none;border-left:none'>RATE_DOWN_PAYMENT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=3 class=xl707315 style='border-top:none'>prev_rate</td>
  <td rowspan=3 class=xl717315 width=113 style='border-top:none;width:84pt'>Downpayment
  and Rate</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>13</td>
  <td class=xl657315 style='border-top:none;border-left:none'>RATE_INTEREST_PRIMARY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>14</td>
  <td class=xl657315 style='border-top:none;border-left:none'>RATE_INTEREST_PRIVILEGED</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>15</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_CASH_LOAN_PURPOSE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_purp</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Loan Purpose</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>16</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_CONTRACT_STATUS</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=4 class=xl707315 style='border-top:none'>prev_contract</td>
  <td rowspan=4 class=xl717315 width=113 style='border-top:none;width:84pt'>Contract
  Information</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>17</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_DECISION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>18</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_PAYMENT_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>19</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CODE_REJECT_REASON</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=38 style='height:28.5pt'>
  <td height=38 class=xl657315 style='height:28.5pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>20</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_TYPE_SUITE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_comm</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Common with application data</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>21</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_CLIENT_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td rowspan=7 class=xl707315 style='border-top:none'>prev_purchase</td>
  <td rowspan=7 class=xl717315 width=113 style='border-top:none;width:84pt'>Purchase
  Detail</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>22</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_GOODS_CATEGORY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>23</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_PORTFOLIO</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>24</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_PRODUCT_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>25</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CHANNEL_TYPE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>26</td>
  <td class=xl657315 style='border-top:none;border-left:none'>SELLERPLACE_AREA</td>
  <td class=xl657315 style='border-top:none;border-left:none'>int64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>27</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_SELLER_INDUSTRY</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>28</td>
  <td class=xl657315 style='border-top:none;border-left:none'>CNT_PAYMENT</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=2 class=xl707315 style='border-top:none'>prev_payment</td>
  <td rowspan=2 class=xl717315 width=113 style='border-top:none;width:84pt'>Payment
  and Yield</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>29</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NAME_YIELD_GROUP</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>30</td>
  <td class=xl657315 style='border-top:none;border-left:none'>PRODUCT_COMBINATION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>object</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_purchase</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Purchase Detail</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>31</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_FIRST_DRAWING</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td rowspan=5 class=xl707315 style='border-top:none'>prev_days</td>
  <td rowspan=5 class=xl717315 width=113 style='border-top:none;width:84pt'>Important
  Dates Relative</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>32</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_FIRST_DUE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>33</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_LAST_DUE_1ST_VERSION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>34</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_LAST_DUE</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>35</td>
  <td class=xl657315 style='border-top:none;border-left:none'>DAYS_TERMINATION</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
 </tr>
 <tr height=19 style='height:14.25pt'>
  <td height=19 class=xl657315 style='height:14.25pt;border-top:none'>previous_application</td>
  <td class=xl697315 style='border-top:none;border-left:none'>36</td>
  <td class=xl657315 style='border-top:none;border-left:none'>NFLAG_INSURED_ON_APPROVAL</td>
  <td class=xl657315 style='border-top:none;border-left:none'>float64</td>
  <td class=xl707315 style='border-top:none;border-left:none'>prev_insu_flag</td>
  <td class=xl717315 width=113 style='border-top:none;border-left:none;
  width:84pt'>Insurance</td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=129 style='width:97pt'></td>
  <td width=28 style='width:21pt'></td>
  <td width=225 style='width:169pt'></td>
  <td width=48 style='width:36pt'></td>
  <td width=120 style='width:90pt'></td>
  <td width=113 style='width:84pt'></td>
 </tr>
 <![endif]>
</table>

</div>


<!----------------------------->
<!--END OF OUTPUT FROM EXCEL PUBLISH AS WEB PAGE WIZARD-->
<!----------------------------->
</body>

</html>


## Column Description - Distribution Anomaly / Relevance and Action Taken

<html xmlns:o="urn:schemas-microsoft-com:office:office"
xmlns:x="urn:schemas-microsoft-com:office:excel"
xmlns="http://www.w3.org/TR/REC-html40">

<head>
<meta http-equiv=Content-Type content="text/html; charset=windows-1252">
<meta name=ProgId content=Excel.Sheet>
<meta name=Generator content="Microsoft Excel 15">
<link rel=File-List href="columns_description_2_files/filelist.xml">

<!--table
	{mso-displayed-decimal-separator:"\.";
	mso-displayed-thousand-separator:"\,";}
.xl153295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:bottom;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl653295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl663295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:bottom;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl673295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
.xl683295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl693295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:12.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:general;
	vertical-align:bottom;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl703295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:12.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl713295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:12.0pt;
	font-weight:700;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:center;
	vertical-align:middle;
	border:.5pt solid windowtext;
	background:#D9E1F2;
	mso-pattern:black none;
	white-space:nowrap;}
.xl723295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:700;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:center;
	vertical-align:bottom;
	border:.5pt solid windowtext;
	background:#D9E1F2;
	mso-pattern:black none;
	white-space:nowrap;}
.xl733295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:.5pt solid windowtext;
	border-right:.5pt solid windowtext;
	border-bottom:none;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl743295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:none;
	border-right:.5pt solid windowtext;
	border-bottom:none;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl753295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:none;
	border-right:.5pt solid windowtext;
	border-bottom:.5pt solid windowtext;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:nowrap;}
.xl763295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:.5pt solid windowtext;
	border-right:.5pt solid windowtext;
	border-bottom:none;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
.xl773295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:none;
	border-right:.5pt solid windowtext;
	border-bottom:none;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
.xl783295
	{padding-top:1px;
	padding-right:1px;
	padding-left:1px;
	mso-ignore:padding;
	color:black;
	font-size:11.0pt;
	font-weight:400;
	font-style:normal;
	text-decoration:none;
	font-family:Calibri, sans-serif;
	mso-font-charset:0;
	mso-number-format:General;
	text-align:left;
	vertical-align:middle;
	border-top:none;
	border-right:.5pt solid windowtext;
	border-bottom:.5pt solid windowtext;
	border-left:.5pt solid windowtext;
	mso-background-source:auto;
	mso-pattern:auto;
	white-space:normal;}
-->
</head>

<body>
<!--[if !excel]>&nbsp;&nbsp;<![endif]-->
<!--The following information was generated by Microsoft Excel's Publish as Web
Page wizard.-->
<!--If the same item is republished from Excel, all information between the DIV
tags will be replaced.-->
<!----------------------------->
<!--START OF OUTPUT FROM EXCEL PUBLISH AS WEB PAGE WIZARD -->
<!----------------------------->

<div id="columns_description_3295" align=center x:publishsource="Excel">

<table border=0 cellpadding=0 cellspacing=0 width=714 style='border-collapse:
 collapse;table-layout:fixed;width:535pt'>
 <col class=xl693295 width=22 style='mso-width-source:userset;mso-width-alt:
 733;width:16pt'>
 <col width=217 style='mso-width-source:userset;mso-width-alt:7406;width:163pt'>
 <col width=48 style='mso-width-source:userset;mso-width-alt:1638;width:36pt'>
 <col width=79 style='mso-width-source:userset;mso-width-alt:2696;width:59pt'>
 <col width=72 style='mso-width-source:userset;mso-width-alt:2457;width:54pt'>
 <col width=227 style='mso-width-source:userset;mso-width-alt:7731;width:170pt'>
 <col width=49 style='mso-width-source:userset;mso-width-alt:1672;width:37pt'>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl713295 width=22 style='height:15.75pt;width:16pt'>#</td>
  <td class=xl723295 width=217 style='border-left:none;width:163pt'>Column</td>
  <td class=xl723295 width=48 style='border-left:none;width:36pt'>Dtype</td>
  <td class=xl723295 width=79 style='border-left:none;width:59pt'>Type of data</td>
  <td class=xl723295 width=72 style='border-left:none;width:54pt'>Subtype</td>
  <td class=xl723295 width=227 style='border-left:none;width:170pt'>Distribution
  Anomaly / Relevance</td>
  <td class=xl723295 width=49 style='border-left:none;width:37pt'>Action</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>0</td>
  <td class=xl663295 style='border-top:none;border-left:none'>SK_ID_CURR</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>1</td>
  <td class=xl663295 style='border-top:none;border-left:none'>TARGET</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>2</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_CONTRACT_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>3</td>
  <td class=xl663295 style='border-top:none;border-left:none'>CODE_GENDER</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>4</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_OWN_CAR</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>5</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_OWN_REALTY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>6</td>
  <td class=xl663295 style='border-top:none;border-left:none'>CNT_CHILDREN</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>7</td>
  <td class=xl663295 style='border-top:none;border-left:none'>AMT_INCOME_TOTAL</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>8</td>
  <td class=xl663295 style='border-top:none;border-left:none'>AMT_CREDIT</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>9</td>
  <td class=xl663295 style='border-top:none;border-left:none'>AMT_ANNUITY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>10</td>
  <td class=xl663295 style='border-top:none;border-left:none'>AMT_GOODS_PRICE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>11</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_TYPE_SUITE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>12</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_INCOME_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>13</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_EDUCATION_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Ordinal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>14</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_FAMILY_STATUS</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>15</td>
  <td class=xl663295 style='border-top:none;border-left:none'>NAME_HOUSING_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>16</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REGION_POPULATION_RELATIVE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Relative Field</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>17</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DAYS_BIRTH</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>YEARS_BIRTH</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Change</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>18</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DAYS_EMPLOYED</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>MONTHS_EMPLOYED</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Change</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>19</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DAYS_REGISTRATION</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>20</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DAYS_ID_PUBLISH</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>21</td>
  <td class=xl663295 style='border-top:none;border-left:none'>OWN_CAR_AGE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>22</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_MOBIL</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>All 1</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Drop</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>23</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_EMP_PHONE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>1 for more than
  81%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>24</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_WORK_PHONE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  80%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>25</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_CONT_MOBILE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>1 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>26</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_PHONE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  71%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>27</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_EMAIL</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  94%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>28</td>
  <td class=xl663295 style='border-top:none;border-left:none'>OCCUPATION_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>29</td>
  <td class=xl663295 style='border-top:none;border-left:none'>CNT_FAM_MEMBERS</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>30</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REGION_RATING_CLIENT</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>31</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REGION_RATING_CLIENT_W_CITY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>32</td>
  <td class=xl663295 style='border-top:none;border-left:none'>WEEKDAY_APPR_PROCESS_START</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Ordinal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>33</td>
  <td class=xl663295 style='border-top:none;border-left:none'>HOUR_APPR_PROCESS_START</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Ordinal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>34</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REG_REGION_NOT_LIVE_REGION</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  98%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>35</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REG_REGION_NOT_WORK_REGION</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  94%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>36</td>
  <td class=xl663295 style='border-top:none;border-left:none'>LIVE_REGION_NOT_WORK_REGION</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  95%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>37</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REG_CITY_NOT_LIVE_CITY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  92%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>38</td>
  <td class=xl663295 style='border-top:none;border-left:none'>REG_CITY_NOT_WORK_CITY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  76%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>39</td>
  <td class=xl663295 style='border-top:none;border-left:none'>LIVE_CITY_NOT_WORK_CITY</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  82%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>40</td>
  <td class=xl663295 style='border-top:none;border-left:none'>ORGANIZATION_TYPE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>object</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=33 style='mso-height-source:userset;height:24.85pt'>
  <td height=33 class=xl703295 style='height:24.85pt;border-top:none'>41</td>
  <td class=xl653295 style='border-top:none;border-left:none'>EXT_SOURCE_1</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Continuous</td>
  <td rowspan=3 class=xl763295 width=227 style='border-bottom:.5pt solid black;
  border-top:none;width:170pt'>As each of the columns EXT_SOURCE_1,
  EXT_SOURCE_2 and EXT_SOURCE_3 have missing value, so a new column with mean
  of all 3 external source rating is created.</td>
  <td rowspan=3 class=xl733295 style='border-bottom:.5pt solid black;
  border-top:none'>Change</td>
 </tr>
 <tr height=33 style='mso-height-source:userset;height:24.85pt'>
  <td height=33 class=xl703295 style='height:24.85pt;border-top:none'>42</td>
  <td class=xl653295 style='border-top:none;border-left:none'>EXT_SOURCE_2</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Continuous</td>
 </tr>
 <tr height=33 style='mso-height-source:userset;height:24.85pt'>
  <td height=33 class=xl703295 style='height:24.85pt;border-top:none'>43</td>
  <td class=xl653295 style='border-top:none;border-left:none'>EXT_SOURCE_3</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Continuous</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>44</td>
  <td class=xl663295 style='border-top:none;border-left:none'>OBS_30_CNT_SOCIAL_CIRCLE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>45</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DEF_30_CNT_SOCIAL_CIRCLE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>46</td>
  <td class=xl663295 style='border-top:none;border-left:none'>OBS_60_CNT_SOCIAL_CIRCLE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>47</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DEF_60_CNT_SOCIAL_CIRCLE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Discrete</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>48</td>
  <td class=xl663295 style='border-top:none;border-left:none'>DAYS_LAST_PHONE_CHANGE</td>
  <td class=xl663295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Numerical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Continuous</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
  <td class=xl663295 style='border-top:none;border-left:none'>&nbsp;</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>49</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_2</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>50</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_3</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>1 for more than
  71%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>51</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_4</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>52</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_5</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  98%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>53</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_6</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  91%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>54</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_7</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>55</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_8</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  91%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>56</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_9</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>57</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_10</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>58</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_11</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>59</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_12</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>60</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_13</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>61</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_14</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>62</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_15</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>63</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_16</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_17</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>65</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_18</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>66</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_19</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>67</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_20</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=21 style='height:15.75pt'>
  <td height=21 class=xl703295 style='height:15.75pt;border-top:none'>68</td>
  <td class=xl663295 style='border-top:none;border-left:none'>FLAG_DOCUMENT_21</td>
  <td class=xl663295 style='border-top:none;border-left:none'>int64</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Nominal</td>
  <td class=xl663295 style='border-top:none;border-left:none'>0 for more than
  99%</td>
  <td class=xl663295 style='border-top:none;border-left:none'>Skip</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>69</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_HOUR</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
  <td rowspan=6 class=xl673295 width=227 style='border-top:none;width:170pt'>These
  columns contains, number of enquiries to Credit Bureau about the client
  during particular duration before application. Understanding the dataset,
  number of enquiries upto 1 month back can be analyzed. As values are
  exclusive, suming upto month to find new column.</td>
  <td rowspan=6 class=xl683295 style='border-top:none'>Change</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>70</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_DAY</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>71</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_WEEK</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>72</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_MON</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>73</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_QRT</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
 </tr>
 <tr height=26 style='mso-height-source:userset;height:19.5pt'>
  <td height=26 class=xl703295 style='height:19.5pt;border-top:none'>74</td>
  <td class=xl653295 style='border-top:none;border-left:none'>AMT_REQ_CREDIT_BUREAU_YEAR</td>
  <td class=xl653295 style='border-top:none;border-left:none'>float64</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Categorical</td>
  <td class=xl653295 style='border-top:none;border-left:none'>Nominal</td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=22 style='width:16pt'></td>
  <td width=217 style='width:163pt'></td>
  <td width=48 style='width:36pt'></td>
  <td width=79 style='width:59pt'></td>
  <td width=72 style='width:54pt'></td>
  <td width=227 style='width:170pt'></td>
  <td width=49 style='width:37pt'></td>
 </tr>
 <![endif]>
</table>

</div>


<!----------------------------->
<!--END OF OUTPUT FROM EXCEL PUBLISH AS WEB PAGE WIZARD-->
<!----------------------------->
</body>

</html>



# Conclusion
## Portfolio and Risk Assessment (Driving Factors)
![image](https://github.com/user-attachments/assets/7d67f8d7-5fa8-4f7b-8d15-961e37107241)

## Portfolio of Clients
### That are likely to have no Difficulty with Repayment
- Clients who are ‘Students’ or ‘Businessmen’.
- Unemployed clients with the family status of ‘Civil marriage’ or ‘Separated’.
- Clients with organization type as ‘Trade: type 4’.
- Clients with an average rating of three external sources EXT_SOURCE > 0.7.
- Clients who are employed for more than 6000 days.
- Unemployed and client with income type ‘Maternity leave’.
- Male clients with ‘Academic degree’.
- Clients with ‘Academic degree’ and Accompanied (not ‘Unaccompanied’) have no Payment Difficulties.
- Clients with ‘Lower secondary’ and categorized as part of a ‘Group of people’ have no Payment Difficulties. 
- ‘Repeater’ clients have the highest Approval in terms of count in all categories.
- ‘New’ clients have the highest Approval in terms of percentage in the same category.
- The clients with larger relative last due and termination of previous applications.

### Proposed action for clients that are likely to default
- The clients that fall under these categories are risky candidates, are following actions may be taken: -
  - Denying the loan (if the client falls under multiple categories as mentioned below)
  - Reducing the amount of loan
  - Lending (to risky applicants) at a higher interest rate, etc
### That are likely to default
- Clients with an average rating of three external sources EXT_SOURCE < 0.3.
- Clients with ‘Maternity Leave’ income and own car.
- Male HR staff with higher Credit Amounts (above 12 lakh).
- Unemployed and clients with income type ‘Maternity leave’ have payment difficulty in repayment of ‘Cash loans’.

