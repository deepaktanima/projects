### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client's want to have small medicale platform app where he want to manage his user through basic SSO platform.
2. He also want to send email to user's registered email's address during: <br />
    a. Signup. <br />
    b. Sign. <br />
    c. Can reset password.

### Used Apps:
1. Amazon Amplify for UI react app.
2. Amazon Cognito to manager user's identity.
3. Amazon SES to manage sender's email.
4. Amazon Lambda function to send emails.

### Apps Into:
1. **AWS Amplify**: <br />
                    a. This is everything you need to build full-stack web UI & mobile apps. <br />
                    b. It comes with inbuild URL, just like AWS cloudfront & S3 have, to host your apps.

2. **Amazon Cognito**: <br />
                    a. The service helps you implement customer identity & access management into web & mobile applications. <br />
                    b. You can quickly & user authentication & access control to your applications in minutes. <br />
                    c. It is fully AWS managed apps so it comes with scalelibilty. <br />
                    d. It help you to trigger another AWS application like lambda, SES etc.

3. **Amazon SES**: <br />
                    a. It is a cloud-based email service provider that can integrate into any application for high volume email automation.

4. **Amazon Lambda function**: <br />
                    a. It is a compute service & serverless applications that runs your code in response to events & it automatically manages the compute resources.

### Solution:
1. We created a UI with reactjs and hosted it into the amplify.
2. We created 3 random URL to call each process of cognito.
    a Login.
    b Signup.
    c Reset password.
3. Whenever a new user comes to website it for signup, it clicks on sinup button.
4. By clicking on  SINGUP URL, our reacts code hits cognito URL which helps users to create their identity.
5. Once user create it's identity, cognito automatically trigger the lambda to send welcome email by using SES email.
6. The lambda have the email templates loaded with client's website details.
7. Same method we implemented for rest of the 2 use cases.
