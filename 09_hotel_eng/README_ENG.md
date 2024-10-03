# Predicting customer churn in hotel chains
The client of this study is the chain of hotels "As a guest". In order to attract customers, this hotel chain added to its website the ability to book a room without prepayment. However, if the customer cancelled the reservation, the company suffered a loss. The hotel staff could, for example, stock up on groceries for a guest's arrival or simply not have time to find another customer.
# Research Objective:
Develop a system that predicts reservation cancellations. If the model shows that the reservation will be cancelled, the client is offered to pay a deposit. The amount of the deposit is 80% of the cost of the room for one night and the cost of one-time cleaning. The money will be deducted from the client's account if he still cancels the reservation.
# Result of the study:
As a result of this study, the best model for predicting booking cancellation was the Decision Tree model as it showed the best Recall metric which is the key metric in this problem.

The most important metric for the problem is `Recall` as this metric determines the number of true positives among all the class labels that have been defined as "positive". This estimation metric is especially important when the error of non-recognition of positive class in the given problem is high. In our case, not recognizing a positive class would lead to an incorrect estimation of cancelled guests and, as a result, an incorrect prediction of cancellations. This will lead to unexpected losses.

In our case the model showed the highest efficiency and accuracy:

`DecisionTreeClassifier(max_depth=19, random_state=12345)`
`Recommendations:` When selecting potential guests from whom to charge a deposit, I think it is reasonable to pay attention to the following categories of guests:

According to the results of the model's predictions, the biggest influence, with a large margin, on the target attribute (booking cancellation) was `lead_time` - the number of days between the date of booking and the date.

On the second place goes `customer_type_Transient` - type of customer, and with a small breakaway `total_of_special_requests` - number of special marks.

You should avoid clients that are close to the portrait of an unreliable client, which is the following set of characteristics:

- Clients with `56 days` between the reservation date and the arrival date
- Clients with a special request mark - `0`.
- Clients of the type of customer - `"Transient"`.
