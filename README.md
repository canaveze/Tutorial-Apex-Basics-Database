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




