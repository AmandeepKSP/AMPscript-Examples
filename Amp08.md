### Task 7  Display Subscriber's Full Information

How can you display the subscriber's full information in the email for verification purposes?

#### Solution
```ampscript
%%[
Var @FullName, @FirstName, @LastName,
@EmailAddress, @PhoneNumber, @Birthdate,
@SubscriptionDate, @Gender, @City, @State, @Country
SET @EmailAddress = [EmailAddress]
SET @FullName = [FullName]
SET @FirstName = [FirstName]
SET @LastName = [LastName]
SET @PhoneNumber = [PhoneNumber]
SET @Birthdate = [Birthdate]
SET @SubscriptionDate = [SubscriptionDate]
SET @Gender = [Gender]
SET @City = [City]
SET @State = [State]
SET @Country = [Country]
]%%
<p></p><p>Here is your information:</p>
<ul>
<li>Email Address: %%=v(@EmailAddress)=%%</li>
  <li>Full Name: %%=v(@FullName)=%%</li>
  <li>First Name: %%=v(@FirstName)=%%</li>
  <li>Last Name: %%=v(@LastName)=%%</li>
  <li>Phone Number: %%=v(@PhoneNumber)=%%</li>
  <li>Birthdate: %%=v(@Birthdate)=%%</li>
  <li>Subscription Date: %%=v(@SubscriptionDate)=%%</li>
  <li>Gender: %%=v(@Gender)=%%</li>
  <li>City: %%=v(@City)=%%</li>
  <li>State: %%=v(@State)=%%</li>
  <li>Country: %%=v(@Country)=%%</li>
</ul>
```
### Resource

Download the AMPscript.csv file from the Amp-csv folder to start practicing.