
# File Info

1. finalck.pdf - Code for manipulating datasets and visualizations.
2. Metrics Observations.pdf - Observations based on metrics outputted. This includes a section on optimum number of cooks per hour. 
3. Design doc for real time analytics.pdf - A design doc on designing real time analytics solution for CK.

# Assumptions about this exercise  

1. Assuming that price_per_unit in menu items dataset includes both fixed and variable cost. Also, the paid_per_unit is the total revenue for CK. This means the gross profit for each transaction is a simple subtraction of the two i.e. paid_per_unit minus price_per_unit
2. Food orders have peaks i.e. intervals of time when customer orders are high. We will assume that these duration are as follows - 
Breakfast: 7:30 am - 9:30 am
Lunch: 11:30 am - 1:30 pm
Dinner: 6:30 pm - 8:30 pm
Above assumptions for high order intervals is important because this is when CK needs to operate most efficiently without any hiccups. In some scenarios, this might mean needing a higher number of cooks to account for higher count of orders. 
3. No menu item is pre-cooked hence the duration noted is the actual duration to cook these items from scratch. 
4. I noticed that time in orders dataset is in UTC. For the simplicity of this exercise, I will convert this time to PST and make computations. 

# Questions for metrics & why they are important

I've included why for each of these questions to give additional context on why measuring these would be important.

# Business Intelligence Category: 

1. What is the average revenue during a day broken out by every hour? 
2. What is the average order count during a day broken out by every hour? 
The why for above two: These are general business metrics and help identify general pulse of the business and seasonal trends if any.

3. Which items sell most broken out by time of the day i.e lunch, breakfast and dinner (Note: both order count and revenue )? The why: If we assume the pareto rule is at play here, we can assume 80% of revenue comes from 20 % of menu items. We want to identify those items and ensure we are well prepared to deliver them in a timely manner. This also provides marketing opportunities like special discounts for repeat orders etc.

4. Which service provider is the source for most revenue (Note: revenue not order count)? The why: If we use the pareto rule of 80/20, 80 % of orders would come from a small set of delivery providers. I want to test that theory and if that holds up, we can provide preferential treatment to service provider(s) during peak hours and special events like superbowl etc. 

6. Which customers are the most profitable as noted by total revenue generated by them? The why: We want to provide incentives so these top customers continue using CK. Also, ask these customers what more they???d like to see (from menu and service standpoint) so we can better their experience using CK.

# Operational: 

7. Find the optimum number of parallel orders during peak hours i.e. breakfast, lunch and dinner. This optimum number is the number where we can ensure delivery of food items without the customer having to wait for extended durations. The why: This is an operational KPI and ensures we are operating within an acceptable SLA. Having a firm understanding of this KPI allows us to better prepare during expected peak order times and also during special events like superbowl etc. We can leverage this metric to provide accurate information on when the food item will be ready for delivery. 

Notes from CD - 
1. paid_per_unit is the amount that is eventually paid, while price_per_unit is the price originally set. Not cost vs revenue, but both are in the revenue category. 
2. Revenue, operation excellence are both great areas to dive in. You might also want to look into the eater section too.
3. It'd be useful to briefly discuss at the end about how you would want the system to be if it needs to deal with millions of orders.
