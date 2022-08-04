# Data_Wrangling_Project
## by Yahaya Yusuf Danladi
 This project demonstrate my data wrangling efforts and exploratory analysis


## Dataset
The dataset to analyze is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. WeRateDogs has over 4 million followers and has received international media coverage.

## Quality issues

    Unwanted/Irrelevant columns for this analysis (e.g: geo, coordinates, place & contributors, in_reply_to_status_id, in_reply_to_user_id, retweeted_timestamp to datatime, retweeted_status_id and retweeted_user_id)

    Some tweet have no images (i.e Retweets)

    "timestamp" and "retweeted_status_timestamp" columns are string instead of datetime

    The twitter_archive table contains "None" as values.

    The img_predictions table has values that contain underscores.

    The "source" column has HTML tags.

    Dog names in p1, p2 and p3 has inconsistent letter casing.

    Incorrect dtypes for stage and source columns.

## Tidiness issues

    The doggo,floofer, pupper and puppo dog stages should be in a single column.
    Merge all three dataframes to one (twitter_archive_master).

## Cleaning Data

We made a copy of the original data before cleaning, we cleaned the data with the follwoing operations:
Under Quality Issues

    For Issue #1: Unwanted/Irrelevant columns for this analysis

    We drop unwanted/irrelevant Columns from all tables.

    Fro Issue #2: Some tweet have no images (i.e Retweets).

    We drop Rows that are Retweets since these are no use.

    Fro Issue #3: "timestamp" column is a string instead of datetime

    We Changed timestamp column dtype to datetime

    Fro Issue #4: The twitter_archive table contains "None" as values.

    We Use np.nan ro replace all the "None" value with NaN in name, doggo, pupper,floffer, puppo columns.

    For Issue #5: The img_predictions table has values that contain underscores.

    We Remove Underscores from all columns values.

    For Issue #6: The "source" column has HTML tags.

    We used regex, to remove the html tags from the source column.

    For Issue #7: Dog names in p1, p2 and p3 has inconsistent letter casing.

    We convert all values in the p1, p2 & p3 columns to Proper case.

    For Issue #8: Incorrect dtypes for stage and source columns. *We Convert the stage and source to category dtypes.

## Under Tidiness Issues

    Issue #1: The doggo, floofer, pupper and puppo dog stages should be in a single column.

    We Merge the dog stage columns (doggo, pupper and puppo) into a single column called "stage".

    For Issue #2: Merge all three cleaned dataframes to one (twitter_archive_master).

    We Merge all cleaned datasets into one single dataset.

And finally we saved the cleaned master dataset to a CSV file named "twitter_archive_master.csv".


## Summary of Findings

Upon the exploration of the data, the follwing finding were made.


We found out that Most Tweets are written in English, Most Tweets were written on Mondays (321) with an average of 285 tweets are written every day.
We also found out that the Golden Retriever dog breed (139) that participated in the rating exercise and that most dogs (203) are of the pupper maturity stage