---
subcategory: "Virtual Private Cloud (VPC)"
---

# huaweicloud\_vpc

Provides details about a specific VPC.
This is an alternative to `huaweicloud_vpc_v1`

## Example Usage

The following example shows how one might accept a VPC id as a variable and use this data source to obtain the data necessary to create a subnet within it.

```hcl

variable "vpc_name" {}

data "huaweicloud_vpc" "vpc" {
  name = var.vpc_name
}

```

## Argument Reference

The arguments of this data source act as filters for querying the available VPCs in the current region. The given filters must match exactly one VPC whose data will be exported as attributes.

* `region` - (Optional, String) The region in which to obtain the vpc. If omitted, the provider-level region will be used.

* `id` - (Optional, String) The id of the specific VPC to retrieve.

* `status` - (Optional, String) The current status of the desired VPC. Can be either CREATING, OK, DOWN, PENDING_UPDATE, PENDING_DELETE, or ERROR.

* `name` - (Optional, String) A unique name for the VPC. The name must be unique for a tenant. The value is a string of no more than 64 characters and can contain digits, letters, underscores (_), and hyphens (-).

* `cidr` - (Optional, String) The cidr block of the desired VPC.



## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `routes` - The list of route information with destination and nexthop fields.

* `shared` - Specifies whether the cross-tenant sharing is supported.
