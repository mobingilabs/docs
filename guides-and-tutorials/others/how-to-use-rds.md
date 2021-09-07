# How to use RDS

## How to use RDS

If you choose AWS as cloud vender when using Mobingi ALM, you can deploy RDS \(MySQL, PostgreSQL\) within application stack.

## Deploy RDS

Choose AWS as cloud vender when stack creation.

![](../../.gitbook/assets/rds-vender.png)

This time, click MySQL. The process when choose PostgreSQL would be almost same, so you can choose PostgreSQL as well.

![](../../.gitbook/assets/rds-mysql_postgresql.png)

After specify MySQL DB instance type, storage volume, and read replicas, click Choose button.

![](../../.gitbook/assets/rds-mysql_open.png)

After MySQL value setup, click Create Application button.

![](../../.gitbook/assets/rds-mysql_set.png)

## Check RDS details

From Stack Details page, click DB Address\(master\).

![](../../.gitbook/assets/rds-check%20%281%29%20%281%29%20%281%29.png)

You can check the connection information of RDS（MySQL・PostgreSQL）

![](../../.gitbook/assets/rds-check_detail.png)

As default, DB Username and DB Password are hided. By mouse click, you can check them.

![](../../.gitbook/assets/rds-check_detail_dbname%20%281%29.png)

