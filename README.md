# Save User Info with your Chatbot using AWS LEX


# Final Project Overview

✅ A new Lex chatbot called BankerBot.
✅ WelcomeIntent set up.
✅ FallbackIntent customised, i.e., your BankerBot says a customised error message if it doesn't understand the user's input.
✅ CheckBalance set up with your custom slot type called accountType.
✅ Random bank balance figures returned to you when you check your balance.


![image](https://github.com/user-attachments/assets/9481bcd3-3541-49c4-bd90-ace0971c2c48)


# Step 1: Select Create bot in AWS LEX

1. Select Create a blank bot.

2. For Bot name, enter 

3. Under IAM permissions, select Create a role with basic Amazon Lex permissions. We'll be using it to call Lambda later!

4. Under Children’s Online Privacy Protection Act (COPPA), select No.

5. Under Idle session timeout, keep the default of 5 minutes.
   
6. Select Done.

 
 
![image](https://github.com/user-attachments/assets/315ddb06-bef3-4ad2-8802-19e2ed080264)



# Step 2: Set Up WelcomeIntent

1. Under Intent details, enter 
2. for the Intent name.
3. Add the description 
5. Scroll down to the Sample utterances panel.
6. Click the Plain Text button


![image](https://github.com/user-attachments/assets/11c39b1f-be80-4ab0-b428-4702a5701005)


![image](https://github.com/user-attachments/assets/2b5a8d84-e147-49b9-8cb9-6cf01aff24d5)


1. Scroll down to Closing response, and expand the speech bubble for Response sent to the user after the intent is fulfilled.
2. In the Message field, enter the following message:

![image](https://github.com/user-attachments/assets/fbcd2ef9-095a-459a-83fc-3efa622c4719)


1. Choose Save intent.
2. Choose Build, which is close to the top of the screen.
3. Choose Test.


# Step 3: Manage FallbackIntent

![image](https://github.com/user-attachments/assets/df01c331-dead-4d30-9709-257fa903222e)

1. Scroll down to Closing responses.

2. Expand the speech bubble for Response sent to the user after the intent is fulfilled.

3. In the Message field, add the following text:‍

![image](https://github.com/user-attachments/assets/7362d1c4-86b7-4c34-80e9-246248271fb6)

1. Choose Save intent.
2. Choose Build - time for another stretch!
3. Choose Test.

![image](https://github.com/user-attachments/assets/cd710548-3ab6-4e0c-b955-f035bfb88351)



# Step 4: Create the AccountType Custom Slot

1. Choose Add slot type.
2. From the dropdown, choose Add blank slot type.
3. Enter for the Slot type name.
4. Choose Add.
5. This will bring up a large Slot types editor panel! Woooooo welcome.
6. In the Slot value resolution panel, choose Restrict to slot values.


![image](https://github.com/user-attachments/assets/1eee0547-7eab-4798-bf11-7ab9eb3aca7c)


1. Now let's add the three account types!

2. In the Values field, enter 

3. Select Add value, or just press Enter on your keyboard.

4. Do the same for 

5. Enter , and add a few synonyms in the second field. Press 
 on your keyboard after every time you add in a new one:

6. Choose Add value to finish up your work for Credit.




# Step 4: Create the CheckBalance intent


![image](https://github.com/user-attachments/assets/37c38446-d78e-4ee4-bc7a-b8bf1fc7a9e5)



1. head back to Intents.
2. Choose Add intent, then Add empty intent.
3. Enter as your intent name
4. Choose Add.
5. Enter the following description in the Intent details panel:
6. Scroll down to Sample utterances.


![image](https://github.com/user-attachments/assets/270c658f-17f0-4cdf-875d-bb0636fd94a2)


1. Choose Add slot button.
2. For slot's Name, enter 
3. For the Slot type, choose your custom slot value 
4. Enter the following for Prompts: 
5. Choose Add.

![image](https://github.com/user-attachments/assets/6124c3ac-be5d-4451-87ff-3dbc55f893d2)


![image](https://github.com/user-attachments/assets/2d8cfa60-f03a-49c9-80c9-dfe70181128d)

![image](https://github.com/user-attachments/assets/2fe67c1e-49f8-447c-82ca-f21498f80206)


1. Choose Save intent.
2. Choose Build.
3. Choose Test.


![image](https://github.com/user-attachments/assets/60787e51-0bd1-49a7-8af8-98ced17842cb)





# Step 5: Create Your AWS Lambda Function

1. Head to Lambda in your AWS Management Console.

2. Choose Author from scratch.

3. Function name - 

4. Runtime - Python 3.12, or a later version of Python3 if v3.12 is not available.

5. Select Create function.

6. Scroll down to the Function code section.

7. Double-click on lambda_function.py on the left-hand file browser.

8. Download the following source code file.

https://storage.googleapis.com/nextwork_course_resources/courses/aws/AWS%20Project%20People%20projects/Project%3A%20Create%20a%20chatbot%20with%20Amazon%20Lex%20/BankingBotEnglish%20NextWork.py

9. Choose Deploy

![image](https://github.com/user-attachments/assets/141cd42f-a55c-4671-bdbf-554d8a592cca)


# Step 6: Connect AWS Lambda with Amazon Lex

1. Head back to your Amazon Lex console.
2. Select BankerBot.
3. On the left-hand menu, choose Aliases.
4. Choose the default TestBotAlias.
5. From the Languages panel, select English (US).
6. For Source, choose your Lambda function BankingBotEnglish.
7. Leave the Lambda function version or alias field at the default $LATEST.

![image](https://github.com/user-attachments/assets/cfcc095f-ae12-4244-92ed-93948546fcac)


# Step 7: Connect your CheckBalance intent with your Lambda function

1. Navigate to your CheckBalance intent.
2. Scroll down to fulfillment panel.
3. Expand the On successful fulfillment bubble.
4. Choose Advanced options.
5. Under the fulfillment Lambda code hook panel, check the checkbox next to Use a Lambda function for fulfillment.


![image](https://github.com/user-attachments/assets/91b202b7-a9ed-4d87-a1c1-8a1f69c5c76b)

