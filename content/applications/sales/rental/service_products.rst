================
Service products
================

The **Rental** app is a comprehensive tool that enables users to manage the scheduling, pricing, and
inventory for both physical goods and non-physical services within a single platform. This
flexibility allows for combining items like bike rentals with guided tours, or booking a studio with
a photographer.

The app supports seamless integration with other Odoo applications, allowing users to configure
service products with various functionalities, such as generating event registrations and
synchronizing staffing shifts directly upon a sale order creation.

Settings
========

To configure default settings on rental products, navigate to :menuselection:`Reantal app -->
Configuration --> Settings`.

.. image:: service_products/
   :alt: Add alt text.

In the :guilabel:`Rental` section, under the :guilabel:`Default Delay Costs` subsection, fill in the
:guilabel:`Apply after` field.

.. note::
   For finer control, configure the costs of late returns for the :guilabel:`Per Hour` and
   :guilabel:`Per Day` fields at the product level. If the defaults apply to all products, leave the
   :guilabel:`Product` field blank.

In the :guilabel:`Default Padding Time` section, fill in the :guilabel:`Padding` field.

Next, enable :guilabel:`Rental Transfers`. In the :guilabel:`Rent Online` section, fill in the
:guilabel:`Minimal Rental Duration` field and designate :guilabel:`Unavailability days`. Click
:guilabel:`Save` to apply the changes.

App integration configuration
=============================

To allow for workflow efficiency and automation when creating a service product and rental order,
the following Odoo apps and configuration are reccomended.

Project app settings
--------------------

Install the **Project** app and enable :guilabel:`Project stages` and :guilabel:`Timesheets`. Refer
to the :doc:`Project management <../services/planning>`  page for more information.

Planning app settings
---------------------

Install the **Planning** app and configure employee shifts and roles. Refer to the :doc:`Project
management <../services/planning>`  for instructions on setting up your employees and shifts.

Sales app settings
------------------

Install the Sales app. Navigate to :menuselection:`Sales app  --> Configuration --> Settings`. In
the :guilabel:`Quotations & Orders` section, tick the :guilabel:`Online Signature`,
:guilabel:`Online Payment`, and :guilabel:`Quotation Templates` checkboxes.

In the :guilabel:`Default Template` field, click the :guilabel:`Quotation templates` to customize
quotation templates to use.

Sign app settings
-----------------

Install the **Sign** app. Refer to the :doc:`Sign <../productibity/sign>` page for instructions on
uploading a rental agreement for the business to use.

Rental services
===============

To view all products that can be rented in the database, navigate to ::menuselection:`Rentals app
--> Products`. By default, the :guilabel:`Rental` filter appears in the search bar, and the view is
Kanban. Remove the filter, then click the search bar. From the preset filters, select
:guilabel:`Services`. All the configured services appear.

Each Kanban card displays the name and rental price of the service.

Create a new service product
============================

To set up a new rental service, go to the ;:menuselection:`Rental app --> Products` and then click
:guilabel:`New`. In the new product window, the :guilabel:`Rental` checkbox is already ticked by
default.

[insert]

Tick the :guilabel:`Sales` checkbox to enable the :guilabel:`Create on Order` and
:guilabel:`Invoicing Policy` fields. Select the :guilabel:`Product Type` as a :guilabel:`Service`.

In the :guilabel:`Create on Order` dropdown menu, select :guilabel:`Project & Task`.

.. important::
   The **Project** and the **Sales** apps must be installed for the :guilabel:`Project & Task`
   option and the :guilabel:`Project Template` field to be available.

In the :guilabel:`Invoicing Policy` drop-down menu, select :guilabel:`Based on Timesheets`.

Tick the :guilabel:`Plan Services` checkbox and either create a new role or select a pre-existing
one. To create a new role, type in the name of the role in the blank field and click
:guilabel:`Create and edit`that appears.

In the :guilabel:`Create Planning Role` pop-up window, enter the role's name. Select an option for
the :guilabel:`Services` and :guilabel:`Resources`, and click :guilabel:`Save`.


[image]

Click the :guilabel:`Rental prices` tab and in the :guilabel:`Pricing` section, click :guilabel:`Add
a price` to enter a new rental rate. Choose a *pricing period* (:dfn:`the unit of duration of the
rental`) in the Period column, or create a new pricing period by typing in the name and clicking
Create and edit.

.. tip::
   Customize rental rate time periods by navigating to  ::menuselection:`Rental app -->
   Configuration --> Rental periods`.

Next, enter the :guilabel:`Price` for that specific :guilabel:`Period`. To apply the configured
rental rate to an existing pricelist, click in the :guilabel:`Pricelist` column and select the
desired list from the drop-down menu.

In the :guilabel:`Reservations` section, fill in the :guilabel:`Hourly Fine`, :guilabel:`Daily
Fine`, and the :guilabel:`Reserve product` time. These values are automatically populated from the
:guilabel:`Default Delay Costs` section, provided they have been configured in the
::menuselection:`Rental app --> Configuration --> Settings`.

Click the :icon:`fa-cloud-upload` :guilabel:`(Save manually)` icon near the top to save.

Create a rental order with a service product
============================================

Go to Rental app > opens the Rental Orders dashboard.
Click New, enter the Customer field, and select a Quotation Template, if applicable.

Next, set the desired rental duration in the Rental period field. To adjust the rental duration,
click the first date in the Rental period field, and select the range of dates and times to
represent the rental duration from the pop-up calendar form that appears.

Once complete, click Apply in the calendar pop-up form. Following that, the pop-up form disappears,
and the designated time period of the rental is represented in the Duration field.

Next, add a rental service in the Order Lines tab, by clicking Add a product and selecting the
desired rental service to add to the form. Enter the desired amount in the Quantity column.

Note: If a rental product is added before the Rental period field has been properly configured, the
user can still adjust the Rental period field accordingly.

Select the desired range of dates to represent the duration of the rental, then click Update Rental
Prices in the Duration field.

The update rental prices option that appears in the Odoo Rental application. Doing so reveals a
Confirmation pop-up window. If everything is correct, click Ok, and Odoo recalculates the rental
price accordingly.

Note: The unit of measure for the Quantity column is automatically the same unit of measure
configured in the service product Rental prices tab.

Once all information has been entered correctly on the rental order form, click Send to send the
quotation to the customer. When the customer approves the quotation, click Confirm. A banner
displays on the rental order stating its current status.

At the top of the SO form, the Tasks, Recorded, and Planned smart buttons appear. Click the Tasks
smart button to view a Kanban view of all the associated Tasks that were automatically created.
Click the desired task, then select the Timesheets tab.

Click Add a line to enter the number of hours worked on the task manually. Click on the Sales Order
smart button to go back.

Customer signature
==================

Odoo allows you to request that the customer sign a
rental agreement outlining the arrangement between the company and the customer before they pick up
the rental products. Such documents can ensure everything is returned on-time and in its original
condition.

Note Requesting a signature can be done during any stage of the order. This feature also requires
the Sign app.

If signatures are required, go to the Rental app and from the default Rental Orders dashboard,
select the desired rental order. To go the  (Actions) icon, and click Request Signature.


A Sign Documents pop-up window displays. Select the desired document from the Template drop-down
menu.


Doing so reveals a New Signature Request pop-up window. Upon confirming the information in the New
Signature Request pop-up form, click Send to initiate the signing process.


A link to the signature request will appear in the record’s chatter. The document is accessible to
the customer via the customer portal or email.

When the customer clicks Sign document, a separate page is then revealed, showcasing the document to
be signed. The customer begins the process by clicking Click to start. The app guides the signee to
the required signature locations and allows them to create electronic signatures to complete the
form.

The adopt your signature pop-up window that appears in the Odoo Rental application. Once the
document has been signed and completed, click Validate & Send Completed Document at the bottom of
the document. Odoo presents the option to download the signed document for record-keeping purposes,
if necessary.

See also Odoo Tutorials: Sign

Pickup products
===============

When a customer picks up the product, navigate to the appropriate rental order, click the Pickup
button, and then click Validate in the Validate a pickup pop-up form that appears.

Doing so places a Picked-up status banner on the rental order.

Return products
===============

When a customer returns the products, navigate to the appropriate rental order, click the Return
button, and validate the return by clicking Validate in the Validate a return pop-up form that
appears.

Doing so places a Returned status banner on the rental order.








