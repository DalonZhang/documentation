==========================
Invoice project milestones
==========================

.. |SO| replace:: :abbr:`SO (Sales Order)`
.. |SOs| replace:: :abbr:`SOs (Sales Orders)`

Invoicing based on project milestones allows companies to bill large or long-running projects
progressively as key deliverables are completed. Each milestone represents a measurable stage of
work whose completion triggers invoicing. This approach helps maintain predictable cash flow and
gives customers visibility into project progress, while allowing payment to occur in manageable
installments.

In Odoo, milestone invoicing is configured at the product level in the **Sales** app, with milestone
progress and completion managed in the **Projects** app. When a milestone is marked as reached, the
delivered quantity on the sales order (SO) is updated and can be invoiced.

.. important::
   This document covers the **Sales** app configuration and invoicing flow for invocing based on
   project milestones. For more information on creating, managing, and completing milestones, and
   how to link them to tasks, see :doc:`Project milestones
   <../../../services/project/project_management/project_milestones>`.

Create milestone products
=========================

Milestones are tied to individual sales order items. Each milestone corresponds to one product line
that uses the :guilabel:`Based on Milestones` invoicing policy.



.. seealso::
   - :doc:`time_materials`
   - :doc:`proforma`
   - :doc:`invoicing_policy`
