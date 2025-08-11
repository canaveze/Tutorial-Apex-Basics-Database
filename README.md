# Tutorial-Apex-Basics-Database
This tutorial will walk you through the Apex Basics & Database Trailhead module. By the end, you'll have a solid understanding of how to use Apex to interact with the Salesforce database.

## Get Started with Apex (1/5)

### Apex
public class StringListTest {
    public static List<String> generateStringList(Integer n) {
        List<String> TestList = new List<String>();
        for(Integer i=0;i<n;i++) {
            TestList.add('Test ' + i);
            System.debug(TestList[i]);
        }
    return TestList;
    }
}

### Debug
StringListTest.generateStringList(5);

## Use sObjects (2/5)

### 1. Describe the relationship between sObjects and Salesforce records.
C) Every record in Salesforce is natively represented as an sObject in Apex.

### 2. How do you create an sObject instance, such as an Account?
A) Declare a variable and assign a new sObject instance to it.

### 3. Which of the following is correct about a generic sObject variable?
C) A generic sObject variable can be assigned to any specific standard or custom sObject, such as Account or Book__c, using casting.

## Manipulate Records with DML (3/5)

### Apex
public class AccountHandler {
   public static Account insertNewAccount(String AccountName){
        Account acct = new Account(Name=AccountName);
        try{
            insert acct;
        }
        catch(DMLException e){
            return Null;
        }
        return acct;
	}
}

### Debug 1
AccountHandler.insertNewAccount('new test account');

### Debug 2
AccountHandler.insertNewAccount('');

## Write SOSL Queries (4/5)

### Apex

public class ContactSearch {
    public static List<Contact> searchForContacts(String lN,String mpc){
        List<Contact> contactList=[Select Id,Name from Contact where
                                  LastName=:lN and MailingPostalCode=:mpc];
        return contactList;
    }
}





