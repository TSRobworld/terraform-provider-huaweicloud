---
subcategory: "Web Application Firewall (WAF)"
---

# huaweicloud_waf_address_group

Manages a WAF address group resource within HuaweiCloud.

-> **NOTE:** All WAF resources depend on WAF instances, and the WAF instances need to be purchased before they can be
used. The address group resource can be used in Cloud Mode, Dedicated Mode and ELB Mode.

## Example Usage

```hcl
variable enterprise_project_id {}

resource "huaweicloud_waf_address_group" "example_group" {
  name                  = "example_address_name"
  description           = "example_description"
  ip_addresses          = ["192.168.1.0/24"]
  enterprise_project_id = var.enterprise_project_id
}
```

## Argument Reference

The following arguments are supported:

* `region` - (Optional, String, ForceNew) Specifies the region in which to create the resource.
  If omitted, the provider-level region will be used. Changing this parameter will create a new resource.

* `name` - (Required, String) Specifies the name of the address group. The value consists of 1 to 128 characters.
  Only letters, digits, hyphens (-), underscores (_), colons (:) and periods (.) are allowed.
  The name of each enterprise project by one account must be unique.

* `ip_addresses` - (Required, List) Specifies the IP addresses or IP address ranges.

* `enterprise_project_id` - (Optional, String, ForceNew) The enterprise project ID of WAF address group.
  Changing this parameter will create a new resource.

* `description` - (Optional, String) Specifies the description of the address group.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `id` - The resource ID.

* `rules` - The list of rules that use the IP address group.
  The [rules](#AddressGroup_rules) structure is documented below.

<a name="AddressGroup_rules"></a>
The `rules` block supports:

* `rule_id` - The ID of rule.

* `rule_name` - The name of rule.

* `policy_id` - The ID of policy.

* `policy_name` - The name of policy.

## Import

The WAF address group can be imported using the `id`, e.g.

```bash
$ terraform import huaweicloud_waf_address_group.test 0ce123456a00f2591fabc00385ff1234
```
