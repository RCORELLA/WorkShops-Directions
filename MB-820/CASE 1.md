Case study -

This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.

To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.

At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.

To start the case study -

To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.

**Company Background**

Alpine Ski House is a company that owns and operates hotels, restaurants, and stores. Currently, the company uses the following software and interface:

Property management software (PMS) to manage hotel rooms

On-premises accounting software to generate sales invoices and create purchase orders

An API that allows restaurants and stores to obtain necessary information

Restaurants and stores use standalone software for point-of-sale (POS) devices. Each day, the POS terminals generate a text file of sales data and save the files in a server folder. An account assistant must manually import the files to the current software tables to be processed by the system.

The general manager receives several reports monthly from department managers. The reports take too much time to prepare.

**Planned improvements**

The company is moving from a different system to Business Central online to manage the whole company.

The company plans to increase efficiency in every department by using APIs to obtain or share information between the different systems.

Each department involved in purchasing must be able to make purchase requests automatically and easily. The departments do not need access to the full ERP management system.

**Technical specifications**

Alpine Ski House requires the development of several extensions for the planned improvements. Business Central design patterns must be used to develop all extensions.

Alpine Ski House must develop the following pages:

- Pages that provide multiple configurations in a multistep dialog, like a wizard, to provide the required information when the extensions are first installed

- Department-specific Role Center pages to show relevant information and pages with additional information

The IT department plans to use Power BI to analyze departmental information. The database must be configured to provide optimal performance.

Department-specific requirements. 

**Housekeeping department**

The housekeeping department requires the following to increase efficiency and help avoid data entry errors:

A Housekeeping Role Center to minimize navigation to relevant areas in Business Central online and to show relevant information in it

Pages to embed into a new Room page to show additional information about the Room entity

A table named Room Incident for the housekeeping team to enter room issue information

A Housekeeping canvas app that connects to an extension

The department requires the development of an extension with a new API page named RoomsAPI.

The housekeeping team will use RoomsAPI to publish room details, update when work is complete, or provide repair notifications from the canvas app.

This custom API page must expose a custom table named Rooms and have an ID 50000. The table must be able to be updated from the PMS. The PMS team must know the endpoint to connect to the custom API.

A developer provides the following details for the API page:

image27

The extension must be published in Business Central online and include a list page named Room List that includes all hotel rooms.

Installation or updates to this extension must meet the following requirements:

Some web services must be published automatically.

The version of the specified application's metadata must be obtained in AL language,

The code required to perform tasks cannot be accessible from other parts of the application.

The Room Incident table information must include the following fields:

Incident entry: An incremental number

Room No.: A room from the Room table

Incident Date: The work date -

The table definition in the Room Incident table must autofill the Incident Date when the housekeeping team inserts a new record,

The value for the Incident Date must be the work date configured in the Business Central online client.

Status: Includes the following options to identify the status of the incident:

  **Open**: When the Room Incident is created

  **In Progress**: When someone starts repair work

  **Closed**: When the incident is solved

Incident Closing Date: Auto-updating field (when the status passes to Closed, the field will update with the work date)

Incident Description: Text -

Image: Media data type -

The stored picture must be downloadable from a menu action,

A Room Incident page must be developed to contain the download action.

Department-specific requirements. Restaurants and stores

To increase efficiency, the new system must manage the generated data from the restaurants and stores directly by using the API on the POS terminals.

The company requires a codeunit called from a job queue to read the information from the POS terminal APIs.

The POS terminal information must be stored in a table named POS Information, have an ID 50100, and be editable on a page.

The account manager requires an option on the menu of the page to run the process manually.

To analyze the information received from the POS terminals, the company requires:

A custom API named ticketAPI to export the information to Power BI

Use of the Read Scale-Out feature to improve database performance

Department-specific requirements. Purchasing department and non-conformity handling

The purchasing department requires a new entity in Business Central online to log non-conformities of goods received from vendors. The entity must be set up as follows:

The non-conformity entity must have two tables:

a header with common information

one or more lines with the detailed received items that are non-conforming

The entity requires a page named Non-conformity and a subpage named Non-conformity Lines to store the information.

When a purchase order with incorrect quantity or quality issues is received, the entity must create a non-conformity document in the system. The following information must be included in the document:

Non-conformity Number: must use the No. Series table from Business Central online to manage this field and use these features:

Alphanumeric values -

Number format that includes **NC** and the year as part of the number; for example, NC24-001

Non-conformity Date: stores only the creation date

Vendor No.: stores the number of the vendor that sent the items; only vendors from the company must be included

Owner: code of an employee defined in the company

Receipt No.: must meet the following conditions:

Be an existing receipt No.

Be received from the vendor indicated in the Vendor No. field

Comments: can include comments with rich text and pictures to illustrate quality problems

Status: includes non-conformity statuses, such as:

Open -

Notified -

Closed -

Lines must contain the following details:

Item No.: item received (for existing inventory items only)

Description: item description -

Quantity: non-conforming quantity

Non-conformity Type:

Quality -

Quantity -

Delivery date -

The serial numbers of the non-conformities and the period in which they can be created must be in a configuration table and its corresponding page to allow them to be modified for the users.
