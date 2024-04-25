==================
Avatax integration
==================

Avalara's *AvaTax* is a cloud-based tax software that delivers the latest sales and use
tax calculations to Odoo's sales and invoicing flow when the customer makes a purchase. *AvaTax* is
supported in every United Nations charted country. This includes inter-boarder transactions as well.

*AvaTax* accounts for geospatial tax rates for each state, county and city. It improves remittance
accuracy by paying close attention to laws, rules, jurisdiction boundaries, and special
circumstances like tax holidays and product exemptions. Companies who integrate with *AvaTax* can
maintain control of tax-calculations in-house with this simple :abbr:`API (application programming
interface)` integration.

Avalara account setup
=====================

To use *AvaTax*, an account with Avalara is required for the setup. If one has not been set up yet,
create one at `Avalara's Knowledge Center <https://knowledge.avalara.com/auth/register>`_.

.. seealso::
   For more information on configuring company information for *AvaTax* in Avalara's management
   console visit: `Set up AvaTax
   <https://knowledge.avalara.com/bundle/dqa1657870670369_dqa1657870670369/page/Set_up_AvaTax.html>`_

Initial Odoo setup
==================

Ensure that the company has data set up in the Odoo database. When the database or company is
initially set up, a country is set. This country sets the fiscal position and helps *Avatax*
calculate the correct tax rates.

.. seealso::
   Refer to this documentation for more information: :ref:`../fiscal_localizations` or
   :ref:`fiscal_positions`.

Next, ensure that the Odoo *Avatax* module is installed. To do so, navigate to :menuselection:`Apps
application --> Search...` bar and then type in `avatax`. Press enter and the following results will
populate:

- :guilabel:`Avatax`: `account_avatax``
- :guilabel:`Avatax for SO`: `account_avatax_sale`
- :guilabel:`Avatax for Subscriptions`: `account_avatax_sale_subscription`
- :guilabel:`Avatax Brazil`: `l10n_br_avatax`
- :guilabel:`Avatax for SOs in Brazil`: `l10n_br_avatax_sale`
- :guilabel:`Account Avatax - Ecommerce`: `website_sale_account_avatax`
- :guilabel:`Account AvaTax - Ecommerce - Delivery`: `website_sale_delivery_avatax`

Click on the :guilabel:`Install` button on the module labeled :guilabel:`Avatax`: `account_avatax`.
This will install the following modules:

- :guilabel:`Avatax`: `account_avatax``
- :guilabel:`Avatax for SO`: `account_avatax_sale`
- :guilabel:`Account Avatax - Ecommerce`: `website_sale_account_avatax`

Should *Avatax* be needed for Odoo *Subscriptions* or for delivery tax in Odoo *Ecommerce*, then
install those modules individually by clicking on :guilabel:`Install`. Additionally, in Brazil two
separate *AvaTax* modules need to be installed. See the list above for these modules.

Gather AvaTax credentials
=========================

.. _avatax/credentials:

Credential configuration in Odoo
================================

To integrate the *Avatax* :abbr:`API (application programming interface)` with Odoo, go to
:menuselection:`Accounting --> Configuration --> Settings --> Taxes --> Avatax` section. This where
the *AvaTax* credentials will be entered in.

.. tip::
   If you do not yet have credentials, click on :guilabel:`How to Get Credentials`.

.. image:: avatax/avatax-configuration-settings.png
   :align: center
   :alt: Configure Avatax settings

.. seealso::
   For help determining which *AvaTax* environment to use (either :guilabel:`Production` or
   :guilabel:`Sandbox`), visit: `Sandbox vs Production environments
   <https://knowledge.avalara.com/bundle/fzc1692293626742/page/sandbox-vs-production.html>`_.

.. _avatax/tax-mapping:

Tax mapping
===========

The Avatax integration is available on Sale Orders and Invoices with the included Avatax fiscal
position.

Before using the integration, specify an :guilabel:`Avatax Category` on the product categories.

.. image:: avatax/avatax-category.png
   :align: center
   :alt: Specify Avatax Category on products

Avatax Categories may be overridden or set on individual products as well.

.. image:: avatax/override-avatax-product-category.png
   :align: center
   :alt: Override product categories as needed

.. _avatax/address-mapping:

Address validation
==================

Manually validate customer addresses by clicking the :guilabel:`Validate address` link in the
customer form view.

.. image:: avatax/validate-customer-address.png
   :align: center
   :alt: Validate customer addresses

If preferred, choose to keep the newly validated address or the original address in the wizard that
pops up.

.. image:: avatax/choose-customer-address.png
   :align: center
   :alt: Address validation wizard

.. _avatax/tax-calculation:

Tax calculation
===============

Automatically calculate taxes on Odoo quotations and invoices with Avatax by confirming the
documents. Alternatively, calculate the taxes manually by clicking the :guilabel:`Compute taxes
using Avatax` button while these documents are in draft mode.

Use the :guilabel:`Avalara Code` field that's available on customers, quotations, and invoices to
cross-reference data in Odoo and Avatax.

.. seealso::
   - :doc:`fiscal_positions`
