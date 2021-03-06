.. index::
   single: referred_customers

Referred customers
==================

Referral (refer a friend, member get member) functionality allows to reward Customers for invitation other Customers to Loyalty program. It allows to give prize either referrer (Customer who sent invitation) and recipient (Customer who responded with action to invitation). 

Administrator can view all invitations sent by customer with current status: 

- **Invited**  
   invitation was sent by referrer to the recipient on their email address (Heads up: OL can be configured not to send invitation emails)

- **Registered** 
   referred customer (recipient) registered new account in Open Loyalty

- **Made purchase** 
   referred customer (recipient) made first purchase in Open Loyalty 

.. image:: /userguide/_images/referred_customers.png
   :alt:   Referred customers


To see all customers who sent and received invitation:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. On the Admin sidebar, tap **Customers**. Then choose **Referred customers**. 

Columns description
*******************

+------------------+-----------------------------------------------------------------------+
| COLUMN           | DESCRIPTION                                                           |
+==================+=======================================================================+
| Referrer Id      | The customer ID of a registered customer, who send invitation         |
+------------------+-----------------------------------------------------------------------+
| Referrer Name    | The name and surname of a registered customer                         |                              
+------------------+-----------------------------------------------------------------------+
| Recipient Id     | The customer ID of a referred person.                                 |
|                  | Will be shown when referred customer will register                    |
+------------------+-----------------------------------------------------------------------+
| Recipient Name   | The name and surname of a referred person.                            |
|                  | Will be shown when referred customer will register                    |
+------------------+-----------------------------------------------------------------------+
| Recipient Email  | The email address of an invitation recipient if set.                  |
+------------------+-----------------------------------------------------------------------+
| Recipient Phone  | The phone number of an invitation recipient if set.                   |
+------------------+-----------------------------------------------------------------------+
| Status           | Options include: invited/registered/made purchase                     |
+------------------+-----------------------------------------------------------------------+

