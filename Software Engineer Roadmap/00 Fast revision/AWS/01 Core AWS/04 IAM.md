
# 10-Second Recall

> **IAM → User → Group → Role → Policy → Least Privilege → Authentication → Authorization**

---

# 60-Second Revision

**IAM**

- Identity and Access Management.
- Controls who can access AWS and what they can do.

**User**

- Permanent identity for a person.

**Group**

- Collection of users with shared permissions.

**Role**

- Temporary identity used by AWS services (like Lambda), applications, or users.

**Policy**

- JSON document defining Allow/Deny permissions.
```json
{
			"Action": [
				"s3:GetBucket*",
				"s3:GetObject*",
				"s3:List*"
			],
			"Resource": [
				"arn:aws:s3:::amx-pbi-de-us-east-1-123456789-glue-scripts",
				"arn:aws:s3:::amx-pbi-de-us-east-1-123456789-glue-scripts/*"
			],
			"Effect": "Allow"
		}
```


**Least Privilege**

- Grant only the minimum required permissions.

**Authentication**

- Verifies identity.

**Authorization**

- Verifies permissions.

**Project Example**

- Lambda assumed an IAM Role to access S3, DynamoDB, and CloudWatch securely without storing AWS credentials.

### Difference between User and Role?

**User**

- Permanent identity
- Used by people

**Role**

- Temporary identity
- Used by AWS services or applications
Note: one user can have multiple role
An IAM User can assume multiple IAM Roles if they have permission to do so. However, they typically assume only one role at a time, and each role provides a different set of temporary permissions.

---

Why does Lambda use a Role instead of a User?

> Lambda is an AWS service. It assumes an IAM Role to obtain temporary credentials, which is more secure than using long-term access keys.