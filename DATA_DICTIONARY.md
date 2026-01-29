`customer_id` : integer identifier.

 `signup_date` : date the customer signed up (YYYY-MM-DD).

 `region` : one of North, Midlands, South, Scotland, Wales.

 `plan_type` : Basic, Standard, Premium.

`tenure_months` : integer months since sign-up. 

`monthly_fee_gbp` : numeric fee.

 `support_tickets_90d` : integer count of support contacts in last 90 days.

 `last_login_days` : integer days since last login (0–90).

`nps_score` : integer Net Promoter Score (-100 to 100), with a small amount of missingness.

 `churned_90d` : 0/1 indicator for whether the customer churned within the last 90 days.

That is, whether a customer stopped being an active subscriber within 90 days of the snapshot date used for the dataset. So churned_90d = 1 means the customer churned (cancelled, did not renew, or otherwise ceased the subscription) within the next 90 days; churned_90d = 0 means the customer did not churn within the next 90 days (they remained active over that period). 