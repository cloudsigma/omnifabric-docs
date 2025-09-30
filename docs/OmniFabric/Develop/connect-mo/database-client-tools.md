# Connecting to OmniFabric with Database Client Tool

OmniFabric now supports the following Database client tools:

- MySQL Client

- Navicat

- DBeaver

## Before you start

Make sure you have already [installed and launched OmniFabric](../../Get-Started/basic-sql.md).

## Connect to the OmniFabric Server through MySQL Client

1. Download and install [MySQL Client](https://dev.mysql.com/downloads/installer/).

2. Connect to the OmniFabric server.

    You can use the MySQL command-line client to connect to OmniFabric server:

    ```
    mysql -h IP -P PORT -uUsername -p
    ```

    The connection string is the same format as MySQL accepts. You need to provide a user name and a password.

    Use the built-in test account for example:

    - user: root

    - password: 111

    ```
    mysql -h 127.0.0.1 -P 6001 -uroot -p
    Enter password:
    ```

    !!! info
    The login account in the above code snippet is the initial account; please change the initial password after logging in to OmniFabric; see .

    The successful result is as below:

    ```
    Welcome to the MySQL monitor. Commands end with ; or \g. Your MySQL connection id is 1031
    Server version: 8.0.30-OmniFabric-v2.1.0 OmniFabric
    Copyright (c) 2000, 2022, Oracle and/or its affiliates.

    Oracle is a registered trademark of Oracle Corporation and/or its affiliates. Other names may be trademarks of their respective owners.
    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
    ```

For more information on deployment, see .

!!! note
    OmniFabric and the client use non-encrypted transmission by default. Refer to  to enable encrypted transmission.

## Connect to the OmniFabric Server through Navicat

1. Open a new terminal and enter into the following command:

    ```
    #Launch OmniFabric (Source code method)
    ./mo-service -launch ./etc/launch/launch.toml
    ```

2. Download and install [Navicat](https://www.navicat.com/en/products).

3. Open Navicat, click **Connection > MySQL**, and fill in the following parameters in the pop-up window:

    - **Connction Name**: OmniFabric

    - **Host**: 127.0.0.1

    - **Port**: 6001

    - **User Name**: root

    - **Password**: 111

    - **Save password**:Yes

4. Click **Save**, save the configuration.


5. To connect to the OmniFabric server, double-click **OmniFabric** in the database directory on the left.

6. Once you connect to OmniFabric, you will see 6 default system databases.


    And on the right you will see the information about this connection.


## Connect to the OmniFabric Server through DBeaver

1. Download and install [DBeaver](https://dbeaver.io/download/).

2. Open DBeaver, click **Connection**, select **MySQL**, then click **Next**.


    Fill in the following parameters in the pop-up window. Click **Finish**, save the configuration.

    - **Host**: 127.0.0.1

    - **Port**: 6001

    - **Database**: OmniFabric

    - **User Name**: root

    - **Password**: 111

    - **Save password locally**: Yes


3. To connect to the OmniFabric server, double-click **OmniFabric** in the database navigation on the left. You will see the four default system databases.


4. By default, views are not appearing in DBeaver. To show complete system databases, you need to right click on the **MatrxiOne**, select on **Connection view** and toggle on the **Show system objects**.


    Then you can see full 6 system databases.

