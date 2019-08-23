# WTP Business

## ?? **Product Permissions**

- User is allowed to create unlimited number of products.
- User is allowed to see other user's product (_but not edit/remove them_).
- An user can assign one or more other user (_in same company_) to have **edit access** to his/her products.
- An user can transfer his product's **ownership** to other user.
- An company can have one or more `Super User`, which is the same as normal user but **can edit/delete all products** in its organization.

- Permission Overview:

  | Role       | View | Edit | Delete | Assign Permissions | Transfer Ownership |
  |------------|------|------|--------|--------------------|--------------------|
  | Owner      | ??    | ??    | ??      | ??                  | ??                  |
  | Super User | ??    | ??    | ??      | ?                  | ?                  |
  | Allowed    | ??    | ??    | ?      | ?                  | ?                  |
  | Denied     | ??    | ?    | ?      | ?                  | ?                  |
  | Other      | ??    | ?    | ?      | ?                  | ?                  |

  - `Allowed`: The user that got edit access issued from product owner.
  - `Denied`: The user that got edit access revoked frorm product owner.
  
## ?? **Chart Permissions**
- A user is allowed to create, edit, and delete its own chart presets.
- A user can view chart presets of other users in the same company.
- A user with chart permission is allowed to edit chart presets of other users in the same company.
- A supper user is allowed to edit, delete chart preset of other users in the same company.
- Only Admin user can create, edit, delete standard presets.

#### Permission Overview:
  | Role       | View | Edit | Delete | 
  |------------|------|------|--------|
  | Owner      |  ??   | ??    | ??   | 
  | Super User | ??    | ??    | ??   | 
  | Allowed    | ??    | ??    | ?   | 
  | Denied     | ??    | ?    | ?   |

## ?? **Product Component**

- A product can be consider `Completed` if it have enough info:
  - **Name**
  - **Industry**
  - One or more **Commodities**/**Components**
  - **Total weight** > 0 _(Total weight is sum of commodities and components weight)_

- Only `Completed` product can be add as a component of another product
- While added as a component, it must remain `Completed`
- When editing a product, should validate and prevent user from making it in-`Completed`

## Commodities

- Commodities data is read-only and got pre-populated by sysadmin

## ?? **Show My Product**
- Only show products of the current user.
## ?? **Import Product**
- Users can import many products by using the Import Function.
- A template can be downloaded to fill in products' information.
## ?? **Export Product**
- The current user can export all products in the company.
- The current user can export its filtered products.
## ?? **Search a Product (Adcanced Search)**
- Users have the posibility to search products by any characteristic of a products. 
- Users can erase all the filtering criteria by Clicking on the button **Clear Filter** in the result screen.
- Users can erase all the filtering criteria by Clicking on the button **Reset** in the advanced search pop up.</br>
*Please view the backlog item to know more about it.* https://buynamics.visualstudio.com/WTP/_workitems/edit/716
## ?? **Compare Products**
- This function offers users the possibility to export to excel and compare multiple products.
- A compared product must be a [`completed`](#completed) product.</br>
  *Please view the backlog item to know more about it.* https://buynamics.visualstudio.com/WTP/_workitems/edit/3826</br>
There are 2 ways to use the **Compare/ Export** function:
  ### Export From The Product List
-  Compared product(s) are selected in the product grip before executing `Compared/Export`.
-  `Include buying price column` button is only visible when buying prices are available in at least one product.
-  Users can choose whether buying price column is included in the excel export file or not.
-  Users can limit the time period of the product prices by selecting the `time frame` (*What is the time frame for your comparision?*). The default is 3 years, counting from the latest commodity price date.
-  Users can choose which price of the product's wtp cost prices compared to buying prices to show in the excel file by selecting the price mode (`average`, `highest`, `lowest`, and `the latest`).
-  If costs/ shackles are available, they are included in the excel file.
-  Currencies are based on each product's currency.
      ### Export in WTP Screen
-  Only 1 product is in the excel file.
-  `Export to Excel` button is visible in an existing product.
-  Currency is based on the currency chosen in the product.
     ### Information  should be involved in the excel file
- Product Name
- Currency
- Country
- Industry
- Cost Name
- % of sale
- Values based on material costs
- Values based on buying price
- Costs/ shakles
## ?? **Completeness Percentage**
### Total product completeness in the product list
- The completeness column in the product grid shows how many percents a product's characteristics are filled.
- The completeness coulumn showns what information (characteristics) is(are) still missing when users hover on a specific percent of a product in the list.</br>
- Color of the completeness:
  - Red: if the completeness in the grid is in red, there's no enough info to create a chart. ( Lacking commodity/component with net weight)
  - Black: if the completeness in the grid is in black, there's not enogh info to break down the production cost (industry data) but it's still possible to create a chart.
  - Green: if the completeness in the grid is in green, it's possible to create a chart and break down the production cost (industry data).
### Total product completeness in the product detail page
- The completeness percentage is the same as the completeness percentage in the product list.
### Completeness percent in the product detail section
- The section `1. Product detail` makes up `70 %` of the total product completeness.
- Here are the detail percents of the section 1:</br>
  | Field      | Percent |
  |------------|---------|
  | Country     |  10 %  | 
  | Industry    | 20 %  | 
  | Supplier    | 5  %  | 
  | Buying Price| 10 % |
  | Annual Quantity    |    10% |
  | Tag| 1%|
  | Description| 1%|
  | Article Number| 5%|
  | Article no Supplier|1%|
  | Unit of Measure| 5%|
  | Image| 2%|

- The percentage formulas: **`(Field (%) / 70 % )*100`**</br>
For example, if country is filled, the percent of `1. Product detail` is (10/70)*100 ~ 14%, and the product total completeness is 10%.
- The color rule for this section:
   | Field      | Percent |
  |------------|---------|
  | Green     |  >=75 %  | 
  | Black | >=50|
  | Red| <50|  

### Completeness percent in the comnodity and component weight section
- The section `2. Commodity and Component Weights` makes up `30 %` of the total product completeness.
- Here are the detail percents of the section 2:</br>
  | Field      | Percent |
  |------------|---------|
  | Commodity/ component     |  15 %  | 
  | Net Weight    | 15 %  |
- The percentage formulas: **`(Field (%) / 30 % )*100`**</br>
For example, if the 
