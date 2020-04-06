<p align="center">
  <img width="650" height="300" src="./media/banner.png">
</p>

# Application Development

## Table of Contents

* [Exercises Guide Overview](#exercises-guide-overview)

* [Exercise Purpose and Rules](#exercise-purpose-and-rules)

### [Exercises]

* [Exercise 1: Introduction, setup, and demo](#exercise-1-introduction-setup-and-demo)

* [Exercise 2: Spreadsheet-based Business Objects](#exercise-2-spreadsheet-based-business-objects)

* [Exercise 3: Web and Mobile Apps](#exercise-3-web-and-mobile-apps)

* [Exercise 4: Data from service](#exercise-4-data-from-service)

* [Extra Exercise 5: Add Data Using REST Call](#extra-exercise-5-add-data-using-rest-call)

* [Extra Exercise 6: Review and edit JavaScript code “under the covers” of VBCS](#extra-exercise-6-review-and-edit-javascript-code-under-the-covers-of-vbcs)

### [Appendices](#appendix)
* [Appendix A: Create Service Connection from Endpoint](#appendix-b-create-service-connection-from-endpoint) - For old-style RESTful APIs

* [Appendix B: Build Mama Maggy Data Application](#appendix-c-build-mama-maggy-data-application) - Used in Exercise 4 and Extra Exercise 5

# Exercises Guide Overview

## Exercise Purpose and Rules

The folowing exercises are designed to provide you with an introduction to using Visual Builder to create Web and Mobile applications and to prepare you to demonstrate it's features to customers.

Here are some general guidelines that will help you get the most from
these exercises.

  - Read through an entire exercise before executing any of the steps.
    Becoming familiar with the expected flow will enhance your learning
    experience.

  - Ask before you do. If you have any questions, please ask the
    instructor before you march down a path that may lead to wasting
    your time.

  - Follow the steps as shown in the Exercise Guide. This is a live
    environment. If you want to do something that is not in the Exercises,
    ask the instructor first. In particular, do not create, delete,
    or alter any cloud objects without asking first.

  - There is no prize for finishing first; there is no penalty for
    finishing last. The goal is to gain a firm understanding of Oracle
    Visual Builder.

  - Ask questions freely. The only dumb questions are those that are not
    asked.

# Exercises

In these exercises you will use Visual Builder to help Mama Maggy’s (using data supporting the Mama Maggy use case, but, other data could be substituted) by adding product ordering and order tracking solutions.

Today when a manager or franchisee needs to order supplies everything is accomplished with a series of phone calls between the manager/franchisee and Mama Maggy headquarters. The only status checks available are by again calling headquarters. 
* Manager/franchisee determines need.
* Manager/franchisee calls HQ for product name and pricing info.
* Manager/franchisee calls HQ to create an order for one or more products.
* Manager/franchisee waits for delivery, if they wish to check status they must once again call HQ.

In addition, if store managers/franchisees wish to contact other stores to ask about borrowing supplies or to discuss business, they once again have to go through headquarters to get contact information. 

These processes are often inconvenient and slow, the managers/franchisees would like to improve things.

In our exercise we will BEGIN to address the needs of the managers/franchisees by adding:
- Web application allowing managers/franchisees to see what products are available for order and what the prices are.
- Web application to list all product orders including each line in the order's product, quantity, and prices.
- Mobile application allowing busy manager/franchisee to check the status of their orders from anywhere with their phone.
- Web application to list all Mama Maggy stores and their locations and the list of associates in that location along with contact information.

In the interest of time this exercise focuses on creating apps to help managers/franchisees to self-serve information they currently rely on headquarters for. Future work will be necessary to automate the creation and update of orders and/or the other information.

The exercise is presented in four parts: Exercise 1 – Introduction and Setup, Exercise
2 - Spreadsheet-based Business Objects, Exercise 3 – Web and Mobile Apps, Exercise
4 – Data from Service. There are two additional “extra” exercises available
for anyone who happens to finish early. No prior experience with Visual
Builder is assumed or necessary.

**Prerequisite:** Before starting these exercises, you should have an OCI
login and `ServerDeveloper` or `ServerAdminstrator` access to our VBCS instance **"OSPA-Class-Of-SE"**  If you are doing this exercises NOT with Class Of SE; most formal classes will share an existing VBCS instance and your permissions will already correct. If you do not have a VBCS instance you may create one using the instructions in the [Getting Started Section](gettingstarted.md) 

**Data Files:**
You will need four data files, three will be used in exercise 3 and one will be used in exercise 4. All four files are available in a single .zip file named [vbcsfiles.zip](https://github.com/oracle/learning-library/blob/master/ospa-library/appdev/application-development-lab/files/vbcsfiles.zip) on GitHub; download the file and expand it to find the following four files (keep them handy they will be used later in this exercise):
- Exercise 2 (data for VBCS Business Objects)
  - Product.csv
  - ProductOrder.csv
  - ProductOrderLine.csv
- Exercise 4 (links used for VBCS Service Connections)
  - AppDev_Endpoints.txt

**NOTE:** All four files may also be downloaded directly from GitHub, however, to download the .csv files directly will require extra steps;  open the .csv in your browser, then, click 'Save As' to store the file as .csv (use the .zip file it's easier)

**NOTE:** Content is driven by external factors such as user data entries and login date. As a result, what you see displayed in your environment may not exactly match with the lab screenshots. Screenshots are provided solely for illustrative purposes to help guide you through the user interface.

**Disclaimer:**  This exercise is designed ONLY for large learning groups and assumes the groups are sharing the Oracle Cloud environment to execute this exercise.
 
**Options**:
- Who Should Complete This exercise:  All Participants (preferred)
- Who Should Complete This exercise:  1 Participant for group

# Exercise 1: Introduction, setup, and demo

In this exercise you will make sure you can access the VBCS instance for your
classroom and supporting exercise files.

1. First, go to cloud.oracle.com, click on **View Accounts** and select **Sign in to cloud**<p>
![](./media/1.1.1.png)<p><br>

2. Enter the name of your **tenancy** or the **cloud account**.<p>
![](./media/1.1.2.png)<p><br>

3. On the login screen select Oracle SSO and provide your credentials.<p>
![](./media/1.1.3.png)<p><br>

4. Once in the main dashboard, open the **General Menu** located at the top left hand side of the screen, select **Platform Services**, and click on **Visual Builder**.<p>
![](./media/1.1.4.png)<p><br>

5. Click the dropdown menu next to your instance name, and select **Open Oracle Visual Builder Home Page**.<p> 
![](./media/1.1.5.png)<p><br>

6. When the **Visual Applications** welcome appears; choose the **New Application** button.<p>
![](./media/1.1.6.png)<p><br>

7. When the **Create Application** page appears, provide a name for the application; you may call your applications anything you wish.<p>
![](./media/1.1.7.png)<p><br>

8. You are now ready to start building your application\!<p>
![](./media/1.1.8.png)<p>



9.  When the “Create Application” page appears, provide a name for the application; you may call your applications anything you wish.
    

    If you are sharing your lab environment with a group of people you might find it convenient to follow a naming convention to make it easier for you to find your work and for the facilitators to help you.
    
    Combine your name or initials with three characters representing your location to use as an application name or to add as a prefix to the names of all applications you create. Visual Builder's list of applications may be sorted and filtered easily.

    (The facilitator will share a three-character code for you to use in your location.)
      
    Be sure the “Empty Application” template is selected and click “Finish” to continue.

  ![](./media/New1.8.png)



10. You are now ready to begin creating your application\!

  ![](./media/vbcs_new_start_building.png)



This concludes exercise 1.

[Go to exercise 2](#exercise-2-spreadsheet-based-business-objects) – [Return to Table of Contents](#table-of-contents)


# Exercise 2: Spreadsheet-based Business Objects

To build the solutions for Mama Maggy's managers/franchisees, data is required, right now that data is stored in several spreadsheets. We need to make that data available inside VBCS so that it may be used in the web and mobile applications created in these exercises.

Visual Builder provides two main methods to access data: built-in business objects, and service connections. VBCS business objects store data in tables like a database. This exercise focuses on creating
and using built-in business objects with data suppiled via spreadsheet (.csv/.xlsx) files. These files get copied into an Oracle Database (under the covers of VBCS) and are actually accessed using the same type of RESTful APIs as those used for service connections (more on this in exercise 4).

NOTE: For this exercise you will need three data files (Product.csv, ProductOrder.csv, and ProductOrderLine.csv), if you have not already downloaded them they may be obtained from GitHub as a .zip file named [vbcsfiles.zip](https://github.com/oracle/learning-library/blob/master/ospa-library/appdev/application-development-lab/files/vbcsfiles.zip); download the file and expand it to find the following three files (keep them handy they will be used later in this exercise):
- Product.csv
- Products available for managers/franchisees to order
- ProductOrder.csv 
- Existing order information: date of order, status, and associate who made the order.
- ProductOrderLine.csv
- Order lines showing the products requested in each of the current orders, their unit price, and the quantity desired.

A fourth file 'AppDev_Endpoints.txt' will be used in a later exercise.


1.  If you have logged out of the Oracle Cloud, please log back in and
    return to your VBCS application. On the left-hand side of the Visual Builder interface is a navigator
    listing several options; choose “Business Objects”

      | Mobile Applications | ![](./media/image67.png) |
      | ------------------- | ------------------------ |
      | Web Applications    | ![](./media/image68.png) |
      | Service Connections | ![](./media/image69.png) |
      | Business Objects    | ![](./media/image70.png) |
      | Components          | ![](./media/image71.png) |
      | Processes           | ![](./media/image72.png) |
      | Source View         | ![](./media/image73.png) |


  
2. If you don’t see the navigator, click the “Expand Navigator” icon in the upper-left corner. 
 ![](./media/image74.png)

  - If you don't have any Business Objects already you'll see the following "You don't have any business objects defined yet" image; click on the "+ Business Object" button.
  ![](./media/vbcs_no_biz_objects.png)

  - If you already have Business Objects a list will appear; click the plus sign "+" at the top of the Business Objects list.
  ![](./media/vbcs_add_biz_object.png)

3.  From the application page, click “+ Business Object” to begin adding
    a business object

4. The first Business Object you will create will contain information about what products are available for managers/franchisees to order for their stores; we'll use the name "Product" to keep things simple.

5. Set the business object name to “Product” as shown here and click the Checkmark ![](./media/image24.png) when ready to continue.
![](./media/image25.png)

6. The Business Object page allows you to create Fields and manage your Business Object. Note that some fields have been defined automatically, this is normal. The “id” field is treated as a key and will be used to access items in the business object automatically later.
![](./media/image26.png)

7. To add a field click the “+ New Field” button
![](./media/image27.png)

8. For each new field the Name and General Data Type are specified

  - Set the label of the first field to “Product Name” note that Visual Builder creates the name as “productName”

  - Set the Type to character by making sure the “A” ![](./media/image28.png) is selected as shown below (be sure to select the correct "type")

  - Click the “Checkmark” icon ![](./media/vbcs_checkmark.png) when done
![](./media/image29b.png)

9.  In the box at the lower-right part of the VBCS editor set the field property to “Required”
![](./media/image30.png)

10.  Now add three more fields; be sure to mark the all “Required” so that you end up with a list like this (note that all four of the fields added should be marked "Required"):

  - A (text)productNameProduct Name (already done above)

  - A (text)product Description Product Description

  - \# (numeric) unitPrice Unit Price
![](./media/image31.png)


11. Create another Business Object named **Product Order** (ProductOrder) by clicking the **plus sign** at the top of the Business Objects list again
![](./media/Snap675.png)
The **Product Order** Business Object will contain specifics about orders made by managers/franchisees including the associate that made the order, the order date, the current order status (open, shipped, complete) , and the last date some action (order shipped, order closed, etc.) occurred on the order.

12. Add these fields; be sure to mark them all **Required**
   | Display Label | Field Name  | Type     |
   |:--------------|:------------|:----------|
   | Associate     | associate   | #         |
   | Order Date    | orderDate   | Date Time |
   | Order Status  | orderStatus | A         |
   | Action Date   | actionDate  | Date Time |<p>
  
13. The final result looks like the screen shot *(Check the fields added are set the correct **type** and marked **Required**)*
![](./media/AppDev2.9.2.png)

14. Create another Business Object named **Product Order Line** (ProductOrderLine).
The **Product Order Line** Business Object will contain specifics about each item included in **Product Orders** made by managers/franchisees including the product ordered, its Unit Price, and the Quantity ordered.
To make it possible for VBCS to connect the **Product Order Line** with the correct **Product Order** and the **Product** being ordered (so that the product name can display rather than a product id) you will create two **Relationships**:<p>
  - between the **Product Order Line** and its associated **Product Order** record
  - between the **Product Order Line** and the Product being ordered
    But this time before adding fields you will first add two relationships to the other business objects that will show up as 'references' later. These relationships connect specific products to product order lines and product order lines to product orders allowing VBCS to **automatically** connect that data when building web and mobile applications later.
![](./media/image35.png)

15. Click on the “Overview” tab to see where relationships are defined.
![](./media/image36.png)


16. Click on the plus sign “+” to begin adding relationships.
![](./media/image37.png)


17. Use the “drop down” on the right side of the screen to select “Product Order” and check to make sure that “Product Order” is on the “One” side and “ProductOrderLine” is on the “Many” side of the relationship. Click “Create Relationship” (default values are ok).
![](./media/vbcs_productorderlinerel.png)


18. Click on the plus sign “+” to add another relationship.
![](./media/vbcs_onerel.png)

19. Using the drop-down on the right side of the screen select the “Product” and make sure that “Product Order Line” is on the “Many” side and that “Product” is on the “One” side of the relationship. Click “Create Relationship” when done (defaults are ok).
![](./media/vbcs_productorderproductrel.png)
The relationships have been defined, now to enter remaining fields.
![](./media/vbcs_two_rel.png)

20. Return to the “Fields” tab; the two relationships are now listed as fields with a “reference” icon ![](./media/image42.png) indicating the relationship. Select the last row, “Product” as shown in next screenshot and click “+ New Field” icon ![](./media/vbcs_plus_new_field_small.png) to continue (VBCS adds new fields below the currently selected field).
![](./media/image43.png)


21. Next, you will add two fields in the usual manner. Add “Unit Price” and “Quantity” as numeric fields.
![](./media/image44.png)
![](./media/image45.png)

22. The completed field list should look like this:
![](./media/image46.png)

23. Examine the “Endpoints” created by VBCS for each of the Business Objects you defined; these are the RESTful APIs that allow your applications (and others) to access the Business Object; Get (read, Post (create), Patch (update), Delete (delete) – we will use at least two of these in the next lab.
![](./media/image47.png)

24. It will be useful for testing purposes to have some data in the "Product" Business Object. VBCS provides a way to load single rows/records manually as shown below. (In #15 below you will add many rows/records from an input file).
25. Reopen the “Product" Business Object (from the Business Objects list); click on the "Data" tab and then click “+ Add Row” to add a row of data
![](./media/image48.png)

26. Provide the following values for the new row:
  - Product Name MOZZARELLA
  - Product Description Mozzarella cheese
  - Unit Price 7
(click the "Checkmark" ![](./media/vbcs_checkmark.png) when done)
![](./media/image49.png)

27. Add two more rows for DOUGH and PIZZA\_SAUCE:
DOUGH
  - Product Name DOUGH
  - Product Description Dough
  - Unit Price 11
![](./media/image50.png)
PIZZA\_SAUCE
  - Product Name PIZZA\_SAUCE
  - Product Description Pizza Sauce
  - Unit Price 6
![](./media/image51.png)

28. Review the rows
![](./media/image52.png)

29. To load more rows from a .csv file; click on the “Product” Business Object’s hamburger menu ![](./media/image16.png) and choose “Data Management”
![](./media/image53.png)  

30. Choose “Import from File”
![](./media/image54.png)


31. Click on “Upload a file or drag it here
![](./media/image55.png)


32. Select the “Product.csv” file provided
![](./media/image56.png)


33. Click the “Import” button to upload the selected file
![](./media/image57.png)


34. You should see success message like the following; if not, try again or ask the instructor for help; click “OK” button when complete
![](./media/image58.png)


35. Review the “Product” business object data to see the results of the load. 
![](./media/image59.png)


36. Create an initial “Product Order” (Product Order -> Data -> + Add Row) as follows, then review your results  
![](./media/AppDev2.20.png)


37. Create an initial “Product Order Line” as follows, use the “Product Order” and “Product” pull-downs to choose those values (if the value you want does not appear in the list you can start to type the value in and it will appear, for instance "M" for "Mozzarella"), type in the other two then review your results and click the checkmark 
![](./media/vbcs_checkmark.png)
![](./media/image61.png)


38. Now, using the technique illustrated in 16-18 above add data to the Product Order and Product Order Line business objects (note: file names same as business object names) using the provided data files

  - Product Order - ProductOrder.csv
  ![](./media/AppDev2.22.1.png)
  - Product Order Line - ProductOrderLine.csv
  ![](./media/image63.png)


39. Click on the business object “Hamburger” icon ![](./media/image16.png) and select “Diagram” to see the relationships
![](./media/image64.png)

![](./media/image65.png)

Congratulations! The data needed allowing Mama Maggy managers/franchisees to see what products are available to order and to check the status of existing orders is now ready for use. This data will be used in the next three exercises.

This concludes exercise 2.

[Go to exercise 3](#exercise-3-web-and-mobile-apps) – [Return to Table of Contents](#table-of-contents)

# Exercise 3: Web and Mobile Apps

Visual Builder provides an easy-to-use WSYIWG *(What You See Is What You Get)* graphical interface for “painting” applications and providing values declaratively allowing people who are not professional developers to create applications. Professional developers may use Visual Builder too; they might also choose to use VBCS’s advanced features and coding capabilities to make applications more-robust.

In this exercise you will create Web applications so that Mama Maggy managers/franchisees may see what products are available for order and to track the status of orders once they are made.

This exercise has three sections:

  - Section 1 – [Create First Web Application](#section-1--create-first-web-application)

  - Section 2 – [Create Master-Detail Application](#section-2--create-master-detail-application)

  - Section 3 – [Create Mobile Application](#section-3--create-mobile-application)

## Section 1 – Create First Web Application

In the last exercise you created three business objects and added data to them; now you will create a web application to work with them

1.  If you're still logged in to the Oracle Cloud and VBCS, skip to #2 below. 

1. If you have logged out of the Oracle Cloud, please log back in and return to your VBCS application. You might find it useful to close any open windows.

1.  On the left-hand side of the Visual Builder interface is a navigator listing several options; choose “Web Applications” ![](./media/image66.png)

| Mobile Applications | ![](./media/image67.png) |
| ------------------- | ------------------------ |
| Web Applications    | ![](./media/image68.png) |
| Service Connections | ![](./media/image69.png) |
| Business Objects    | ![](./media/image70.png) |
| Components          | ![](./media/image71.png) |
| Processes           | ![](./media/image72.png) |
| Source View         | ![](./media/image73.png) |

  
1. If you don’t see the navigator, click the “Expand Navigator” icon in the upper-left corner, then click the "Web Applications" button
![](./media/image74.png)
 
1. Add a new Web Application

1. First, you'll create a web application with two features; a list of all products that a manager/franchisee might order, and a page showing specifics about a chosen product.

1. If you don’t have any Web Applications yet; click the “+ Web Application” button
![](./media/image75.png)
 
 
1. Or, if you want to add to your existing Web Applications; click the plus sign “+” at the top of the Web Apps list
![](./media/image76.png)
 

1. The first Web Application you will create will be called “productList” - type the name in the “Id” box and click the “Create” button to start building the application.
![](./media/image77.png)


1.  The Visual Builder interface has three main tabs for creating web applications: ![](./media/image78.png) Designer, ![](./media/image79.png) Components, and ![](./media/image80.png) Page Structure.
![](./media/image81.png)

1. Visual Builder will also display an object list in the navigator
![](./media/image82.png)


1. Drag a “Heading” component from the Component list (icon is a toggle) to the display area
![](./media/image83.png)
![](./media/image84.png)


1. Change the heading to “Product List” using the Property Inspector on the right-side of the screen. The “slider” may be used to alter the heading’s size.
![](./media/image85.png)


1. If you don’t see the Property Inspector; click the “Expand Property Inspector Icon” in the upper-right corner.
![](./media/image86.png)

1. The screen should look something like this now.
![](./media/image87.png)


1. Add a table to the application by scrolling the Components list until you see the Table icon.
![](./media/image88.png)
 
 
1. Drag the Table icon to the design area.
 ![](./media/image89.png)
 

1. To add data to the table, select the table and click the “Add Data” option from the list on the right.
![](./media/image90.png)

1. The “Add Data” wizard will list any Business Objects and/or Service Connections currently defined.
![](./media/image91.png)

1. Choose the “Product” business object then click “Next” to go to the next step in the wizard.

1. Select the fields you wish to display (select them in the sequence to be displayed, you can move them if you make a mistake) and click “Next” to continue in the wizard to “bind” the business object’s data to the objects on the screen.
![](./media/image92.png)

1. For this app you will not be changing the query, so just click the “Finish” button
![](./media/image93.png)

1. Visual Builder will then show some data in the design window.
![](./media/image94.png)

1. Test the application by clicking the “Run” button ![](./media/image95.png) in the upper-right part of the screen.
![](./media/image96.png)

1. A new browser window will open with your running application.
![](./media/image97.png)

1. Success\! Mama Maggy managers/franchisees can now see a list of the various products available for order (without having to call headquarters).

1. Now, let’s add a page of detail. Return to the Visual Builder Designer and select the table containing the property list. Notice the icon on the right side near the top of the Property Inspector.
![](./media/image98.png)

1. The “Quick Start” button makes adding to your application easy.
![](./media/image99.png)

1. The Quick Start options include: Adding data, building a Create Page (new row), an Edit Page (update row), a Detail page (display single row), Delete Action (delete row), or Task Actions (add task controls).
![](./media/image100.png)

1. Click “Add Detail Page” to begin the wizard.
![](./media/image101.png)

1. Once the wizard starts; select the “Product” Business Object and click “Next” to continue.
![](./media/image102.png)


1. Select the fields to be displayed; you may either select by checking them in the list or “dragging” them to the fields in the center area. You may also change title and other features, even the name of the button that will display on the main page to launch this page. Click
“Finish” when done.
![](./media/image103.png)


1. When complete, the object navigator on the left will show the new page. Select the new page “main-product-detail” to see what it looks like. Note that the "Product List" screen is called "main-start" and the "Product Detail" screen is called "main-product-detail" (These may be renamed if desired but it's not really necessary.)
![](./media/image104.png)

1. **Potential Context Error**
You may see an “error” message similar to the following. Remember that Visual Builder is WYSIWYG (what you see is what you get) and attempts to show real data during the design process. This error frequently occurs because Visual Builder cannot find a “context” to tell it which data to display. (in this case, the VBCS editor wants to show the Product Detail page with "live" data, but, does not know which record to display) The process below uses the VBCS editor's "Live" capability to set the context.
![](./media/image105.png)


1. Fortunately there is an easy fix for setting the context. First, look for the “Live/Design/Code” button in the upper-right part of the Visual Builder editor. Click on “Live” to begin the process.
![](./media/image106.png)

1. Now, return to the Product List display and select a row, this sets the context to the selected row. ("MOZZARELLA" selected below)
![](./media/image107.png)

1. Click the "Product Detail" button to return to the Product Detail display and you should now see data rather than the error message
![](./media/image108.png)

1. The VBCS "Live" mode is useful in testing to see how changes might behave, it is not the same as running the application 

1. Click "Design" to exit "Live" mode
![](./media/image109.png)


1. Now, to really test the application; run the application using the "run" ![](./media/image95.png) button in the upper-right corner. When the “Product List” displays note the “Product Detail” button is not available (it is "grayed out") since no product has been chosen. Select one of the products and the “Product Detail” button will become active. Click on the “Product Detail” button to see the details for that product

1. The following two images show something similar your results.
![](./media/image110.png)

1. Once you have reviewed the product details, click the provided “Back” button to return to the list.
![](./media/image111.png)


1. In addition to viewing the data; you may also use the “Quick Start” do add Create, Edit, and Delete pages for products. (not part of this exercise).

Congratulations\! You’ve successfully created your first Visual Builder
web application. 

You've also made a day in the life of a Mama Maggy manager/franchisee easier since they can now see what products are available to order without having to play telephone-tag with headquarters.

[Return to top of Section 1 – Create First Web Application](#section-1--create-first-web-application)

[Return to Table of Contents](#table-of-contents)


## Section 2 – Create Master-Detail Application

In this section you will create a set of screens to represent product orders. As a reminder, here’s what the data model looked like.
![](./media/image65.png)

The second application will allow Mama Maggy managers/franchisees to track the status of their product orders. This will include a list of all product orders, the ability to see the specifics of a single order including a list of each product in that order, its unit price, and the quantity ordered.

In this exercise section you will create a two-screen application similar to the last one with a twist, the Product Order Detail screen will include the list of Product Order Lines that match the Product Order. The exercise guide will not be as detailed for activities you have already gone
through.
  - Product Order List
  - Product Order Detail with list of matching Product Order Lines

 
1. Create a new Web Application to display a list or Product Order business object rows. This is very similar to the Product List created earlier and you will end up with a screen that looks something like this. Include these fields:
  - Id
  - Associate
  - Order Date
![](./media/image112.png)


1. Wow, that date does not look very nice\! A simple way to change the format is by dragging the “Input Date Time” component from the component list and dropping it into the date column
![](./media/image113.png)
![](./media/image114.png)


1. Create a Product Order Detail page for the Product Order page’s table, select these fields:
  - Id
  - Associate
  - Order Date
  - Order Status
  - Action Date

1. Your page should look something like this when done (again, you may need to [switch into “Live” mode to set the context](#potential-context-error))
![](./media/image115.png)

1. Add a new heading “Order Items” BELOW the “Back” button on the Product Order Detail page, make the heading size 2
![](./media/image116.png)


1. Now you’ll add a new table with data from the Product Order Line business object making sure that only lines matching the Product Order appear. First, drag a Table component under the new heading.
![](./media/image117.png)


1. Add data to the table from the Product Order Line business object
![](./media/image118.png)
    

1. In the “Bind Data” step of the Add Data wizard, select:
  - id
  - product
  - unitPrice (set type to Input Number)
  - quantity (set type to Input Number)
![](./media/image119.png)
 

1. Here’s the key step\! In step 3 “Define Query” of the Add Data wizard you will connect the data from the Product Order and the Product Order Line  **DO NOT CLICK “Finish” until complete\!**
![](./media/image120.png)
    
    
1. On the right-side of the “Define Query” wizard page under “Target” expand “{} filterCriterion -\> \[\] criteria -\>{} item\[0\] -\>” to expose attribute, op, and value” as shown below.
![](./media/image121.png)
    
    
1. Select “attribute” and type “productOrder” as a “static” value (references Product Order).
![](./media/image122.png)
    
    
1. Select “op” and type “$eq” also as a “static" value (equal condition test).
![](./media/image123.png)
    
    
1. Drag the “ProductOrderId” value from the left-hand “Sources” column and drop it onto the “value” under “Target”.

1. Click the "Finish" button when done.
![](./media/image124.png)
    
    
1. The Product Order Line information matching the current order should be displayed, if not, you may need to reset the context using the “Live” mode again (see [Section 1 – Create First Web Application
\#10 for more](#potential-context-error))
![](./media/AppDev3.18.6.png)
    
    
1. You should now be able to test your Product Order – Product Order Line “master-detail” screens

1. You've enabled Mama Maggy's managers/franchisees to retrieve a list of their orders and check order status when it is convenient to them without having to call headquarters
    
1. This is a good time to use “Quick Start” to build Create, Edit, and Delete screens for both the Product Order List table (Product Order screen) and the Product Order Line table (Product Order Detail screen)
    
1. Congratulations\! You’re now ready to create your first Mobile application with Visual Builder

[Return to top of Section 2 – Create Master-Detail Application](#section-2--create-master-detail-application)

[Return to Table of Contents](#table-of-contents)

## Section 3 – Create Mobile Application

Mama Maggy's managers/franchisees want to be able to check product order status anytime, not just when they are in their offices. So, in this exercise you will create a mobile application allowing them to check order status from their phone or other mobile devices, wherever they want, whenever they want

1. Use Visual Builder’s Navigator to open Mobile Applications
![](./media/image126.png)


1. If you have not created any Mobile Applications yet click the “ + Mobile Applications” button; otherwise, click the “+” to the right of “Mobile Apps”  
![](./media/image127.png)  
![](./media/image128.png)


1. The New Mobile Application wizard has two steps; select “None” and click the right-arrow button “\>” to continue
![](./media/image129.png)


1. Click “Finish” on the second page of the wizard
![](./media/image130.png)


1. Notice the “mobile” frame to help visualize a mobile app; select the title then modify it in the property inspector
![](./media/image131.png)


1. Drag a “Table” component into the body of the phone, below the title.
![](./media/image132.png)


1. Click on the empty table, then use “Quick Start” to “Add Data” - choose the “Product Order” business object
![](./media/image133.png)


1. Select the id (Input Number), `orderDate` (Input Date) , and `orderStatus` (Text) fields (no need to Define Query)
![](./media/image134.png)


1. Review the page; test
![](./media/image135.png)


1. Add a Detail page using the “Quick Start” menu and `ProductOrder`. Select `id`, `associate`, `orderDate`, and `orderStatus`
![](./media/vbcs_add_detail_prodordermobile.png)


1. The basic Order Detail page looks like this ![](./media/image137.png)


1. Add a heading “Items” below the Order Status by dragging the “Heading” component to the “Flex Container” in the Visual Builder Page Structure (click the Page Structure icon ![](./media/image138.png) to show/hide) then change the heading text to “Items” and the size to “H3”.
![](./media/image139.png)


1. Add a table below the new heading by dragging a “Table” component to the “Flex Container” in the Page Structure display
![](./media/image140.png)


1. Use the table’s “Quick Start” to “Add Data” from "ProductOrderLine" to the table, add Product Name (text) **Find Product Name by drilling down**
![](./media/image141.png)

1. Use “Define Query” to connect the Product List to the list of Items as follows:
  - Open {} filterCriterion -\> \[\] criteria -\> {} item\[0\] -\>
  - Select “attribute” and type “productOrder”
  - Select “op” and type “$eq”
  - Drag “productOrderId” to “value”
![](./media/image142.png)

1. Product Order Line data populates table row(s)
![](./media/image143.png)

1. Test the mobile application the two screens should look something like the following:
![](./media/image144.png)
![](./media/image145.png)

Congratulations! You have made the daily lives of Mama Maggy managers/franchisees easier. Instead of calling headquarters to check the status of their product orders they can now use your mobile app when and where it is convenient.

This concludes exercise 3.

[Return to top of Section 3 – Create Mobile Application](#section-3--create-mobile-application)

[Go to exercise 4](#exercise-4-data-from-service) 

[Return to Table of Contents](#table-of-contents)

# Exercise 4: Data from service

Mama Maggy's has multiple existing databases and other data stores being used to run their business. Mama Maggy management would prefer to access existing databases and any new databases directly rather than duplicating data in VBCS Business Objects.

While using Visual Builder’s built-in business objects is useful; they limit applications to data found within the Visual Builder instance.
Most modern applications will use data from varied sources both in and outside of an organization’s systems. This is accomplished using service connections that take advantage of RESTful APIs exposed by databases and other providers. API stands for Application Programming Interface; a pre-defined calling mechanism used to read and modify data using standardized calls over the internet with HTTP/HTTPS (often called RESTful APIs). RESTful APIs are the most common way of using external data in
modern applications. In this exercise you will add useful information to your application using RESTful API calls rather than Business Objects (though, the truth is that VBCS uses RESTful API calls when accessing Business Objects too).

Your resources for this exercise include two (2) service connections used to access data for Mama Maggy stores and Mama Maggy associates. You will use these “Service Connections” to provide data services to your applications. 


*******************************************************************
NOTE 1:

  If your environment does not have access to the Mama Maggy APIs; use the instructions in [Appendix B: Build Mama Maggy Data Application](#appendix-c-build-mama-maggy-data-application) to create some that you may use.

NOTE 2:

  Exercise 4 assumes access to modern APIs that provide an industry-standard manifest; if only old-style endpoints are available use the instructions in [Appendix A: Create Service Connection from Endpoint](#appendix-b-create-service-connection-from-endpoint) instead of the instructions in this exercise to access the APIs.
*******************************************************************


#### Begin Exercise 4

In this exercise you will create new VBCS Web applications to display a list of Mama Maggy stores and the Associates who work in them. This will make it easier for a Mama Maggy manager/franchisee to collaborate with other. The data used to create these apps will come from "Service Connections" that you will create allowing the application to use data via RESTful APIs provided by the service provider.

1. If you have logged out of the Oracle Cloud, please log back in and return to your VBCS application. You might find it useful to close any open windows

1. On the left-hand side of the Visual Builder interface is a navigator listing several options; choose “Service Connections”
![](./media/image146.png)

1. If you have not yet created any “Service Connections” click the “ + Service Connection” button
![](./media/4.3.1.png)
 
 
1. If you are presented with a list of one or more existing connections click the plus “+” sign at the top of the list to the right of the word “Services”
![](./media/4.3.2.png)
 

1.  The “Create Connection” wizard starts by asking for the source of the connection; for this exercise we will choose “Define by Specification” for the connections created. Please click “Define by Specification” to continue. (if you only have an “endpoint” see [Appendix A: Create Service Connection from Endpoint](#appendix-a-create-service-connection-from-endpoint) for an example of “Define by Endpoint”)
![](./media/image149.png)
 

1.  The wizard will then ask for specifics about the endpoint:
  - Choose **ADF Describe** from the API Type pulldown
  - Choose **Web Address** as the Service Specification
  - Paste the URL into the space provided
  - Name the Service Id **mmassociates**
  - Choose **Oracle Cloud Account** from the Authentication pulldown
  - Select Dynamic, the service supports CORS in Connection Type
  - Click next when you are ready to continue
 ![](./media/4.5.1.png)
 
 
1. When prompted to **Select Endpoints** open the navigator-style list under **Associate**; and for this exercise choose the two GET methods; one returns all **Associate** rows, the other selects specific **Associate** rows using an id value
  
1. Click **Create** to complete the process
![](./media/4.5.2.png)
 

1.  Next, open the service for testing: select the connection, choose the “Endpoints” tab, find and select the desired endpoint (highlighted below)
![](./media/4.6.1.png)
 

1. Test the connection by selecting the “Test” tab, filling in any necessary parameters, and clicking “Send” to make a request
![](./media/4.7.1.png)
![](./media/4.7.1b.png)
 
 
1. When the service responds, look for a response status “200” (everything ok) and check the results
![](./media/4.7.2.png)
![](./media/image156.png)
 
 
1. If the response looks good to you click the “Copy to Response Body” so that Visual Builder will map out the response details as part of the connection
![](./media/4.7.4.png)

1. Locate the next endpoint to test and select it
![](./media/image159.png)
 

1.  This endpoint gets a single “Associate” row that is identified by passing in an “{Associate\_Id}” value (or whatever the key field is named). Type an associate id number (“7 in the example”) and “Send” to test
![](./media/4.9.1.png)  
  
 
1. You have now created and tested two connections
![](./media/4.9.2.png)

1. Repeat the steps above to create the following two “mmstores” connection endpoints
![](./media/4.10.1.png)
  
1. Select the GET endpoints
![](./media/4.10.2.png)

1. Once you have created the connections, test them; repeat the steps 6 to 9 above for the two **mmstores** connection endpoints
    - Mama Maggy Store – get all
    - Mama Maggy Store – get single using {Store\_id}
    ![](./media/4.10.3.png)
    
    - Test the endpoint **getall_Store**
    ![](./media/4.10.4.png)
    
    - Test the last endpoint **get_Store** with store_id as value 2
    ![](./media/4.10.5.png)
    
    - Check the result; dont forget to click **Save as Example Response**
    ![](./media/4.10.6.png)

1. Create a new Web Application named “storelist” that displays all of the Mama Maggy stores in a table. Refer to exercise 3: Web and Mobile Apps if you need a refresher on the basic steps  
![](./media/4.11.1.png)

1. Create a header that says **Mama Maggy Stores** 
![](./media/4.11.2.png)

1. Drag and drop a table component below it
![](./media/4.11.3.png)

1. Add data source to the table; use the **mmstores** service connection as the data source
![](./media/4.11.4.png)
1. Use the **mmstores** service connection as the data source for the table
![](./media/4.11.5.png)

1. Choose the following fields and the primary key:
     - id
     - name
     - city
     - state
 
1. Be sure to select **id** as the Primary Key too
1. Click the **Next** button when you are ready to continue
![](./media/4.12.1.png)

1. No need to Define Query, click the **Finish** button to continue
![](./media/4.13.1.png)

1. The finished screen will look something like this
![](./media/4.13.2.png)
 
1. Use the table’s “Quick Start” ![](./media/image167.png) to “Add Detail Page” to get started
![](./media/image168.png)

1. Use the “mmstores” again (because our connection used the standardized descriptors Visual Builder will choose the correct endpoint)
![](./media/image164.png)


1. Choose the following fields from the Endpoint Structure:
    - id 
    - name
    - address
    - city
    - state
    - mailcode  
    
    ![](./media/4.15.1.png)


1. Your Store details screen should look something like this

 ![](./media/image170.png)
 

1. Now create an “associatelist” web application to display all “Associate” rows (you pick the fields) and provide a “Add Detail Page” to display a single Associate (you pick the fields here too).
  - List display of all Associates (“mmassociates”)
  - Details display of selected Associate (“”mmassociates” using
    “associate\_id”)

1. Test your application

1. For something really fun; return to the “storelist” application and display the “Stores Detail” page (probably called “main-store-detail” or something close)
![](./media/image171.png)
 

1. Add a heading “Associates” under the “Back” button and add a “Table” component under the heading. Use the table’s “Quick Start“ menu to “Add Data” to the screen. Choose the “mmassociates” connection to supply the data
![](./media/image172.png)
 
 
1. Select `id`, `name`, `email`, and `hire date`. Also be sure the “Primary Key” is set to the `id` field.
![](./media/image173.png)
 

1. **STOP** on step (3) “Define Query” so that you can connect the Associates to the Store listed on the page. Under “Define Query” expand “{} filterCriterion -\> \[\] criteria -\> {} item\[0\].
![](./media/image174.png)
 
 
1. Select “A attribute” and type “store” into the text box provided, this is “static” content.
![](./media/image175.png)
 
 
1. Select “A op” and type “$eq” into the text box provided, this is “static” content.
![](./media/image176.png)
 
1. Expand the “Sources” values under “Page-\>{} store” and drag the “id” value from the left side of the screen to the “A value” postion on the right. This establishes the link between the current screen (source) and the Associates data (target).
![](./media/image177.png)
 

1. The completed screen should look something like this. Note, if the system is under stress it may take a few moments for the filtering to work properly. (This delay can be masked using an “if” test but is not necessary for our exercise.)
![](./media/image178.png)
 

This concludes exercise 4.

**Congratulations\!** You’ve now finished the required exercises for this
course.

You may save today’s work using Visual Builder’s “export” capability, this will provide you with a starting point if you would like to continue working on the exercises, **but more importantly will give you a starting point when you want to create a customer demonstration using VBCS**:

  - Return to the list of VBCS applications, highlight your application,
    then click the “Hamburger” menu icon on the right.

 ![](./media/image179.png)

  - Choose “Export

 ![](./media/image180.png)

  - Specify “Export with Data” and you will be prompted for the location
    where you want the application’s “.zip” file copied. (this file may
    be imported into another Visual Builder instance when you want to
    work some more).

 ![](./media/image181.png)

[Go to Extra Exercise 5](#extra-exercise-5-add-data-using-rest-call) 

[Return to Table of Contents](#table-of-contents)

# Extra Exercise 5: Add Data Using REST Call

The “Extra” exercises are intended to “flex” the mind-muscles of those who have finished the other exercises early so, they are short on explanation and there are no example solutions provided.

In this exercise you will work more with RESTful API calls

1.  Review the “orderlist” web application and the similar mobile application

1.  Recreate the “orderlist” as a new application (so that you don’t mess up the old one) 
      
1. See if you can get data from the “mmassociates” service connection (single row access) to provide the associate’s “Name” rather than their “id” in the “Product Orders” list and “Product Order Detail” displays

1.  (optional) Try to repeat \#2 and add replace the associate id with associate name in a copy of your mobile application (again, don’t mess up the original).

This concludes Extra Exercise 5

[Go to Extra Exercise 6](#extra-exercise-6-review-and-edit-javascript-code-under-the-covers-of-vbcs) – 
[Return to Table of Contents](#table-of-contents)

# Extra Exercise 6: Review and edit JavaScript code “under the covers” of VBCS

The “Extra” exercise are intended to “flex” the mind-muscles of those who have finished the other exercises early so, they are short on explanation and there are no example solutions provided.

In this exercise you will work actually “code” (assuming you know something about JET or at least HTML5, JavaScript, and CSS).

1. Reopen one of your Web or Mobile application pages. Select the “Code” view
![](./media/image182.png)


1. This will display the actual code that supports your screen
![](./media/image183.png)

1. Depending upon the time available and your proficiency coding, experiment a little with the code
1. If you’re light on coding skills just try something as simple as changing the size of one of the headings
For instance:  
“\<h2…\>Order Items\</h2\>” on line 19 above might be changed to
“\<h4…\>Order Items\</h4\>” to make the heading much smaller
This concludes Extra Exercise 6

[Return to Table of Contents](#table-of-contents)

# Appendix

# Appendix A: Create Service Connection from Endpoint


1.  If you have not yet created any “Service Connections” click the “+ Service Connection” button
![](./media/image_1.png)
 
 
1. If you are presented with a list of one or more existing connection click the plus “+” sign at the top of the list to the right of the word “Services”
![](./media/image_2.png)
 

1.  The “Create Connection” wizard starts by asking for the source of the connection; for this exercise we will choose “Define by Endpoint” for the connections created. Please click “Define by Endpoint” to continue
![](./media/image_3.png)
 

1. The wizard will then ask for specifics about the endpoint
 ![](./media/image_4.png)

 
1. Provide the “Method” (GET), “URL” (from course specifications), and “Action Hint” (Get Many) then click “Next” to continue. This connection will return all rows from the “Associate” data source
![](./media/image_5.png)
 

1. Provide a name for the connection (“mmassociate” in the example)
![](./media/image_6.png)
 

1.  Test the connection by selecting the “Test” tab, filling in any necessary parameters, and clicking “Send” to make a request
![](./media/image_7.png)
 
 
1. When the service responds, look for a response status “200” (everything ok) and check the results
![](./media/image_8.png)
![](./media/image_9.png)
 
 
1. If the response looks good to you click the “Copy to Response Body” so that Visual Builder will map out the response details as part of the connection
![](./media/image_10.png)
 
 
1. Click the “Create” button to finish the process of building the service connection.
 
1. Create the next connection to select a single “Associate” row that is identified by passing in an “{id}” value (or whatever the key field is named)
![](./media/image_12.png)  

1. Provide a name for the connection (“mmassociateget” in the example)
 ![](./media/image_13.png)
 

1.  Test the connection; be sure to specify a valid id for the test. Please notice that the parameters are surrounded by curly-style braces “{id}” in the path and that a place is automatically provided to enter a test value
![](./media/image_14.png)
 
 
1. Check the response status and values, then click “Copy to Response Body” and the “Create” button to finish things up.  You have now created and tested two connections.
![](./media/image_15.png)


1.  Repeat the steps above to create two more connections
  - Mama Maggy Store – get all (maybe “mmstoregetall”)
  - Mama Maggy Store – get single using {id}. (maybe “mmstoreget”)
Be sure to test your connections. Please ask the instructor if you need assistance

[Return to Appendix list](#appendix)

[Return to Table of Contents](#table-of-contents)

# Appendix B: Build Mama Maggy Data Application

This appendix shows how the “Mama Maggy” application was created to serve as a data source for the Application Development exercises.

Make sure a co-worker has not already performed this task. However, it is possible you may need to create this VBCS application; it is used to simulate “external” data available via RESTful APIs.

In this exercise you will create:
  - A VBCS Application to house the data components (we suggest the name “Mama Maggy”)
  - A “Store” Business Object containing fields and data for the list of Mama Maggy’s stores
  - An “Associate” Business Object containing fields and data for Mama Maggy associates
  - Two .csv files are provided to provide data for Store and Associate   (be sure to create “Store” before “Associate” (Associate references Store), and load data into “Store” first before loading data into “Associate”)

 

1.  Log into your tenancy using cloud.oracle.com; be sure it has been provisioned to allow Visual Builder Cloud Service and the database and object storage instances also required. (check with your tenancy admin if unsure)


1.  From the “Visual Builder” service box there are two ways to open a service console.
![](./media/image_c_3.png)
 

1. One method is to click on the box’s “Visual Builder” text to display a overview page.
![](./media/image_c_7.png)


1. From the overview page, click the “Open Service Console” button to continue.
![](./media/image_c_8.png)


1. Another method is to click the “hamburger” icon ![](./media/image_c_9.png) in the lower-right corner of the  “Visual Builder” service box to display a menu.
![](./media/image_c_3.png)


1. Select “Open Service Console” from the menu
![](./media/image_c_10.png)


1. When the VBCS Service Console “Instances” list appears; use the “Hamburger Icon” ![](./media/image_c_9.png)on the far right and choose “Open Oracle Visual Builder Cloud Service Home Page” to begin creating your new application
![](./media/image_c_11.png)


1. When the “Visual Applications” list appears; choose the “New” button
![](./media/image_c_12.png)
![](./media/image_c_13.png)


1.  When the “Create Application” panel opens; provide an “Application Name” of “Mama Maggy” (“Application Info” will default based upon what you type), provide a description (optional), and select the “Empty Application” template (should be the default)
![](./media/image_c_14.png)
 
1. Click the “Finish” button when done
![](./media/image_c_15.png)


1. This application will be used to host two Business Objects that will be used by other applications via RESTful APIs; this is simulating the use of external API access such as database or SaaS application

1. Select the “Business Object” button to start creating business objects
![](./media/image_c_16.png)
 

1. From the application page, click “+ Business Object” to begin adding a business object
![](./media/image_c_17.png)
 
 
1. Provide a name “Store” and click the “checkbox” icon
![](./media/image_c_18.png)
 

1.  Add Fields to the Store object as follows (please create them as shown to match the .csv data):
    - Name
    - Address
    - City
    - State
    - Mailcode
![](./media/image_c_19.png)


1. Create an “Associate” object next; this will happen in steps to account for the reference in the “Associate” row to the “Store” row


1. Add fields as follows:
     - From the “Fields” tab, click “+ New Field” and add “Name”
     - Define the “Store” relationship:
       1.  Switch to the “Overview” tab
       2.  Click “Relationships +”
       3.  Use dropdown to select “Store”
       4.  Make sure the relationship is one “Store” to many “Associate”
       5.  Click “Done” when finished
     - From the “Fields” tab, click “+ New Field” and add “Hire Date” (date field)
     - From the “Fields” tab, click “+ New Field” and add “Email” (email field)
 ![](./media/image_c_20.png)
 
1. Use the Business Object “hamburger” icon’s ![](./media/image_c_9.png) menu to select “Diagram” option.
![](./media/image_c_21.png)
 

1. The business object diagram should look like the following; if not please correct or redo
![](./media/image_c_22.png)
 

1. To load data into the objects, start by once again using the Business Object “hamburger” ![](./media/image_c_9.png)icon but this time select the “Data Manager” option
![](./media/image_c_23.png)
 
 
1. Click on “Import from File” from the “Manage Application Data” panel
![](./media/image_c_24.png)
 
 
1. Click on the “Upload a file or drag it here” picture
![](./media/image_c_25.png)
 
 
1. Select the “Store.csv” file supplied as part of the course setup and click the “Import” button
![](./media/image_c_26.png)


1. Visual Builder will report upon the success/failure of the import
![](./media/image_c_27.png)


1. Import the “Associate.csv” file using the same technique
![](./media/image_c_28.png)


1. Results should be.
![](./media/image_c_29.png)


1. Review the added data using the “Data” tab for the two objects
![](./media/image_c_30.png)
![](./media/image_c_31.png)
 

1. Access points currently have a “version” number and will change each time the objects are modified. Currently only the “development” addresses are available. The steps below will show you how to publish and make the addresses constant
![](./media/image_c_32.png)
 

1. To “set” the access points so that they will not change over time; you must first “Stage” and then “Publish” the application.  (When the application is in "Development" and "Staging" the addresses are versioned; once an application is published to the "Live" environment the address will not change and is suitable for sharing)
      
1. First, return to the list of business objects
![](./media/image_c_33.png)
 
 
1. Using the “hamburger” icon ![](./media/image_c_9.png) (far right) open the menu and select “Stage” for the application
![](./media/image_c_34.png)
 
 
1. Select “Populate Stage with Development data” to copy the data loaded previously into the staging environment, then click the “Stage” button
![](./media/image_c_35.png)
 
1. The addresses we need are still not final, so the application must be published. Return to the list of applications and click the “hamburger” icon again. This time choose the “Publish” option
![](./media/image_c_36.png)

1. Be sure to “Include data from Stage” before you click the “Publish” button
![](./media/image_c_37.png)


1. Reopen the application. In order for others to use REST APIs toaccess the data in the application’s business objects the Resource API addresses must be made available

1. Select the “Store” business object and click on the “Endpoints” tab. Addresses are listed for Development, Staging, and Live environments. Also there are two columns, the ones on the left provide Metadata that more-advanced client applications (like Visual Builder) may take advantage of. The column on the right shows data-only “Endpoints” that require a little more work to use
 
1. From the left column select the “Live” address and click the “clipboard” icon ![](./media/image_c_38.png). Paste the resulting string into a text file in your local environment to share with applications wanting to use the data
 
1. This is the address needed to access “Store” data
![](./media/image_c_39.png)
![](./media/image_c_40.png)
 
 
1. Select the “Associate” business object and once again display the “Endpoints” tab. Copy the value from the “Metadata” column “Live” row using the “clipboard” icon ![](./media/image_c_38.png). Paste the resulting string into a text file in your local environment to share with applications wanting to use the data
 
1. This is the address needed to access “Associate” data

1. That’s it, you’ve created an application with business objects that may be accessed using REST APIs like those used in exercise 4

[Return to Appendix list](#appendix)
[Return to Table of Contents](#table-of-contents)
[Return to Main Page](README.md)