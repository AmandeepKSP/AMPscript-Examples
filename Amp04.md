### Task 4 Birthday Email

How can you send a special birthday message to subscribers on their birthday?

#### Soltuion
```ampscript
%%[
VAR @FirstName, @BirthDate, @Today, @BirthMonth, @BirthDay, @TodayMonth, @TodayDay
SET @FirstName = [FirstName]
SET @BirthDate = [Birthdate]
SET @Today = Now()

SET @TodayDate = DateParse(@Today)
SET @BirthMonth = DatePart(@BirthDate, "m")
SET @BirthDay = DatePart(@BirthDate, "d")
SET @TodayMonth = DatePart(@Today, "m")
SET @TodayDay = DatePart(@Today, "d")
a
IF @BirthMonth == @TodayMonth AND @BirthDay == @TodayDay THEN
]%%
<p>Happy Birthday %%=v(@FirstName)=%%! Enjoy Your Day</p>
<p>Welcome to our newsletter!</p>
%%[
ELSE
]%%
<p>Hello %%=v(@FirstName)=%%,</p>
<p>Welcome to our newsletter!</p>
%%[
ENDIF
]%%
```

### Resources

Download the sample dataset from the `AMPScript.csv` file to start practicing.