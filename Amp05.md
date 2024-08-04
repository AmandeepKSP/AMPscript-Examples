### Task 4 Dynamic Content Based on Gender

HHow can you display different content based on the subscriber's gender?

#### Soltuion
```ampscript
%%%[
VAR @FirstName, @Gender
SET @FirstName = [FirstName]
SET @Gender = [Gender]
IF @Gender == "Male" THEN
]%%
<p>Hello Mr. %%=v(@FirstName)=%%,</p>
<p>Check out our latest products for men!</p>
%%[
ELSEIF @Gender == "Female" THEN
]%%
<p>Hello Ms. %%=v(@FirstName)=%%,</p>
<p>Check out our latest products for women!</p>
%%[
ELSE
]%%
<p>Hello %%=v(@FirstName)=%%,</p>
<p>Check out our latest products!</p>
%%[ 
ENDIF
]%%

```

### Resources

Download the sample dataset from the `AMPScript.csv` file to start practicing.