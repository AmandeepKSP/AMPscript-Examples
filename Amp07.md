### Task 6  Dynamic City-Based Content

How can you customize content based on the subscriber's city?

#### Solution
```ampscript
%%[
Var @FirstName, @City
Set @FirstName = [FirstName]
Set @City =[City]
IF @City == "Philadelphia" THEN
]%%
<p>Hello %%=v(@FirstName)=%% from Philadelphia,</p>
<p>Check out our exclusive offers for Philadelphias!</p>

%%[ELSEIF @City == "New York" THEN]%%
<p>Hello %%=v(@FirstName)=%% from New York,</p>
<p>Check out our exclusive offers for New Yorkers!</p>

%%[ELSEIF @City == "Los Angeles" THEN ]%%
<p>Hello %%=v(@FirstName)=%% from Los Angeles,</p>
<p>Check out our exclusive offers for Angelenos!</p>

%%[ELSE]%%
<p>Hello %%=v(@FirstName)=%%,</p>
<p>Check out our latest offers!</p>

%%[ENDIF]%%
```
### Resource

Download the `AMPscript.csv` file from the `Amp-csv` folder to start practicing.