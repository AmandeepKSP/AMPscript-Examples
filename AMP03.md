### Task 3 - Personalized Greeting

How can you create a personalized greeting that addresses the subscriber by their first name?

#### Solution
```ampscript
%%[
VAR @FirstName
SET @FirstName = [FirstName]
]%%
<p>Hello %%=v(@FirstName)=%%,</p>
<p>Welcome to our newsletter!</p>
```
## Resources

Download the sample dataset from the `AMPScript.csv` file to start practicing.