### Task 7  Display Registration Confirmation Email

You are tasked with creating a registration confirmation email.

#### Solution
```ampscript
%%[
    Var @firstname, @lastname, @email
    Set @firstname = AttributeValue("First Name")
    Set @lastname = AttributeValue("Last Name")
    Set @email = AttributeValue("Email")
]%%

Hi %%=v(@firstname)=%%,<br>
<br>
Thank you for registering with us!<br>
<br>
Here are the details we have on file for you:<br>
<br>
First Name: %%=v(@firstname)=%%<br>
Last Name: %%=v(@lastname)=%%<br>
Email: %%=v(@email)=%%<br>
<br>
If any of these details are incorrect, please click here to update your information.<br>
<br>
Best regards,<br>
The Team
```
### Resource

Download the `Amp09.csv` file from the `Amp-csv` folder to start practicing.



