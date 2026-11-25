# Step-by-Step Guide to Build Blinkit_Sales_Dashboard.pbix in Power BI Desktop

Follow these exact steps to create your `.pbix` file :

## Step 1: Load Raw Data & Clean in Power Query
1. Open **Power BI Desktop** -> click **Get Data** -> **Text/CSV** -> select `blinkit_sales_raw.csv`.
2. Click **Transform Data** to open Power Query Editor.
3. Either apply the steps manually OR click **Home -> Advanced Editor** and paste the code from `power_query_m_script.txt` (update the file path in line 3):
   - Standardizes `Item_Fat_Content` (`LF`, `low fat` -> `Low Fat`; `reg` -> `Regular`).
   - Replaces missing `Item_Weight` values with the column average.
   - Ensures proper numeric and text data types and removes duplicates.
4. Click **Close & Apply**.

## Step 2: Create DAX Measures
In Report View, click **New Measure** and create each measure from `dax_measures.txt`:
- `Total Sales`
- `Average Sales`
- `No of Items`
- `Average Rating`
- `Sales % of Total`

## Step 3: Build Dashboard Visuals
Use a clean Blinkit color theme: Yellow (`#F8CB46`), Green (`#0C831F`), and Dark Slate (`#1E293B`).
1. **Top Row (4 KPI Cards)**: Place 4 Card visuals displaying `Total Sales`, `Average Sales`, `No of Items`, and `Average Rating`.
2. **Left Panel (3 Slicers)**: Add Slicer visuals for `Outlet_Location_Type`, `Outlet_Size`, and `Item_Type`.
3. **Visual 1 — Category-Wise Sales**: Clustered Bar Chart with `Item_Type` on Y-axis and `Total Sales` on X-axis.
4. **Visual 2 — Outlet-Wise Performance**: Clustered Column Chart with `Outlet_Type` on X-axis and `Total Sales` on Y-axis.
5. **Visual 3 — Sales by Outlet Size**: Donut Chart with `Outlet_Size` as Legend and `Total Sales` as Values.
6. **Visual 4 — Establishment Year Trend**: Area/Line Chart with `Outlet_Establishment_Year` on X-axis and `Total Sales` on Y-axis.

## Step 4: Save
Save the file as `Blinkit_Sales_Dashboard.pbix`.
