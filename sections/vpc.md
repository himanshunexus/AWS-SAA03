# VPC and network controls

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Routing](#routing)
- [Security groups versus NACLs](#security-groups-versus-nacls)
- [Private service access](#private-service-access)
- [Troubleshooting order](#troubleshooting-order)

## Routing

- A subnet belongs to one AZ. Route tables determine where packets go; security groups and NACLs control which traffic is allowed.
- A public subnet has a route to an internet gateway. An IPv4 instance still needs suitable addressing and security rules for direct internet connectivity.
- Private IPv4 instances commonly use a NAT gateway for initiated internet access. With zonal NAT gateways, route each AZ through its own NAT for AZ resilience.
- IPv6 outbound-only access uses an egress-only internet gateway; it is not IPv4 NAT.

## Security groups versus NACLs

| Property | Security group | Network ACL |
|---|---|---|
| Scope | Network interface | Subnet boundary |
| State | Stateful | Stateless |
| Rules | Allow | Allow and deny |
| Return traffic | Automatically allowed for tracked flows | Requires appropriate rules |

## Private service access

- Gateway endpoints provide private S3/DynamoDB access through route tables. They cannot be extended to on-premises clients simply through a VPN.
- Interface endpoints use private network interfaces and can support hybrid access with correct routing, security and DNS.
- PrivateLink exposes a service without giving the consumer general network access to the provider VPC.
- VPC peering is not transitive. Transit Gateway provides hub-and-spoke connectivity and route-table segmentation.

## Troubleshooting order

Check DNS, route tables, addressing, security groups, NACL return ports and service policies. Flow Logs show traffic metadata and accept/reject status, not packet payloads.

## Related PDF practice

[Q15](../practice-exams/questions-001-050.md#question-15) · [Q19](../practice-exams/questions-001-050.md#question-19) · [Q55](../practice-exams/questions-051-100.md#question-55) · [Q101](../practice-exams/questions-101-150.md#question-101) · [Q135](../practice-exams/questions-101-150.md#question-135) · [Q184](../practice-exams/questions-151-200.md#question-184) · [Q218](../practice-exams/questions-201-250.md#question-218) · [Q230](../practice-exams/questions-201-250.md#question-230) · [Q231](../practice-exams/questions-201-250.md#question-231) · [Q237](../practice-exams/questions-201-250.md#question-237) · [Q250](../practice-exams/questions-201-250.md#question-250) · [Q251](../practice-exams/questions-251-300.md#question-251) · [Q254](../practice-exams/questions-251-300.md#question-254) · [Q296](../practice-exams/questions-251-300.md#question-296) · [Q318](../practice-exams/questions-301-350.md#question-318) · [Q360](../practice-exams/questions-351-400.md#question-360) · [Q385](../practice-exams/questions-351-400.md#question-385) · [Q406](../practice-exams/questions-401-450.md#question-406) · [Q438](../practice-exams/questions-401-450.md#question-438) · [Q439](../practice-exams/questions-401-450.md#question-439) · [Q448](../practice-exams/questions-401-450.md#question-448) · [Q468](../practice-exams/questions-451-500.md#question-468) · [Q489](../practice-exams/questions-451-500.md#question-489) · [Q497](../practice-exams/questions-451-500.md#question-497) · [Q600](../practice-exams/questions-551-600.md#question-600) · [Q657](../practice-exams/questions-651-684.md#question-657)

## Further reading

- [RonitSachdev: VPC](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/06-VPC.md)

---

[Previous: Amazon S3](s3.md) · [Next: Route 53, CloudFront and global delivery](global-delivery.md)
