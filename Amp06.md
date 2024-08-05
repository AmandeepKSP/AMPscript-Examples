### Task 5 Subscription Anniversary Email

How can you send a special message on the anniversary of the subscriber's subscription date?

#### Soltuion
```ampscript
%%[
Var @FirstName, @SubscriptionDate, @TodayMonth, @SubscriptionMonth, @SubscriptionDay, @TodayMonth, @TodayDay
Set @FirstName = [FirstName]
Set @SubscriptionDate =[SubscriptionDate]
Set @TodayDate = Now()
Set @SubscriptionMonth = DatePart(@SubscriptionDate, "m")
Set @SubscriptionDay = DatePart(@SubscriptionDate, "d")
Set @TodayMonth = DatePart(@TodayDate, "m")
Set @TodayDay = DatePart(@TodayDate, "d")

If @SubscriptionMonth == @TodayMonth AND @SubscriptionDay == @TodayDay THEN
]%%
<p>Happy Subscription Anniversary, %%=v(@FirstName)=%%!</p>
<p>Thank you for being with us for another year!</p>
%%[ELSE]%%
<p>Hello %%=v(@FirstName)=%%,</p>
<p>Welcome to our newsletter!</p>
%%[ENDIF]%%

```

### Resources

Download the sample dataset from the `AMPScript.csv` file to start practicing.
