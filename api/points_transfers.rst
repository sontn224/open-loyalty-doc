Points transfers
================

These endpoints will allow you to easily manage Points transfers.


Get a complete list of Points transfers
---------------------------------------

To retrieve a paginated list of Points transfers you need to call the ``/api/points/transfer`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/points/transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| customerFirstName                   | query          | *(optional)* First Name                           |
+-------------------------------------+----------------+---------------------------------------------------+
| customerLastName                    | query          | *(optional)* Last Name                            |
+-------------------------------------+----------------+---------------------------------------------------+
| customerPhone                       | query          | *(optional)* Customer Phone                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerEmail                       | query          | *(optional)* Customer Email                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerId                          | query          | *(optional)* Customer ID                          |
+-------------------------------------+----------------+---------------------------------------------------+
| state[]                             | query          | *(optional)* Possible values: active, expired     |
+-------------------------------------+----------------+---------------------------------------------------+
| type                                | query          | *(optional)* Possible values: adding, spending,   |
|                                     |                | p2p_adding, p2p_spending                          |
+-------------------------------------+----------------+---------------------------------------------------+
| page                                | query          | *(optional)* Start from page, by default 1        |
+-------------------------------------+----------------+---------------------------------------------------+
| perPage                             | query          | *(optional)* Number of items to display per page, |
|                                     |                | by default = 10                                   |
+-------------------------------------+----------------+---------------------------------------------------+
| sort                                | query          | *(optional)* Sort by column name                  |
+-------------------------------------+----------------+---------------------------------------------------+
| direction                           | query          | *(optional)* Direction of sorting [ASC, DESC],    |
|                                     |                | by default = ASC                                  |
+-------------------------------------+----------------+---------------------------------------------------+


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
        "transfers": [
            {
                "pointsTransferId": "ae1c49b1-02ab-4626-982d-71b544b01136",
                "accountId": "49a218ab-71ba-4f7f-8f4e-407df5f84b11",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
                "customerFirstName": "John",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "47834433524",
                "customerEmail": "user@example.com",
                "customerPhone": "+48234234000",
                "createdAt": "2018-09-13T16:37:33+0200",
                "expiresAt": "2018-10-13T16:37:33+0200",
                "value": 10,
                "state": "active",
                "type": "adding",
                "comment": "Event - First Purchase - 10",
                "issuer": "system"
            },
            {
                "pointsTransferId": "cd470d77-a08e-4c62-9f47-da180524f683",
                "accountId": "49a218ab-71ba-4f7f-8f4e-407df5f84b11",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
                "customerFirstName": "John",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "47834433524",
                "customerEmail": "user@example.com",
                "customerPhone": "+48234234000",
                "createdAt": "2018-09-13T16:37:33+0200",
                "expiresAt": "2018-10-13T16:37:33+0200",
                "value": 6.9,
                "state": "active",
                "type": "adding",
                "transactionId": {
                    "transactionId": "00000000-0000-1111-0000-000000000003"
                },
                "comment": "General spending rule - 2.3",
                "issuer": "system",
                "transactionDocumentNumber": "456",
                "transaction": {
                    "grossValue": 3,
                    "items": [
                        {
                            "sku": {
                                "code": "SKU1"
                            },
                            "name": "item 1",
                            "quantity": 1,
                            "grossValue": 1,
                            "category": "aaa",
                            "labels": [
                                {
                                    "key": "test",
                                    "value": "label"
                                },
                                {
                                    "key": "test",
                                    "value": "label2"
                                }
                            ],
                            "maker": "sss"
                        },
                        {
                            "sku": {
                                "code": "SKU2"
                            },
                            "name": "item 2",
                            "quantity": 2,
                            "grossValue": 2,
                            "category": "bbb",
                            "labels": [],
                            "maker": "ccc"
                        }
                    ]
                }
            }
        ],
        "total": 2
    }


Get a complete list of Points transfers (seller)
------------------------------------------------

To retrieve a paginated list of Points transfers you need to call the ``/api/seller/points/transfer`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/seller/points/transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| customerFirstName                   | query          | *(optional)* First Name                           |
+-------------------------------------+----------------+---------------------------------------------------+
| customerLastName                    | query          | *(optional)* Last Name                            |
+-------------------------------------+----------------+---------------------------------------------------+
| customerPhone                       | query          | *(optional)* Customer Phone                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerEmail                       | query          | *(optional)* Customer Email                       |
+-------------------------------------+----------------+---------------------------------------------------+
| customerId                          | query          | *(optional)* Customer ID                          |
+-------------------------------------+----------------+---------------------------------------------------+
| state                               | query          | *(optional)* Possible values: active, expired,    |
|                                     |                | pending                                           |
+-------------------------------------+----------------+---------------------------------------------------+
| type                                | query          | *(optional)* Possible values: adding, spending    |
+-------------------------------------+----------------+---------------------------------------------------+
| page                                | query          | *(optional)* Start from page, by default 1        |
+-------------------------------------+----------------+---------------------------------------------------+
| perPage                             | query          | *(optional)* Number of items to display per page, |
|                                     |                | by default = 10                                   |
+-------------------------------------+----------------+---------------------------------------------------+
| sort                                | query          | *(optional)* Sort by column name                  |
+-------------------------------------+----------------+---------------------------------------------------+
| direction                           | query          | *(optional)* Direction of sorting [ASC, DESC],    |
|                                     |                | by default = ASC                                  |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/seller/points/transfer \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.


Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
        "transfers": [
            {
                "pointsTransferId": "cd470d77-a08e-4c62-9f47-da180524f683",
                "accountId": "49a218ab-71ba-4f7f-8f4e-407df5f84b11",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
                "customerFirstName": "John",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "47834433524",
                "customerEmail": "user@example.com",
                "customerPhone": "+48234234000",
                "createdAt": "2018-09-13T16:37:33+0200",
                "expiresAt": "2018-10-13T16:37:33+0200",
                "value": 6.9,
                "state": "active",
                "type": "adding",
                "transactionId": {
                    "transactionId": "00000000-0000-1111-0000-000000000003"
                },
                "comment": "General spending rule - 2.3",
                "issuer": "system",
                "transactionDocumentNumber": "456",
                "transaction": {
                    "grossValue": 3,
                    "items": [
                        {
                            "sku": {
                                "code": "SKU1"
                            },
                            "name": "item 1",
                            "quantity": 1,
                            "grossValue": 1,
                            "category": "aaa",
                            "labels": [
                                {
                                    "key": "test",
                                    "value": "label"
                                },
                                {
                                    "key": "test",
                                    "value": "label2"
                                }
                            ],
                            "maker": "sss"
                        },
                        {
                            "sku": {
                                "code": "SKU2"
                            },
                            "name": "item 2",
                            "quantity": 2,
                            "grossValue": 2,
                            "category": "bbb",
                            "labels": [],
                            "maker": "ccc"
                        }
                    ]
                }
            },
            {
                "pointsTransferId": "e82c96cf-32a3-43bd-9034-4df343e5f333",
                "accountId": "cdcc55e9-cfab-4840-991d-0e0f25ba2141",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e2",
                "customerFirstName": "Jane",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "0000",
                "customerEmail": "user-temp@example.com",
                "customerPhone": "+48345345000",
                "createdAt": "2018-09-13T16:37:35+0200",
                "expiresAt": "2018-09-13T16:37:35+0200",
                "value": 100,
                "state": "active",
                "type": "spending",
                "comment": "Example comment",
                "issuer": "system"
            }
        ],
        "total": 2
    }



Get a complete list of points transfers (customer)
--------------------------------------------------

To retrieve a paginated list of Points transfers you need to call the ``/api/customer/points/transfer`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET  /api/customer/points/transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| state                               | query          | *(optional)* Possible values: active, expired,    |
|                                     |                | pending                                           |
+-------------------------------------+----------------+---------------------------------------------------+
| type                                | query          | *(optional)* Possible values: adding, spending    |
+-------------------------------------+----------------+---------------------------------------------------+
| page                                | query          | *(optional)* Start from page, by default 1        |
+-------------------------------------+----------------+---------------------------------------------------+
| perPage                             | query          | *(optional)* Number of items to display per page, |
|                                     |                | by default = 10                                   |
+-------------------------------------+----------------+---------------------------------------------------+
| sort                                | query          | *(optional)* Sort by column name                  |
+-------------------------------------+----------------+---------------------------------------------------+
| direction                           | query          | *(optional)* Direction of sorting [ASC, DESC],    |
|                                     |                | by default = ASC                                  |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/customer/points/transfer \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
        "transfers": [
            {
                "pointsTransferId": "ae1c49b1-02ab-4626-982d-71b544b01136",
                "accountId": "49a218ab-71ba-4f7f-8f4e-407df5f84b11",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
                "customerFirstName": "John",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "47834433524",
                "customerEmail": "user@example.com",
                "customerPhone": "+48234234000",
                "createdAt": "2018-09-13T16:37:33+0200",
                "expiresAt": "2018-10-13T16:37:33+0200",
                "value": 10,
                "state": "active",
                "type": "adding",
                "comment": "Event - First Purchase - 10",
                "issuer": "system"
            },
            {
                "pointsTransferId": "cd470d77-a08e-4c62-9f47-da180524f683",
                "accountId": "49a218ab-71ba-4f7f-8f4e-407df5f84b11",
                "customerId": "00000000-0000-474c-b092-b0dd880c07e1",
                "customerFirstName": "John",
                "customerLastName": "Doe",
                "customerLoyaltyCardNumber": "47834433524",
                "customerEmail": "user@example.com",
                "customerPhone": "+48234234000",
                "createdAt": "2018-09-13T16:37:33+0200",
                "expiresAt": "2018-10-13T16:37:33+0200",
                "value": 6.9,
                "state": "active",
                "type": "adding",
                "transactionId": {
                    "transactionId": "00000000-0000-1111-0000-000000000003"
                },
                "comment": "General spending rule - 2.3",
                "issuer": "system",
                "transactionDocumentNumber": "456",
                "transaction": {
                    "grossValue": 3,
                    "items": [
                        {
                            "sku": {
                                "code": "SKU1"
                            },
                            "name": "item 1",
                            "quantity": 1,
                            "grossValue": 1,
                            "category": "aaa",
                            "labels": [
                                {
                                    "key": "test",
                                    "value": "label"
                                },
                                {
                                    "key": "test",
                                    "value": "label2"
                                }
                            ],
                            "maker": "sss"
                        },
                        {
                            "sku": {
                                "code": "SKU2"
                            },
                            "name": "item 2",
                            "quantity": 2,
                            "grossValue": 2,
                            "category": "bbb",
                            "labels": [],
                            "maker": "ccc"
                        }
                    ]
                }
            }
        ],
        "total": 2
    }



Add points to customer's account
--------------------------------

To add points you need to call the ``/api/points/transfer/add`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/add

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer/add \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[customer]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[points]=9"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "32132863-3d1e-4a94-8bb4-6e42e3c96c0b"
    }



Spend customer's points
-----------------------

To spend customer's points you need to call the ``/api/points/transfer/spend`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/spend

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer/spend \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[customer]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[points]=1"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "b97a31fe-9bc9-4fff-a467-487f2c316371"
    }



Transfer points between customers (admin)
-----------------------------------------

To transfer points between customers you need to call the ``/api/admin/p2p-points-transfer`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/admin/p2p-points-transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[sender]                    | query          | email/phone or uuid of customer from whom points  |
|                                     |                | will be transferred                               |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[receiver]                  | query          | email/phone or uuid of customer who will get      |
|                                     |                | points                                            |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points will be transferred               |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/admin/p2p-points-transfer \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[sender]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[receiver]=b9af6a8c-9cc5-4924-989c-e4af614ab3c5" \
        -d "transfer[points]=100"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "b97a31fe-9bc9-4fff-a467-487f2c316371"
    }

.. note::

    Returned pointsTransferId is a UUID of the P2P spend points transfer created.



Transfer points between customers (customer)
--------------------------------------------

To transfer points between logged in customer and another customer you need to call the ``/api/customer/points/p2p-transfer`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/customer/points/p2p-transfer

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[receiver]                  | query          | email/phone or uuid of customer who will get      |
|                                     |                | points                                            |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points will be transferred               |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/customer/points/p2p-transfer \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[receiver]=b9af6a8c-9cc5-4924-989c-e4af614ab3c5" \
        -d "transfer[points]=100"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "b97a31fe-9bc9-4fff-a467-487f2c316371"
    }

.. note::

    Returned pointsTransferId is a UUID of the P2P spend points transfer created.



Cancel specific points transfer
-------------------------------

To cancel specific points transfer you need to call the ``/api/points/transfer/<transfer>/cancel`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/<transfer>/cancel

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| <transfer>                          | query          | Points transfer ID                                |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer/313cf0c1-5376-4f66-9de3-77943760423a/cancel \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    (no content)



Import transfers points
-----------------------

To import file with points transfer you need to call the ``/api/points/transfer/import`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/import

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| file[file]                          | query          | XML file                                          |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer/import \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "file[file]=C:\\fakepath\\points.xml"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "items": [
        {
          "status": "success",
          "processImportResult": {
            "object": {
              "pointsTransferId": "e08cf828-989b-4bd0-8221-cf44c3be8a64"
            }
          },
          "identifier": "11000000-0000-474c-b092-b0dd880c07e2x/(adding 15)"
        }
      ],
      "totalProcessed": 1,
      "totalSuccess": 1,
      "totalFailed": 0
    }



Add points to customer's account (seller)
-----------------------------------------

To add points to a customer's account as seller you need to call the ``/api/pos/points/transfer/add`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/pos/points/transfer/add

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[validityDuration]          | query          | *(optional)* Validity of points given in days     |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer                            | query          | *(optional)* Points transfer ID                   |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/pos/points/transfer/add \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[customer]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[points]=10"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "481b60c5-ccba-4ce9-9b40-2567513cb555"
    }



Spend customer points (seller)
------------------------------

To spend customer points as seller you need to call the ``/api/pos/points/transfer/spend`` endpoint with the ``POST`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/pos/points/transfer/spend

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points customer can get                  |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[validityDuration]          | query          | *(optional)* Validity of points given in days     |
+-------------------------------------+----------------+---------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/pos/points/transfer/spend \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[customer]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[points]=1"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "ff4698aa-5d3b-4b58-952e-90d08fe94e30"
    }

Points transfers histogram
--------------------------

To get information about points transfers histogram you need to call the
``/api/points/transfers`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET /api/points/transfers

+------------------------------------+----------------+----------------------------------------------------------------+
| Parameter                          | Parameter type |  Description                                                   |
+====================================+================+================================================================+
| Authorization                      | header         | Token received during authentication                           |
+------------------------------------+----------------+----------------------------------------------------------------+
| <interval>                         | request        | Group result by (day|month|year)                               |
+------------------------------------+----------------+----------------------------------------------------------------+
| <lastDays>                         | request        | Display data in last days                                      |
+------------------------------------+----------------+----------------------------------------------------------------+
| <futureDays>                       | request        | Display data to X future days                                  |
+------------------------------------+----------------+----------------------------------------------------------------+
| <storeCode>                        | request        | Filter result by given store                                   |
+------------------------------------+----------------+----------------------------------------------------------------+
| <pointType>                        | request        | Type of point (earned, spent, expired, pending)                |
+------------------------------------+----------------+----------------------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfers \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "2018-01-06": 0,
      "2018-01-07": 0,
      "2018-01-08": 0,
      "2018-01-09": 5,
      "2018-01-10": 0,
      "2018-01-11": 5,
      "2018-01-12": 4,
      "2018-01-13": 3,
      "2018-01-14": 0,
      "2018-01-15": 0,
      "2018-01-16": 3,
      "2018-01-17": 0,
      "2018-01-18": 5,
      "2018-01-19": 0,
      "2018-01-20": 6,
      "2018-01-21": 5,
      "2018-01-22": 0,
      "2018-01-23": 6,
      "2018-01-24": 0,
      "2018-01-25": 0,
      "2018-01-26": 0,
      "2018-01-27": 0,
      "2018-01-28": 5,
      "2018-01-29": 0,
      "2018-01-30": 0,
      "2018-01-31": 0,
      "2018-02-01": 0,
      "2018-02-02": 5,
      "2018-02-03": 0,
      "2018-02-04": 0
    }



Block points to customer's account
----------------------------------

Administrator can block points to customer's account in order prevent to spend it. To block points you need to
call ``/api/points/transfer/block`` endpoint with the ``POST`` method. In order to unblock points you need to
use ``/api/points/transfer/<transfer>/cancel`` endpoint.

Definition
^^^^^^^^^^

.. code-block:: text

    POST /api/points/transfer/block

+-------------------------------------+----------------+---------------------------------------------------+
| Parameter                           | Parameter type | Description                                       |
+=====================================+================+===================================================+
| Authorization                       | header         | Token received during authentication              |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[customer]                  | query          | Customer ID                                       |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[points]                    | query          | How many points to block                          |
+-------------------------------------+----------------+---------------------------------------------------+
| transfer[comment]                   | query          | *(optional)* Comment                              |
+-------------------------------------+----------------+---------------------------------------------------+


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/points/transfer/block \
        -X "POST" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..." \
        -d "transfer[customer]=b9af6a8c-9cc5-4924-989c-e4af614ab2a3" \
        -d "transfer[points]=9"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value can be different. Read more about Authorization :doc:`here </api/authorization>`.

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    {
      "pointsTransferId": "32132863-3d1e-4a94-8bb4-6e42e3c96c0b"
    }

