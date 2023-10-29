# Project Overview

## Content
- **Hot Pepper Gourmet (hpg):** Similar to Yelp, this platform allows users to search for restaurants and make online reservations.
- We utilized the Pandas library to clean and merge data from three sources, optimizing columns for creating informative dashboards.
- You can gain insights into reservation trends and understand the best times to take action for marketing campaigns.

## Data Gathering
- We downloaded the dataset from [Kaggle](https://www.kaggle.com/competitions/recruit-restaurant-visitor-forecasting/data).
- The dataset includes three main files, one of which is `hpg_reserve.csv`, containing information on reservations made within the hpg system.
  - `hpg_store_id`: Unique restaurant identifier in the hpg system.
  - `visit_datetime`: Reservation time.
  - `reserve_datetime`: Reservation creation time.
  - `reserve_visitors`: Number of visitors for that reservation.
- The second file, `hpg_store_info.csv`, provides details about select hpg restaurants, with self-explanatory columns.
  - `hpg_store_id`
  - `hpg_genre_name`
  - `hpg_area_name`
  - `latitude`
  - `longitude`
- The third file, `date_info.csv`, offers essential information about the calendar dates in the dataset.
  - `calendar_date`
  - `day_of_week`
  - `holiday_flg`: Indicates whether the day is a holiday in Japan.

## Data Cleaning
To prepare the data for analysis, we performed the following data cleaning steps:
- Converted the data type of `visit_datetime` and `reserve_datetime` to datetime format.
- Created new columns, `visit_date` and `reserve_date`, with yyyy-mm-dd format.
- Split the `hpg_area_name` column into `prefecture` and `city` columns.
- Merged data from `hpg_reserve.csv` and `hpg_store_info.csv` using the `hpg_store_id` as the key.
- Joined `date_info.csv` on `visit_date`, and removed the `calendar_date` column.
- Joined `date_info.csv` on `reserve_date`, and removed the `calendar_date` column.
- Ensured there were no null records in the dataset.
- Saved the cleaned data as `recruit_restaurant_visitor.csv`.

## Dashboards and Visualizations
For visualizing the insights from the cleaned data, we used `Tableau`. You can explore our dashboards and visualizations through the Tableau Public link [here](https://public.tableau.com/app/profile/takanobu.suzuki/viz/recruit_restaurant/ReservationTrend).
