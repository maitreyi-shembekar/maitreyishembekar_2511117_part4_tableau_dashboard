# Part 4: Tableau Executive Dashboard & Data Storytelling

## Charts Selection

### 1. Sales Trend (Line Graph)
**What Question the Chart Answers:**  
"How do the sales and profits fluctuate month by month, and are we seeing positive (seasonal) growth?"

**Why the Chart Type is Appropriate:**  
Line charts are standard for continuous time-series data. We can identify trajectories, acceleration, and dips, which would not be possible in other graphs like bar charts or pie charts.

**Fields Used:**

**X-Axis:** Order Date (Month-Year continuous)

**Y-Axis:** Sales

**Tooltip:** Sum of Profits.

**Marks / Features:** Minimum and Maximum points highlighted, plus a Linear Trend Line.

**Design Principle Applied:**  
Instead of adding an additional second profit line onto the chart, profit data was added inside the Tooltip. This keeps the view clean while still giving the user the exact information when they hover over the line. Adding the Linear Trend Line gives an immediate look at the long-term direction of sales.

**Mistake Avoided:**  
The Visual Clutter / Dual-Axis Confusion Trap by stacking multiple lines or forcing two different y-axes onto one graph. By tracking only Sales on the main axis and highlighting the highest/lowest points, the chart remains clean and readable.
__________
### 2. Category Profitability (Horizontal Bar Grouped by Category)
**What Question the Chart Answers:**  
"Which specific product categories and sub-categories are carrying our profitability, and which ones are dragging down our efficiency?"

**Why the Chart Type is Appropriate:**  
A horizontal bar chart is ideal for categorical data. It allows text labels to be read comfortably and makes comparing long/short bar lengths very easy.

**Fields Used:**

**Rows (Y-Axis):** Category and Sub-Category (Nested hierarchy)

**Columns (X-Axis):** Profit (Determines length of the bars)

**Color / Label:** Profit Margin (%) is used to color gradient and text label is added to show sum of profit numbers.

**Design Principle Applied:**  
Bars are sorted descending by total profit within their parent categories to show the highest-value items at the top and the worst performers at the bottom.

**Mistake Avoided:**  
Misaligning Length with Value. Avoided using a pie chart or stacked. For 13 distinct sub-categories, a pie chart would be illegible, whereas a sorted horizontal bar chart handles high cardinality cleanly.
________
### 3. Discount vs. Profits (Scatter Plot)
**What Question the Chart Answers:**  
"What is the direct impact of the discounting strategy on net profits, and is there a point where discounting becomes financially toxic?"

**Why the Chart Type is Appropriate:**  
Scatter plots are the preferrable choice for showing correlation between two continuous numeric variables. By plotting individual points across both axes, it reveals distributions, clusters, outliers, and the mathematical direction of a relationship.

**Fields Used:**

**X-Axis:** Discount Percentage (Independent Variable)

**Y-Axis:** Profit (Dependent Variable)

**Detail:** Order ID to populate individual markers.

**Trend Line:** a linear regression trend line to map the correlation.

**Design Principle Applied:**  
Adding a linear trend line shows the viewer the collective weight of thousands of points instantly. In this case, the trend line goes downwards showing that profit decrease as discounts grow.

**Mistake Avoided:**  
If discounts and profits were plotted onto a simple bar chart, they would have been averaged out. This would cause operational reality of deep losses (like hitting a drop of -Rs. 17,800) would be hidden behind a misleading average.
_________
### 4. Shipping Performance (Stacked Bar Chart)
**What Question the Chart Answers:**  
"How frequently do our different shipping modes miss their delivery windows, and which shipping tier is responsible for the majority of our operational delays?"

**Why the Chart Type is Appropriate:**  
A stacked bar chart allows us to show two levels of information at once. The total length of the bar shows the volume of orders of each shipping mode, and the coloured internal segments show the proportion of delays within that mode.

**Fields Used:**

**Rows (Y-Axis):** Ship Mode

**Columns (X-Axis):** Distinct Count of Order ID

**Color:** Shipping Delay Bucket (e.g., Fast, Standard, Delayed, Severe Delay)

**Label:** Count of Order ID to display the numbers in the bars.

**Design Principle Applied:**  
Colouring the different buckets of shipping delay, allows for the executive to see the proportion of delays with respect to the other orders or total orders.

**Mistake Avoided:**  
The internal segments are stacked chronologically by speed (0-2 days up to 7+ days) rather than alphabetically. This maintains a logical timeline flow within each physical bar.
__________
### 5. Regional Performance (Choropleth Map)
**What Question the Chart Answers:**  
"How is our sales volume distributed geographically across the country, and are there specific states underperforming in market?"

**Why the Chart Type is Appropriate:**  
A choropleth map shows geographical boundaries to visualize data by regions.

**Fields Used:**

**Detail:** State (Geographic mapping), and Profit Margin (%)

**Color Fill:** Sales (Sequential color gradient where darker shades represent higher revenue volumes)

**Tooltip / Label:** Profit Margin (%) and Sales (Rs.) to provide detailed metrics.

**Design Principle Applied:**  
Using a single-hue like light blue to dark blue to represent sales volume. This allows the absolute the largest revenue generators (like Rajasthan) to coloured in a dark shade, while lower volume states remain faint.

**Mistake Avoided:**  
Avoided using a multi-colored rainbow palette (red, blue, yellow, green) to represent sales numbers. Rainbow coloring confuses quantitative scaling.