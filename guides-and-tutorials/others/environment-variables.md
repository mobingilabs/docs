# Environment variables

In Mobingi ALM, the information of each resource is automatically set to environment variables according to the stack you made. You no longer need to check individual settings such as RDS or ElastiCache. If you just set the environment variable in your code, you can use it immediately from the application.

You can also set your own environment variables.

## Default environment variables

We automatically set the following environment variables to your container according to the stack you made.

**Case: RDS \(MySQL, PostgreSQL\)**

* `MO_DATABASE_NAME`: The database name.
* `MO_DATABASE_USERNAME`: The database username.
* `MO_DATABASE_PASSWORD`: The database password.
* `MO_DATABASE_PORT`: The port number.
* `MO_DATABASE_HOST`: The master address.
* `MO_DATABASE_SLAVE1_HOST`, `MO_DATABASE_SLAVE2_HOST`... : The slave address \(number of slaves\).
* `MO_DATABASE_SLAVE_HOSTGROUP`: The slave address group \(output slave addresses in comma-delimited format\).

**Case: Redis**

* `MO_REDIS_ENDPOINT`: The primary endpoint.
* `MO_REDIS_NODE1_ENDPOINT`, `MO_REDIS_NODE2_ENDPOINT`... : The node endpoint \(number of nodes\).
* `MO_REDIS_NODE_ENDPOINTGROUP`: The nodes endpoint group \(output node addresses in comma-delimited format\).
* `MO_REDIS_PORT`: The redis port.

**Case: Memcached**

* `MO_MEMCACHED_ENDPOINT`: The configuration endpoint.
* `MO_MEMCACHED_PORT`: The memcached port.

## Defining your environment variables

After creating the stack, you can set environment variables from the stack Settings.

Click the save button to launch the new container. When switching from the old container to the new container is completed, the input environment variables can be used.

![](../../.gitbook/assets/environment-variables-en.png)

